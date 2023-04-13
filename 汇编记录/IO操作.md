设备和芯片的I/O端口操作实现，其实没有复杂的东西在里边 ;
I/O端口操作主要是看一堆文档，把整个X86架构的PC机所有I/O端口记住， ;

并记住它们每一个数据寄存器、命令寄存器等操作访问标准（也可以称之协议） ;

记住之后，整个过程中就是按标准使用I/O指令： ;

in, out（只能与DX,AX,AL寄存器结合使用） ;

下面的实现是提供给C使用，因为不太喜欢GNU的inline asm，语法太 ;

晦涩，所以直接使用汇编实现。

inb 从I/O端口读取一个字节(BYTE, HALF-WORD) ;

outb 向I/O端口写入一个字节（BYTE, HALF-WORD） ;

inw 从I/O端口读取一个字（WORD，即两个字节） ;

outw 向I/O端口写入一个字（WORD，即两个字节） ;

byte inb(word port); ;

word inw(word port); ;

void outb(word port, byte value); ;

void outw(word port, word value); ;