---
layout: post
title:  "RecyclerView"
date:   2018-01-07
categories: android
image: https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/android.png
---

<https://developer.android.com/training/material/lists-cards.html>

## RecyclerView

- ListView의 더욱 향상되고 유연해진 버전
- 한정된 수의 뷰를 유지함으로써 매우 효율적으로 스크롤할 수 있는 큰 데이터 집합을 표시하기 위한 컨테이너

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/rc.png)	

## LayoutManager

- 항목 뷰를 RecyclerView 내에 배치
- 사용자에게 더 이상 보이지 않는 항목 뷰를 언제 재사용할지 결정
- 뷰를 재사용 (또는 재활용)하기 위해, Adapter에게 뷰의 콘텐츠를 데이터 집합의 다른 요소로 교체하도록 요청
- 이런 방식으로 뷰를 재활용하면 불필요한 뷰 생성이나 리소스를 많이 소모하는 findViewById()를 수행하지 않아도 되므로 성능이 개선

	- LinearLayoutManager : 항목을 가로 또는 세로 스크롤 목록으로 표시
	- GridLayoutManager : 그리드 형식으로 항목을 표시
	- StaggeredGridLayoutManager : 지그재그형의 그리드 형식으로 항목을 표시

## 사용방법
- RecyclerView 위젯을 레이아웃에 추가

```
<!-- A RecyclerView with some commonly used attributes -->
<android.support.v7.widget.RecyclerView
    android:id="@+id/my_recycler_view"
    android:scrollbars="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"/>
```

- 객체 핸들을 얻어 LayoutManager에 연결
- 표시할 데이터의 어댑터를 첨부

````
public class MyActivity extends Activity {
    private RecyclerView mRecyclerView;
    private RecyclerView.Adapter mAdapter;
    private RecyclerView.LayoutManager mLayoutManager;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.my_activity);
        mRecyclerView = (RecyclerView) findViewById(R.id.my_recycler_view);

        // use this setting to improve performance if you know that changes
        // in content do not change the layout size of the RecyclerView
        mRecyclerView.setHasFixedSize(true);

        // use a linear layout manager
        //객체 핸들을 얻어 LayoutManager에 연결
        mLayoutManager = new LinearLayoutManager(this);
        mRecyclerView.setLayoutManager(mLayoutManager);

        // specify an adapter (see also next example)
        // 표시할 데이터의 어댑터를 첨부
        mAdapter = new MyAdapter(myDataset);
        mRecyclerView.setAdapter(mAdapter);
    }
    ...
}
```

## Adapter

- 데이터 집합의 항목에 액세스할 수 있게 해주고,
- 항목 뷰를 생성하고, 
- 원래의 항목이 더 이상 보이지 않을 경우 일부 뷰의 콘텐츠를 새 데이터 항목으로 교체

```
public class MyAdapter extends RecyclerView.Adapter<MyAdapter.ViewHolder> {
    private String[] mDataset;

    // Provide a reference to the views for each data item
    // Complex data items may need more than one view per item, and
    // you provide access to all the views for a data item in a view holder
    public static class ViewHolder extends RecyclerView.ViewHolder {
        // each data item is just a string in this case
        public TextView mTextView;
        public ViewHolder(TextView v) {
            super(v);
            mTextView = v;
        }
    }

    // Provide a suitable constructor (depends on the kind of dataset)
    public MyAdapter(String[] myDataset) {
        mDataset = myDataset;
    }

    // Create new views (invoked by the layout manager)
    @Override
    public MyAdapter.ViewHolder onCreateViewHolder(ViewGroup parent,
                                                   int viewType) {
        // create a new view
        View v = LayoutInflater.from(parent.getContext())
                               .inflate(R.layout.my_text_view, parent, false);
        // set the view's size, margins, paddings and layout parameters
        ...
        ViewHolder vh = new ViewHolder(v);
        return vh;
    }

    // Replace the contents of a view (invoked by the layout manager)
    @Override
    public void onBindViewHolder(ViewHolder holder, int position) {
        // - get element from your dataset at this position
        // - replace the contents of the view with that element
        holder.mTextView.setText(mDataset[position]);

    }

    // Return the size of your dataset (invoked by the layout manager)
    @Override
    public int getItemCount() {
        return mDataset.length;
    }
}

```

	

