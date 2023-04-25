# 学习Git

命令中使用[]括起来的都是需要根据自己的实际情况更改的。

#### 安装git

可以试一下非安装版

#### 创建本地用户

在本地创建一个用户，如果名字中间有空格，需要使用英文双引号。

```bash
git config --global user.name Trump

git config --global user.email Trump@gmail.com
```

#### 提高命令输出的可读性

```bash
git config --global color.ui auto
```

#### 初始化

将一个普通文件夹交给git管理，会生成一个.git文件夹

先cd到相应的目录

```bash
git init
```

#### clone

克隆一个项目

```bash
git clone https://github.com/Water-blue7/test.git
```

```bash
git clone git@github.com:Water-blue7/test.git
```

#### status

查看当前工作状态

```bash
git status
```

#### add

git不知道需要管理哪些文件，提交到暂存区的文件才是git真正要管理的文件。

##### 将指定文件加入到暂存区

```bash
git add [filename]
```

##### 将所有文件加入到暂存区

```bash
git add .
```

#### commit

##### 将暂存区中的文件提交到本地git中

```bash
git commit -m "备注"
```

##### 使用参数-a可以省略add，-a -m=-am

```bash
git commit -a -m "备注"
```

#### push

将本地git中的内容push到github中——远程仓库。

##### push到与所在分支同名的远程分支

```bash
git push
```

##### push到指定名称的远程分支

```bash
git push origin [remote_branch_name]
```

##### 将本地某分支push到远程某分支

```bash
git push origin [local_branch_name]:[remote_branch_name]
```

#### fetch

远程分支同步到本地

当 git fetch 命令从服务器上抓取本地没有的数据时，它并不会修改工作目录中的内容。它只会获取数据然后让你自己合并。

```bash
git fetch origin [branch_name]
```

手动合并

```bash
git merge FETCH_HEAD
```

#### pull

由于 git pull 的魔法经常令人困惑所以通常单独显式地使用 fetch 与 merge 命令会更好一些。

git pull = git fetch + git merge

##### 将与本地当前分支同名的远程分支 拉取到 本地当前分支上

```bash
git pull
```

##### 将远程指定分支 拉取到 本地当前分支上

```bash
git pull origin [remote_branch_name]
```

##### 将远程指定分支 拉取到 本地指定的分支上

```bash
git pull origin [remote_branch_name]:[local_branch_name]
```

#### 分支

##### 创建分支

```bash
git branch [new_branch_name]
```

##### 切换分支

```bash
git checkout [branch_name]
```

##### 切换到远程分支

```bash
git checkout origin/[branch_name]
```

##### 创建并切换分支

```bash
git checkout -b [new_branch_name]
```

##### 删除本地分支

```bash
git branch -d [branch_Name]
# 强制删除 -D
git branch -D [branch_Name]
```

##### 删除远程分支

```bash
git push origin --delete [branch_name]
```

##### 删除远程跟踪分支

```bash
git branch -dr origin/[branch]
```

意思就是将当前分支与远程分支解除关系，如果再次git push当前分支由于找不到跟踪的远程分支会提示git push --set-upstream origin [branch_name] 意思就是将当前分支与远程的某个分支建立跟踪关系，有三种方法。

```bash
git push --set-upstream origin [branch_name]
```

或者

```bash
git push origin [local_branch_name]:[remote_branch_name]
```

或者

```bash
git push origin [remote_branch_name]
```

##### 合并分支

将指定分支合并到当前分支

```bash
git merge [branch_name]
```

如果两个分支有冲突——两个分支都对同一文件进行了修改，分支名称变为(branch_name|MERGING)，git不知道你需要哪个版本，所以这时候就需要手动去打开冲突文件分析需要保留哪个版本，把不需要的内容删掉后再commit。

#### 远程仓库重命名与移除

将 pb 重命名为 paul

```bash
git remote rename [pb] [paul]
```

删除跑路

```bash
git remote remove [paul]
```

#### 删除本地仓库

```bash
# 先删除.git文件夹
rm -rf .git

cd ..
rm -rf [rep_name]
```
