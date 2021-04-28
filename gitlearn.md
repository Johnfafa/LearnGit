### git学习笔记

##### 一. 初始化git

> 1. git下载地址 http://git-scm.com/downloads
> 2. 修改Git Bash主目录
>
>> ```
>> $ pwd #显示当前所在的目录路径
>> ```
>> <kbd>我的电脑</kbd>-><kbd>属性</kbd>-><kbd>高级系统设置</kbd>-><kbd>环境变量</kbd>->新建<i>（key:Home,value:你想要的迁移到的目录地址）</i>
>> 如果你之前的C:\Users\用户名路径下已经生成了.ssh、.gnupg、.bash_history、.gitconfig等文件，直接把这些文件拷贝到你新设定的用户主目录下即可
>
> 3. 配置用户的个人信息(Git Bash)
>
>> ```
>> $ git config --global user.name "fafa"
>> $ git config --global user.email test@fafa.com
>> ```

##### 二. 在本地电脑创建SSH Key

> 1. 本地生成SSH key，一路回车操作完后，.ssh文件夹内会生成两个文件:id_rsa_git和id_rsa_git.pub
> ```
> $ mkdir .ssh
> $ cd .ssh
> $ ssh-keygen -t rsa -C "xxx@qq.com" #如果有.ssh文件夹可以省略前面两步
> ```
>> 参数含义：
>> -t ：指密钥类型（加密方式），默认是 rsa ，可以省略
>> -C ：设置公钥文件中的备注，比如邮箱或其他注释性文字均可
>> -f ：指定密钥文件存储文件名，默认是id_rsa，可以使用其他文件名
> 2. 在你的github中添加生成的ssh的key
> <kbd>Settings</kbd>-><kbd>SSH and GPG keys</kbd>
> 将id_rsa_git.pub中的内容添加到github中

##### 三、在本地电脑新建版本仓库，然后把内容推送到GitHub仓库

> 1. 初始化本地仓库，在目录下新建一个learngit文件夹
> ```
> $ mkdir learngit
> $ cd learngit
> $ git init
> # git init newfolder #制定初始化仓库的目录
> ```
> 2. 通过命令将文件夹下所有文件信息添加到索引库的暂存区，然后提交到本地仓库
> ```
> $ git add -A #提交到暂存区
> $ git commit -m "注释，没有注释不允许提交" #提交到仓库
> ```
> 3. 把本地仓库内容推送到github中，将本地的master分支推送到origin主机，同时指定origin为默认主机，后面就可以不加任何参数使用git push了
> 1> 在你的github中新建仓库<kbd>New repository</kbd>
> 2> 将新建的仓库ssh链接拷贝好
> ```
> $ git remote add origin git@github.com:Johnfafa/LearnGit.git
> $ git push -u origin master
> ```
> 如果提示已存在remote origin already exists，可以直接push或者删除origin后继续重复2>步骤
> ```
> $ git remote rm origin
> ```

##### 四、git的一些命令应用

> |  命令   | 说明  |
> |  ----  | ----  |
> |<b>创建仓库命令</b>| |
> | git init  | 初始化仓库 |
> | git clone  | 拷贝一份远程仓库，也就是下载一个项目 |
> |<b>提交与修改</b>||
> | git add  | 添加文件到仓库 |
> | git status  | 查看仓库当前的状态，显示有变更的文件 |
> | git diff  | 比较文件的不同，暂存区和工作区的差异 |
> | git commit  | 提交暂存区到本地仓库 |
> | git reset  | 回退版本 |
> | git rm  | 删除工作区文件 |
> | git mv  | 移动或重命名工作区文件夹 |
> |<b>日志</b> ||
> | git log  | 查看历史提交记录 |
> | git mv  | 以列表形式查看指定文件的历史修改记录 |
> | <b>远程操作</b>  | |
> | git remote  | 远程仓库操作 |
> | git fetch  | 从远程获取代码库 |
> | git pull  | 下载远程代码并合并 |
> | git push  | 上传远程代码并合并 |
> | git ls-files | 查看所有文件 |
> 
>
> ```
> $ git rm 文件名称 #删除指定文件
> $ git rm -r 文件夹名称 #删除指定文件夹
> $ git rm –r * #删除该目录下所有文件和子目录
> ```


#### 五、git分支管理

> ```
> $ git branch #列出分支列表
> $ git branch branchname #创建分支
> $ git branch -d branchname #删除分支
> $ git checkout branchname #切换分支
> $ git checkout -b branchname #创建新分支并切换到该分支下
> $ git merge #合并分支
> ```