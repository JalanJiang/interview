## 系统

### 简述 Linux 开机启动的过程？

![Linux 开机启动过程](/img/os/linux-begin.png)

1. 电脑接通电源，电脑开始执行 BIOS（基本输入输出系统 Basic I/O System）的 POST（上电自检 Power On Self Test）过程
    - BIOS
        - 是一个固件（嵌入在硬件中的软件），BIOS 程序存放在断电后内容不会丢失的只读内存中
        - 是开机的时候计算机执行的第一个程序，这个程序知道可以开机的磁盘，并读取磁盘第一个扇区的**主要开机记录**（MBR）
    - POST
        - 检查 CPU 、内存和其他硬件，若没有异常就开始加载 BIOS 程序到内存当中
2. 读取 MBR 的引导文件（grub，lilo）
    - MBR
        - 存储于磁盘的头部，大小为 512 Bytes，其中，446 Bytes 用于存储 BootLoader 程序，64 Bytes 用于存储分区表信息，最后 2 Bytes 用于 MBR 的有效性检查
        - 主要开机记录（MBR）中的开机管理程序提供以下功能
            1. 选单
            2. 载入核心文件
            3. 转交其它开机管理程序
    - GRUB(Grand Unified Bootloader)，多系统启动程序，查找并加载 Kernel
3. 引导 Linux 内核，GRUB 将 Kernel 读进内存
    - Kernel 以只读方式挂载根文件系统
    - 当根文件系统被挂载后，开始装载第一个进程（用户空间的进程）
    - 执行 `/sbin/init`，之后就将控制权交接给了 init 程序
4. 运行第一个进程 init（进程号永远为1）
    - 进行 OS 初始化操作
5. 启动指定级别的服务，不同的级别会启动的服务不一样
    - Linux的启动级别分为以下几种
        1. 关机模式
        2. 单一用户模式（直接以管理员身份进入）
        3. 多用户模式（无网络）
        4. 保留
        5. 多用户模式（图形界面）
        6. 重启
6. 运行终端，输入用户名和密码

### Linux 系统是由那些部分组成？

- Linux 系统内核
- Shell
- 文件系统
- 应用程序

### 硬链接和软链接有什么区别？

## 参考资料

- [Linux启动过程](https://www.cnblogs.com/codecc/p/boot.html)