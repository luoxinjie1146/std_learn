# xtr1common学习笔记

[TOC]

* ```template<class _Ty, _Ty _Val> struct integral_constant;``` 编译时常量。
* ```template<bool _Val> using bool_constant = integral_constant<bool, _Val>;``` 编译时布尔类型常量。
* ```using true_type  = bool_constant<true>;``` 编译时```true```常量。
* ```using false_type = bool_constant<false>;``` 编译时```false```常量。