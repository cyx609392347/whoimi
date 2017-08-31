用VC6在64位Windows7下调试的时候，如果中断(Shift+F5)调试，程序无法退出。

**问题描述：**
当点击F5开始一个项目的调试时，程序在设置的断点处停止，这时按下Shift+F5后，vc6可以退出调试状态，但是WINDOWS系统的任务栏上会留下前面调试时产生的进程图标。该进程不能被结束，即使使用任务管理器，也不可以。这时如果再次按下F5调试，并按下Shift+F5后，任务栏上会留下两个这样的图标，这两个进程都可以在任务管理器上看到，不占CPU资源，但占用一定的内存。结束该进程的唯一的办法是（在任务栏上去掉该图标）：关闭VC6,并重新开启.

**一般的解决方法：**
不使用"结束调试"这个功能,让程序正常结束(就是放个可以退出的菜单或者按钮, 而不是使用Shift+F5的退出)。

**终极解决方法：**
替换DM.dll和TLLOC.DLL为正确的版本。首先下载正确版本：VC6.zip（里面包含这两个dll），然后将下载的版本替换到程序安装目录“Common/MSDev98/Bin/TLLOC.dll”和“Common/MSDev98/Bin/DM.dll”，这样VC6在windows 7 64位的系统调试时，就可以任意退出了。

[back](../../index.md)