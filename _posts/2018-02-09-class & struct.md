---
layout: post
title:  "class VS struct"
date:   2018-02-06 00:27:03 +0900
categories: cs
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cs_img.jpg
---

### type

- class 
	- reference type
- struct 
	- value type

### allocation

- class 
	-  are allocated on the heap and garbage-collected
- struct
	- are allocated either on the stack or inline in containing types 
	- and deallocated when the stack unwinds or when their containing type gets deallocated.
	- allocations and deallocations are in general cheaper than reference types.

### arrays

- class
	- arrays of reference types are allocated out-of-line, 
	- meaning the array elements are just references to instances of the reference type residing on the heap
- struct
	 - Value type arrays are allocated inline, meaning that the array elements are the actual instances of the value type.
	 - allocations and deallocations of value type arrays are much cheaper than reference type arrays. 

### memory usage

- class
	- no boxing occurs as reference types are cast.
- struct
	 -  get boxed when cast to a reference type or one of the interfaces they implement.
	 -  get unboxed when cast back to the value type
	 -  Because boxes are objects that are allocated on the heap and are garbage-collected, 
	 -  too much boxing and unboxing can have a negative impact on the heap, the garbage collector, and ultimately the performance of the application

### copy

- class
	- reference type assignments copy the reference
	- assignments of large reference types are cheaper than assignments of large value types.
- struct 
	- value type assignments copy the entire value

### pass

- class
	- reference types are passed by reference
	- Changes to an instance of a reference type affect all references pointing to the instance
- struct
	- value types are passed by value
	- Value type instances are copied when they are passed by value.
	- When an instance of a value type is changed, it of course does not affect any of its copies. 
	- Because the copies are not created explicitly by the user but are implicitly created when arguments are passed or return values are returned, value types that can be changed can be confusing to many users. 
	- Therefore, value types should be immutable.


	
