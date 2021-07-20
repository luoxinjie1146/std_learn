# xstddef学习笔记

[TOC]

* ```constexpr _Ty* addressof(_Ty& _Val) noexcept``` 用于获取左值表达式的地址。
  * 对于重载```_Ty::operator&```操作符的类型，此函数也可以使用。
  * ```gcc 4.7.1```实现方式如下。详见 [addressof操作符](https://blog.csdn.net/creambean/article/details/89683294)
```cpp
template<typename __Tp>
inline __Tp* __addressof(_Tp& __r) _GLIBCXX_NOEXCEPT
{
    return reinterpret_cast<__Tp*>(&const_cast<char&>(reinterpret_cast<const volatile char&>(__r)));
}
```