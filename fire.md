#### 3. 解决卡死问题。	
	
启动时先按del进入boot界面，按E键,在 "splash" 这个单词后加 “nomodeset”, 按F10启动                

#### 4. 永久解决卡死问题。	

步骤3完成后，开机应当不会出现卡死现象，但是每次开机时都要执行一次步骤3，十分麻烦。

永久解决方案：

sudo gedit /etc/default/grub , 编辑这个文件：	

文件内：	
```
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"  
```
这一行改为
```
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash nomodeset"  
```

以及
```
GRUB_CMDLINE_LINUX="*"
```
这一行改为
```
GRUB_CMDLINE_LINUX="rw"
```

保存，然后 sudo update-grub