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
> ```
> 2. 通过命令将文件夹下所有文件信息添加到索引库的暂存区，然后提交到本地仓库
> ```
> $ git add -A #提交到暂存区
> $ git commit #提交到仓库
> ```
> 3. 把本地仓库内容推送到github中
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