ELF (Executable and Linkable Format)是一种为可执行文件，目标文件，共享链接库和内核转储(core dumps)准备的标准文件格式。

一个ELF文件由以下三部分组成：

-   ELF头(ELF header) - 描述文件的主要特性：类型，CPU架构，入口地址，现有部分的大小和偏移等等；
    
-   程序头表(Program header table) - 列举了所有有效的段(segments)和他们的属性。 程序头表需要加载器将文件中的节加载到虚拟内存段中；
    
-   节头表(Section header table) - 包含对节(sections)的描述。

具体信息可以参考该[文章](https://xinqiu.gitbooks.io/linux-inside-zh/content/Theory/linux-theory-2.html)