# 简介

ABI 是编译器和链接器遵守的一组规则，以让编译后的程序可以正常工作。ABI 里包含很多方面的内容：

ABI 最大和最重要的部分是规定函数的调用顺序，也称为“调用约定”。调用约定标准化了如何将“函数”转换为汇编代码。
ABI 还规定了库中公开函数的 name（如 printf）应该如何表示，以便在链接后可以正确的调用这些库函数并接收参数。
ABI 还规定可以使用什么类型的数据类型、它们必须如何对齐以及其他低级细节。
此外，ABI 还涉及操作系统的内容，如可执行文件的格式，虚拟地址空间布局，还有 Program Loading and Dynamic Linking 等细节。

## 参考资料

-   [ABI 接口](https://zhuanlan.zhihu.com/p/386106883)
-   [Linux Standard Base](https://refspecs.linuxfoundation.org/)
-   [C 与汇编语言混合使用](https://cq674350529.github.io/2020/01/13/C与汇编语言混合使用/)
-   [Application binary interface](https://en.wikipedia.org/wiki/Application_binary_interface)
-   [System V ABI](https://wiki.osdev.org/System_V_ABI)
-   [x86 calling conventions](https://en.wikipedia.org/wiki/X86_calling_conventions#List_of_x86_calling_conventions)
