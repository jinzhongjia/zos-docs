## GDT



全局描述符表GDT（Global Descriptor Table）在整个系统中，全局描述符表GDT只有一张(一个处理器对应一个GDT)，GDT可以被放在内存的任何位置，但CPU必须知道GDT的入口，也就是基地址放在哪里，Intel的设计者门提供了一个寄存器GDTR用来存放GDT的入口地址，程序员将GDT设定在内存中某个位置之后，可以通过LGDT指令将GDT的入口地址装入此寄存器，从此以后，CPU就根据此寄存器中的内容作为GDT的入口来访问GDT了。GDTR中存放的是GDT在内存中的基地址和其表长界限。

> 分段管理可以把虚拟地址转换成线性地址，而分页管理可以进一步将线性地址转换成物理地址。
>（根据段选择子找到）段基指 + 偏移地址 => 线性地址
> 线性地址 （通过页表） => 物理地址


## 参考文章

- [GDT Tutorial](https://wiki.osdev.org/GDT_Tutorial#Survival_Glossary)
- [段描述](https://wiki.osdev.org/Segmentation)
- [【构建操作系统】全局描述符表GDT](https://zhuanlan.zhihu.com/p/25867829)
- [cpu three mode](https://sunra.top/2022/02/06/three-cpu-mode/)
- [Global Descriptor Table](https://wiki.osdev.org/Global_Descriptor_Table)

- [Interrupt Service Routines](https://wiki.osdev.org/Interrupt_Service_Routines)