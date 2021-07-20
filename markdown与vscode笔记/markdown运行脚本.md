```bash {cmd=true}
ls .
```

```javascript {cmd="node"}
const date = Date.now()
console.log(date.toString())
```

```cpp {cmd="cl.exe"}
#include <iostream>
int main(){
    std::cout << "Hello World!" << std::endl;
}
```

脚本运行默认是禁用的并且需要在 Atom 和 VSCode 的插件设置中开启来进行使用

请小心使用这一特性，因为它很有可能造成安全问题！ 当你的脚本运行设置是开启的，你的电脑很有可能被黑客攻击，如果有人使你运行了 Markdown 文档中的恶意代码。

设置名称： enableScriptExecution

命令 & 快捷键

    Markdown Preview Enhanced: Run Code Chunk 或者 shift-enter 运行你现在光标所在的一个 code chunk。
    Markdown Preview Enhanced: Run All Code Chunks 或者 ctrl-shift-enter 运行所有的 code chunks。

详细内容：[Code Chunk](https://shd101wyy.github.io/markdown-preview-enhanced/#/zh-cn/code-chunk)