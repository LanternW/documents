### 1. VSCode插件安装

``` 
Git Blame
Git Graph (可选)
```

### 2. 登陆git账号

方法1： 在 gitconfig 文件内配置账号
```
git config --global user.name "$USERNAME"
git config --global user.email "$email"
```

方法2：



### 3. 移交暂存、提交暂存、远程推送

```
git add .
git commit -m "update what"
git push
```

分别对应在 source control 中的操作

### 4. 本地仓库搭建

在 workspace 母文件夹下运行指令
```
git init
```

### 5. 克隆远程仓库
将完全复制远程仓库的代码及**历史版本**
```
git clone [url]
```

### 6. 忽略某些文件

某些文件不加入版本控制，需要在 workspace 中建立 .gitignore 文件。 .gitignore 编写规则：

+ 注释采用 "#" 开头
+ “*” 代表任意数目字符
+ “？”代表一个字符
+ 方括号 [abc] 代表可选字符范围为a,b,c
+ 大括号 {str1, str2,...} 代表可选字符串
+ 名称前加 “!” 表示此文件为例外
+ 路径符“/” 在前表示要忽略此目录/..下的所有文件，不包括子目录
+ 路径符“/” 在后面表示忽略此目录下所有文件，不包括子目录
  
示例：
```
*.txt          #忽略所有txt文件
!lib.txt       # lib.txt 除外
build/         # 忽略build/ 目录下所有文件
```
### 7. 链接 github 远程仓库   

**7.1 和 7.2的步骤是实现电脑免密登录 github**
#### 7.1 配置SSH公钥

user目录下（windows为 C:\Users\[UserName]）开启隐藏文件显示，查看是否有.ssh 目录及此目录下是否有id_rsa和id_rsa.pub这两个文件，若无，创建SSH密钥：
```
ssh-keygen -t rsa -C "email"
```
email 保持与 giuthub账号一致，其余选项默认，通常无需设置密码。

执行完毕后

.ssh/id_rsa 是私钥，不能泄露出去。

.ssh/id_rsa.pub 是公钥，可以放心地告诉任何人。

#### 7.2 github设置

登陆 GitHub，打开“Account settings”，“SSH Keys”页面：

然后，点“Add SSH Key”，填上任意 Title，在 Key 文本框里粘贴id_rsa.pub文件的内容

点“Add Key”，你就应该看到已经添加的 Key。

#### 7.3 仓库关联

在 github 上创建仓库，假设叫做 ccc ,在本地 workspace 下运行指令：
```
git remote add [r_name] git@github.com:[Github Username]/ccc.git
```
其中 [r_name] 为远程仓库在本地的命名，习惯上命名为 origin
[Github Username]是github用户名。
```
git remote add origin git@github.com:LanternW/ccc.git
```




