# xmemory学习笔记

[TOC]

## allocator\<class _Ty\>

* 模板参数```_Ty```不能被```const```修饰。
* ```constexpr```类型。
* ```_Ty* address(_Ty& _Val) const noexcept``` 取地址。
  * ```_Val```必须是allocated分配的空间。
  * 为保证安全，std使用 [addressof](xstddef.md) 实现。