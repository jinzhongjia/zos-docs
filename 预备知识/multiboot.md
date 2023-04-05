# 什么是 multiboot

multiboot 是一个开放标准，它描述了引导程序应该如何加载 x86 操作系统内核，该规范允许任何兼容的引导加载程序实现来引导任何兼容的操作系统内核。因此，它允许不同的操作系统和引导加载程序一起工作和互操作，而不需要特定于操作系统的引导加载程序。因此，它还允许不同操作系统更容易地在一台计算机上共存，这也称为多重启动。

简单来说，multiboot可以帮我们完成引导启动，还有从实模式到保护模式转换这一过程，我们只需要专注于实现内核即可。

## 历史

该规范最初创建于 1995 年，由自由软件基金会开发。 GNU Hurd、VMware ESXi、Xen 和 L4 微内核都需要使用此方法启动。 GNU GRUB 是 GNU 操作系统和其他操作系统中使用的参考实现。截至 2019 年 7 月，Multiboot 规范的最新版本是 0.6.96，定义于 2009 年。与 UEFI 支持不兼容的第二次迭代，即 Multiboot2 规范，后来被引入。截至 2019 年 4 月，Multiboot2 的最新版本是 2.0，定义于 2016 年。

## 简单技术性概述

> While Multiboot defines a header as a struct, which needs to be present in the image file as a whole, in Multiboot2, fields or group of fields have a type tag, which allows them to be omitted from the Multiboot2 header.
>
> Within the OS image file, the header must be in the first 8192 (213) bytes for Multiboot and 32768 (215) bytes for Multiboot2. The loader searches for a magic number to find the header, which is 0x1BADB002 for Multiboot and 0xE85250D6 for Multiboot2.
>
> In the header, entry_addr points to the code where control is handed over to the OS. This allows different executable file formats (see Comparison of executable file formats). If the OS kernel is an ELF file (Executable and Linkable Format), which it is for the Linux kernel, this can be omitted for Multiboot2. The ELF format is very common in the open source world and has its own field (e_entry) containing the entry point.
>
> Before jumping to the OS entry point, the boot loader must provide a boot information structure to tell the OS how it left the system; for Multiboot, this is a struct, and for Multiboot2, every field (group) has a type tag and a size.

## 参考

- 0.9.6 规范翻译版本：[前往](https://www.cnblogs.com/chio/archive/2008/01/01/1022430.html)
- 0.9.6 官方规范：[前往](https://www.gnu.org/software/grub/manual/multiboot/multiboot.html#Boot-information-format)
- 2.0   官方规范：[前往](https://www.gnu.org/software/grub/manual/multiboot2/multiboot.html)