# 学习Git

学习使用git

1. 安装git（可以试一下非安装版）

2. 在本地创建一个用户，如果名字中间有空格，需要使用英文双引号。

    ```bash
    git config --global user.name Trump
    
    git config --global user.email Trump@gmail.com
    ```

3. 提高命令输出的可读性

    ```bash
    git config --global color.ui auto
    ```

4. 初始化，将普通文件夹/文件加载到git中管理。

    ```bash
    # 先cd到相应的目录
    git init
    ```

5. 暂存区

    ```bash
    git add filename
    
    #或者将所有文件加入到暂存区
    git add .
    ```

6. commit：将更改提交到本地的git中

    ```bash
    git commit -m "本次更改内容"
    
    # 使用参数-a可以省略上一步add
    git commit -a -m "本次更改内容"
    ```

7. push：将本地git中的内容上传到github中

    ```bash
    git push
    ```

    

```bash
# 查看当前工作状态
git status

# 创建新的分支
git branch new_branch_name

# 切换分支
git checkout branch_name

# 创建并切换到新的分支
git checkout -b new_branch_name

# 删除分支
git branch -D branch_name

# 将指定分支合并到当前（正在打开的）分支，下面就是将branch_name分支合并到master分支
git checkout master
git merge branch_name

# clone 用ssh的链接clone，修改后可以不用登陆github就push，因为设置了SSH Key
git clone git@github.com:Water-blue7/test.git
```

