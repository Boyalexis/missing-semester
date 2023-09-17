---
theme: v-green
highlight: a11y-dark
---
## Lecture1:Course Overview + the Shell
### 常用linux指令
cd：进入文件夹

ls：列出文件夹中的文件

mkdir：创建文件夹

touch：创建文件

cat：查看文件内容

man：查看某个指令的手册

sudo：以root用户的权限执行指令

chomd：修改文件或文件夹的访问权限，访问权限分为`读`，`写`,`执行`，三项权限可以用数字表示，即`r(读read)=4`，`w(写write)=2`、`x(执行execute)=1`。而每个文件/文件夹对应不同的用户有不同的权限，第一个`rw`代表文件所有者拥有`读和写`的权限，第二个`r`代表文件所有组拥有`读`的权限
，第三个`r`代表其他用户也只拥有`读`权限
![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/ea57d7a5d1774f43b48d98775c0d0a12~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=788&h=303&s=47792&e=png&b=000000)

rm：删除文件或目录


![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/eebcaf81f99a4826b2dbdb4f783c88b7~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=405&h=978&s=689513&e=png&b=f3eff3)

clear：清屏

### git工作原理
四个工作区域：`Workspace工作区`、`Stage暂存区`、`Repository本地仓库`、`Remote Directory远程仓库`

git add  将工作区文件加入暂存区
git commit  将暂存区文件加入本地仓库

### git操作
`git config`：查看git配置

`git clone url`：从github上克隆项目

`git checkout`： <文件名> 撤回已add进暂存区的文件

`git reset`： 撤回已commit到本地仓库的文件


### 如果在github寻找好的开源项目
可以在这里可以找到别人分享的很多有意思的github项目

[稀土掘金](https://juejin.cn/)

[git trending](https:github.com/trending)

[HelloGithub](https://github.com/521xueweihan/HelloGitHub)

[阮一峰科技爱好者周刊](https://www.ruanyifeng.com/blog/weekly/)

### 在github特殊的找资源小技巧
`找百科大全：搜索awesome xxx，例如搜索vue百科`


![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/e2b143d7a95e482297de43a7f0885b77~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=2559&h=1206&s=320211&e=png&b=fefefe)

`找例子 xxx sample，例如找机器学习的相关例子`

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/40a610f3fd0e4c2f874ede1ba57e934d~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=2513&h=1202&s=346162&e=png&b=fefefe)

`找空项目架子 xxx starter/xxx boilerplate`

![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/c475ad47f72646d48c985ce285b0bff3~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=2559&h=1206&s=345006&e=png&b=fefefe)

`找教程 xxx tutorial`

![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/78594e1eac754d0baabe3a56a407363d~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=2559&h=1206&s=330125&e=png&b=fefefe)

### git add . git add -A git add -u的区别
**·** git add -A  提交所有变化

**·**  git add -u  提交被修改(modified)和被删除(deleted)文件，不包括新文件(new)

**·**  git add .  提交新文件(new)和被修改(modified)文件，不包括被删除(deleted)文件


`提问：git clone和Download ZIP有什么区别？`

Download ZIP下载下来的只是一个【文件夹】，与git没有任何关系，只有通过git init初始化后才能变成一个git仓库，而git clone下来的是一个【仓库】

## Lecture2:Shell Tools and Scripting
vim
```bash
mcd() {
    mkdir "$1"
    cd"$1"
}
```
:wq
mcd test

```bash
alexis@DESKTOP-0E6M7UV MINGW64 ~/Desktop/gitlearn/test (master)
$ echo "hello"
hello

alexis@DESKTOP-0E6M7UV MINGW64 ~/Desktop/gitlearn/test (master)
$ echo $?
0
```

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/e735a72b679947efb893177288e1f17e~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=717&h=161&s=15794&e=png&b=000000)

如果我们执行`grep football mcd.sh`，然后检查错误代码，可以看到错误代码为`1`，这是因为我们在`mcd.sh`文件中查找football字符串，但是该字符串不存在，所以grep不会返回任何内容，但会返回1的错误代码告诉我们发生了错误
![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/f3dbd77906f14e00b8bb66f9b3636374~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=672&h=131&s=15048&e=png&b=000000)
这里需要注意的是，true的错误代码始终为0，false的错误代码始终为1

花括号{}

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/43312eb4e57741d98b66476029240f72~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=732&h=116&s=15969&e=png&b=000000)

### 管道符 `|`
**作用：管道是一种通信机制，通常用于进程间的通信。**

**它表现出来的形式将**

**前面每一个进程的输出（stdout）直接作为下一个进程的输入（stdin） 。**

## Lecture4 data wrangling
journalctl
ssh通过命令行远程访问计算机
### grep

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/16335b828c384fefa762810c13d26c5a~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=876&h=482&s=29316&e=png&b=000000)
```shell
$ grep "test" greptext
```
默认情况下，grep在查找字符串时区分大小写，因此我们可以看到大写`TEST`并没有被打印出来，不过grep提供一个参数`-i`，可以在查找时不区分大小写
```shell
$ grep -i "test" greptext
```

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/3c47021f999141b89ca8d49894781578~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=662&h=138&s=15170&e=png&b=000000)

如果我们想知道文本内容第几行匹配字符串，我们还可以使用参数`-n`来显示被打印内容在文本中的行号
```shell
$ grep -i -n "test" greptext
```

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/f87e87b1d0a04621a3f25742414a8a1c~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=645&h=132&s=15615&e=png&b=000000)

`tips：-n+数字（例如-n5）可以只显示五行`
#### 高亮显示`--color`

这个时候还有一个问题。虽然字符串“test”被打印出来了，但是一旦匹配到的内容行增加到1000行，我们很难看出匹配到的内容，因此可以使用`--color`参数将匹配内容高亮显示

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/063f0a5bf9ca4005b62d90483067938d~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=645&h=138&s=16412&e=png&b=000000)
#### 匹配其他行：`-B`,`-A`,`-C`

此外还有诸如`-B+n`、`-A+n`、`-C+n`这类命令可以打印出匹配行的前`n`行、后`n`行和前后`n`行。`-B`有Before之意，`-A`有After之意，`-C`有Context之意。我们在`greptext`中加入以下测试信息：

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/51148124880f44d4ab176748f314dec0~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=293&h=237&s=10732&e=png&b=000000)

```shell
$ grep -n --color -B1 "年龄：18" greptext    // 查找年龄为18的同学，打印匹配内容的前1行，高亮显示并显示行号
```

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/5dff3b9ad3f0498e8c22afa479c6a457~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=669&h=152&s=15859&e=png&b=000000)
```shell
$ grep -n --color -A1 "年龄：18" greptext    // 查找年龄为18的同学，打印匹配内容的后1行，高亮显示并显示行号
```

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/3f3d3b7caf6044b5bb9e027ec65d5641~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=660&h=153&s=15263&e=png&b=000000)

```shell
$ grep -n --color -C1 "年龄：18" greptext
```

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/0e5e744e727e4d42896dfc3f8f1b6bd3~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=665&h=195&s=18873&e=png&b=000000)

#### 此外还有一些其他的常用参数

`-w`：精准匹配

`-e`：同时匹配多个目标

`-o`:只显示符合条件的字符串，但是不整行显示，每个符合条件的字符串单独显示一行

`-q`：静默查找，只关心有没有查到，不关心查到的内容是什么，可以使用`echo $?`返回查找结果，0表示查找失败，1表示查找成功

`-v`：反向查找，查找不包含某个字符串的行

### less
less可以看作是分页器

### sed
sed是一个“流编辑器”，它允许你修改流的内容，你可以将其视为文本替换

sed最常见的操作
```shell
$ cat ssh.log | sed 's/.*Disconnected from //' | less
```
上面这条指令指的是查看ssh日志，并将文本内容传输给sed，sed将其内容修改，将“Disconnected from”及之前的内容替换为空，并传输给less分页显示
这里的`s/.*Disconnected from //`为正则表达式，第一个`/`后是搜索字符串，第二个`/`后是要换成的字符串，这里为空，因此可以理解为`s(ubstitute)字符串“.*Disconnected from ”，并将其替换为空`

### 正则表达式Regular Expression
`.`表示任意单个字符，`*`表示匹配零次或多次该字符，因此`.*`表示匹配零次或多次任意字符

`+`表示匹配一次或多次

`\w`匹配包括下划线的任何单词字符，等价于 [A-Z a-z 0-9_]

`\s`匹配空格

`[]`匹配括号中任一字符

`g`尽可能多的匹配

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/1f23fb61af5645999322680951d4c31f~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=1260&h=624&s=117657&e=png&b=f6f4f4)
```shell
$ echo 'abaabbbaababc' | sed 's/[ab]//g'
c
```
此外我们也可以使用()来匹配整个字符串`ab`
```shell
$ echo 'ababcaba' | sed -E 's/(ab)*//g'
ca
```
如果你不用`-E`进入扩展正则表达式，也可以使用转义符`\`，否则sed会认为你需要匹配的是括号
```shell
$ echo 'ababcaba' | sed 's/\(ab\)*//g'
ca
```
#### 捕获组capture group
捕获组就是把正则表达式中子表达式匹配的内容，保存到内存中以数字编号或显式命名的组里，方便后面引用。
在正则表达式中`()`为一个捕获组，例如在这个例子中，捕获组为`(invalid |authenticating )`，`(.*)`和`(\[preauth\]))`
```shell
$ cat ssh.log | sed -E 's/.*Disconnected from (invalid |authenticating )?user (.*) [0-9.]+ port [0-9]+ (\[preauth\])?$/\2/'
```
最后`\2`为获取第二个捕获组，该命令的意义是先匹配整行，最后在替换中放入第二个捕获组匹配的值

正则表达式可以变得非常复杂，但这都是一步一步调试、修正过来的，这里有一个[正则表达式调试器](https://regex101.com/)，你可以把你所写的正则表达式写入，查看匹配到的值
#### uniq
uniq会查看一个排序后的行列表，然后将重复的行去掉
```shell
$ cat ssh.log | sed -E 's/^.*Disconnected from (invalid |authenticating )?user (.*) [0-9.]+ port [0-9]+ ( \[preauth\])?$/\2/'

```

#### awk

### 提问环节
Q1：[0-9.]+代表的意思是？

A1：匹配数字`0-9`以及`.`中的一个或多个

Q2：`.*`代表的意思是?

A2：

### Exercise课后练习
https://regexone.com/

## Lecture5 命令行环境

### nohup
nohup全称no hang up（不挂起），也就是说当命令行关闭后，进程仍在执行
```shell
$ nohup Command [Arg...] [ &]
```
`&`：表示在后台运行程序，不占用命令行

![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/28fa91b4b5ca4f02b427fb7733c2f61c~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=641&h=396&s=38544&e=png&b=000000)
### bg继续执行进程
当你的进程被放到后台并暂停执行时，使用`bg`(background)命令来继续运行后台进程，相当于向进程发送了一个继续在后台运行的信号
`bg %加上我想引用的特定进程`
```shell
$ bg %1             // 继续第一个任务
```
与之对应的是`fg`(foreground)，使用`fg`将进程恢复到前台继续运行



### jobs
查看后台进程

### kill
`kill`命令用于终止指定的进程(terminate a process)的运行，`-HUP`代表`hang up挂起`，
![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/1d0863a9a15e4a569973300efbc4f089~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=569&h=200&s=17661&e=png&b=000000)
```shell
$ kill -KILL %3      // 强制杀死第三个进程
```

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/7279e9feea34476b9a8448fd47ceb4dd~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=545&h=158&s=14600&e=png&b=000000)

### tmux
Session
window
pane

Ctrl+A p(previous上一窗口)
Ctrl+A n(next 下一窗口)
Ctrl+A "(将命令行水平分为两个面板)
Ctrl+A %(将命令行垂直分为两个面板)

### dotfiles

`-ls -la`：ls-la：查看所有文件（包含了隐藏文件）

`ls -lah`：查看所有文件以及文件大小（包含隐含文件）

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/3703e011f9474d65aa4a003f1cbd3333~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=648&h=359&s=52229&e=png&b=000000)
#### `alias`别名
随着你构建越来越长的命令，反复输入他们会变得有些麻烦，别名`alias`在这种情况就变得特别方便，它可以映射长命令为一个短的字符串。`注意：别名只接受一个参数，所以不要在等号旁边输入空格`
```shell
$ alias ll="ls -lah"         // 将命令“ls -lah”设置别名为“ll”
$ ll
total 119K
drwxr-xr-x 1 alexis 197609    0 Sep 14 20:31 ./
drwxr-xr-x 1 alexis 197609    0 Sep 15 09:09 ../
drwxr-xr-x 1 alexis 197609    0 Sep 11 11:11 .git/
-rw-r--r-- 1 alexis 197609 4.0K Sep 11 13:42 .mcd.sh.swp
-rw-r--r-- 1 alexis 197609   13 Sep 11 11:02 add-me
-rw-r--r-- 1 alexis 197609   16 Sep 11 11:01 change-me
```

### remote machine远程服务器
#### ssh连接远程服务器
由于每次使用ssh让远程服务器执行命令都需要输入密码，非常不方便，因此我们可以通过`ssh密钥`来解决这个问题

ssh密钥使用非对称加密创建一对ssh密钥，一个公钥，一个私钥，你可以把公钥交给服务器，并使用私钥证明自己的身份，这样一来就不用每次都输入密码了

#### 创建ssh密钥对
```shell
ssh-keygen -0 -a 100 -t ed25519     // 也可以使用ssh-keygen -t rsa
```
`-t ed25519`表示使用ed25519算法生成密钥对（Ed25519 的安全性在 RSA 2048 与 RSA 4096 之间，且性能在数十倍以上。）

## Lecture6 版本控制系统
版本控制系统是用于跟踪源代码或其他文件/文件夹更改记录的工具，这些版本控制工具可以帮忙跟踪文件的更改历史，除此之外，他们还可以多人协作，所以它们在多人开发中非常有用

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/a82011df05444168817af6c7e38bda1a~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=809&h=1181&s=576545&e=png&b=fbfbf9)

some ugly interface you have to memorize

git快照-状态（动态）

git commit就是一次快照，就会上传一次动态

每个动态都有一个SHA-1哈希值

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/aa8162fa0b954015b621cd7b9fab4da5~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=653&h=116&s=15225&e=png&b=000000)
这个哈希值对应一个提交，而每个提交内部包含树的哈希值和一些其他信息，我们可以用`git cat-file -p 9d3aade`来查看这个提交内部的信息
![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/2df4c3d5fc7f46ed8f6e82242000a7d2~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=662&h=161&s=20595&e=png&b=000000)
查看树(tree)的哈希值
![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/92c0bf16078d4071867e21bf1600dde4~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=740&h=81&s=14567&e=png&b=000000)
查看文件(blog)的哈希值

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/e9d68a96e0984d0099d47359b38c02e8~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=659&h=80&s=10923&e=png&b=000000)


### git log可视化历史提交信息


![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/86b475b78d8c4028909bb9128ecbe8df~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=716&h=164&s=19129&e=png&b=000000)

为什么我必须使用`git add`，为什么不能直接提交所有更改

其实有一种方法可以提交所有更改`git commit -a`，这会提交所有git跟踪了的文件的更改，但不会提交新文件（因为新文件没有被git跟踪）

因为你不总是希望快照中包含所有内容：我可能正在做我的项目，然后实现了两个功能，但是我不想在一次快照中展示“我实现了功能A和B”，也许我想在历史记录中创建两个单独的节点，看起来像是我先在前节点完成了A，然后在这个节点的基础上完成的B

而`git add`的暂存区(Stage area)可以让我完成这样的事，它可以指定只添加某个文件的修改，然后我可以提交它，创建快照

`以图形结构展示git提交历史记录`
```bash
git log --all --graph --decorate
```

添加新节点
```bash
$ echo "another line" >> hello.txt
$ cat hello.txt
$ git add hello.txt
$ git commit -m "add another line"
$ git log --all --graph --decorate
```

### git checkout 
切换当前节点到你想到的节点
```shell
$ git checkout 
```

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/08950b89efd64d7bb1e0b9847884d01b~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=647&h=68&s=9845&e=png&b=000000)

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/2216c4d36fb6470b8cc85e1bc762b2a1~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=708&h=75&s=8549&e=png&b=000000)
我们可以用`git log`看到当前HEAD指向的位置也变了

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/8527f28ef4634c7599d4c2c77a2cb116~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=716&h=281&s=32399&e=png&b=000000)

git checkout移动了HEAD指针，根据HEAD指针改变你当前的工作节点，因此如果误用了它会有点危险。假如我修改了`hello.txt`且还未提交快照，这个时候如果我git checkout 换到其他节点的话会报错，但如果我使用`git checkout -f 9d3aade`强制更换工作节点的话，我之前所做的修改都会被丢弃

```shell
git checkout hello.txt
```
这会直接丢弃对hello.txt修改的内容，并将hello.txt的内容设置回HEAD指向的快照的状态

### git diff

![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/d0394b720f0b4c4f97d3d8e6a9f78894~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=879&h=321&s=35451&e=png&b=000000)
也可以与指定节点进行对比，这里与第一个节点`9d3aade`进行对比，如果不指定节点的话，将会与HEAD指针指向的节点做对比

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/4da1d4d7cb9642f7a0c72072a1ea793f~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=881&h=257&s=27349&e=png&b=000000)

### git branch
git branch 命令用于访问分支，仅运行`git branch`会列出本地仓库中存在的所有分支
```shell
$ git branch cat      // 创建新分支cat
```
这个时候再执行`git branch cat`命令，会切换到cat分支，工作目录的内容会替换为cat所指向的内容

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/64caebde693e4e1cb931b414ea159041~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=813&h=399&s=44623&e=png&b=000000)

如果这个时候对工作目录进行修改并进行新提交快照，cat分支指针将被更新并指向新快照，而master分支将呆在原地

git checkout -b dog

创建新分支dog并且切换到该分支

git仓库就是历史的完整副本

git push origin master:master

![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/b706e9569774471a92af7f0abde4325f~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=881&h=155&s=20839&e=png&b=000000)

git push每次都要输入一长串，但是设置了这个配置，可以告诉git本地仓库分支对应的远程仓库的分支
git --set-upstream-to="origin/master"

将本地仓库的master分支对应远程仓库origin的master分支

git pull = git fetch + git merge

#### `.gitignore文件`
不提交的文件列表

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/9260f06370174ffe8a304f7f79078633~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=657&h=83&s=11459&e=png&b=000000)

这个时候输入`git branch -vv`可以查看本地仓库分支的详细信息

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/bf6617f5416a476da3729488b6745b10~tplv-k3u1fbpfcp-jj-mark:0:0:0:0:q75.image#?w=666&h=99&s=12848&e=png&b=000000)