# #pramga用法

[TOC]

## #pragma pack

* 设置数据对齐方式。
* 详见 [#pragma pack](https://www.cnblogs.com/flyinggod/p/8343478.html)

## #pragma warning

* 该指令允许有选择性的修改编译器的警告消息的行为
* 详见 [#pragma warning](https://blog.csdn.net/weixin_38271274/article/details/82893337)

## #pragma push_macro/pop_macro

在三方库源码中，我们经常看到这样的代码：

```cpp {cmd}
#pragma push_macro("new")

#undef new

// do something with new

......

#pragma pop_macro("new")
```

它的作用就是将宏定义new压入栈并取消它的定义，如此一来new的本来含义便获得了恢复，使用完毕后将宏定义new弹出栈，恢复宏定义。
详见 [#pragma push_macro](https://blog.csdn.net/ixsea/article/details/7976627)