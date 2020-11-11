## Ubuntu 18.04或者20.04 安装显卡驱动
#### 屏蔽开源驱动nouveau
下面命令sudo 开始 安装过程会询问是否屏蔽，手动屏蔽也有多种操作方式，终端输入  
`sudo gedit /etc/modprobe.d/blacklist.conf`  
加参数到最底下回车另起一行内容为  
```
blacklist nouveau 
options nouveau modeset=0
```  
保存再终端更新内核命令 终端输入  
`sudo update-initramfs -u sudo apt update `  
`sudo apt install gcc g++ make`  
然后重启电脑  `reboot`  
***

#### nvidia官网下对应显卡版本的驱动  
[英伟达驱动下载地址](https://www.nvidia.cn/Download/index.aspx?lang=cn)  

举例（下面XXX是版本的意思）  
NVIDIA-Linux-x86_64-440.run （384或者440都可以版本里面的）  
*下好的文件放在 主文件夹 或者说叫home目录下*    
***

**先按Ctrl + Alt + F3到控制台，关闭当前图形环境**    
输入  
`sudo telinit 3`   
再安装驱动程序输入  
*这里输入用户名 然后会跳出输入密码的提示(再输入密码)* 
`cd /home/用户名`  
*进入到驱动所在文件夹（下好的驱动文件放在home 或者叫主文件夹下）*  
输入    
`sudo chmod a+x NVIDIA-Linux-x86_64-xxx.run sudo sh NVIDIA-Linux-x86_64-xxx.run -no-opengl-files`  
最后重新启动  `reboot`  

安装完成  
