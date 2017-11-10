---
layout: post
title:  "express-passport"
date:   2017-09-27 00:27:03 +0900
categories: node
---

### session 등록

````
app.use(session({secret:'MySecret', resave: false, saveUninitialized:true}));
````

### passport가 등록한 session 사용하도록 등록

````
app.use(passport.initialize());
app.use(passport.session());
````

### userSchema의 method에 authenticate 등록

````
userSchema.methods.authenticate = function (password) {
  var user = this;
  return password==user.password ?  true : false;
};
````

````
/login으로 들어오면 passport.authenticate middle ware가 실행이 돼
그럼 middleware의 local-login 에 의해서 
passport에 등록된 Local Strategy 라는 객체의 인자인 콜백함수가 실행이 됨

router.post('/login', passport.authenticate('local-login', {
  successRedirect : '/posts',
  failureRedirect : '/login',
  failureFlash : true
}));
````

### id, pwd 확인

````
passport.use('local-login',
  new LocalStrategy({
      usernameField : 'email',
      passwordField : 'password',
      passReqToCallback : true
    },
    function(req, email, password, done) {
      User.findOne({ 'email' :  email }, function(err, user) {
        if (err) return done(err);
        if (!user){
            req.flash("email", req.body.email);
            return done(null, false, req.flash('loginError', 'No user found.'));
        }
        if (!user.authenticate(password)){
            req.flash("email", req.body.email);
            return done(null, false, req.flash('loginError', 'Password does not Match.'));
        }
        return done(null, user);	//login 끝났는데 false가 아니면 login한 사용자에 대한 객체로 사용
      });
    }
  )
);
````

### passport.serializeUser 에서 등록한 call back 함수 실행

````
passport.serializeUser(function(user, done) {
  done(null, user.id);  //현재 접근하고 있는 사용자의 user.id(db의 고유 아이디)가 session에 저장.
});
````

### 다시 사용자가 웹에 방문하면 passport.deserializeUser에 등록된 call back 함수 실행

````
passport.deserializeUser(function(id, done) {
  User.findById(id, function(err, user) {
    done(err, user);
  });
});
````
