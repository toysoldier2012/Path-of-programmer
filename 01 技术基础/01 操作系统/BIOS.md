
Base I/O System，允许系统监测各种外设，并加载相应软件。
BIOS 在 SOC 内部的 iROM 中，是固化代码。
在启动时，BIOS 从固定位置开始执行，在x86系统中为CS:IP=0xf000:fff0，其中CS为段寄存器，IP为指令指针寄存器
