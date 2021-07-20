# type_traits学习笔记

[TOC]

本文件包含所有std内编译时推断的类型。C++提供了强大的模板参数推断机制，可以利用模板参数推断进行编译时类型判断。

例如：

```cpp {cmd .line-numbers}
// STRUCT TEMPLATE is_const
template <class>
_INLINE_VAR constexpr bool is_const_v = false; // determine whether type argument is const qualified

template <class _Ty>
_INLINE_VAR constexpr bool is_const_v<const _Ty> = true;
```

```cpp {.line-numbers}
is_const_v<int>;
is_const_v<const int>;
```

编译器首先会匹配特化的模板，当调用```is_const_v<const int>```时，特化模板成功匹配```_Ty=const int```，```is_const_v=true```。当调用```is_const_v<int>```时，```int```无法匹配```const _Ty```，特化模板匹配失败，此时```is_const_v=false```。

## 四种模板

详见 [四种模板](https://blog.csdn.net/zwvista/article/details/54612025)

C++11添加别名模板

```cpp
template<typename T, typename U>
struct A;
 
template<typename T>
struct B
{
    typedef A<T, int> type;
};
 
template<typename T>
using C = A<T, int>;
 
template<typename T>
using D = typename B<T>::type;
```

C++14添加变量模板，相当于一个没有参数但是有返回值的函数模板

```cpp
#include <iostream>
#include <iomanip>
using namespace std;
// 函数模板
template<class T>
constexpr T pi_fn()
{
    return T(3.1415926535897932385);
}
// 变量模板
template<class T>
constexpr T pi = T(3.1415926535897932385);
 
int main()
{
   cout << pi_fn<int>() << pi<int> << '\n'; // 33
   cout << setprecision(10) << pi<float> << '\n'; // 3.141592741
   cout << setprecision(10) << pi<double> << '\n'; // 3.141592654
}
```

## 模板参数推断

* const推断

```cpp {cmd}
// STRUCT TEMPLATE is_const
template <class>
_INLINE_VAR constexpr bool is_const_v = false; // determine whether type argument is const qualified

template <class _Ty>
_INLINE_VAR constexpr bool is_const_v<const _Ty> = true;
```

## type_traits包含内容

1. ```template<class> constexpr bool is_const_v;``` 当T被const修饰时返回true，否则返回false。