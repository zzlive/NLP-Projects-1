# NLP-Projects
This is the NLP projects for HKU MFin course.

# Initializing GitHub Repo
1. 在GitHub上建立库
    先在GitHub上创建一个库(Repo)或者fork别人的库(Repo)
    假设这个库的地址是：`user_name/repo_name`

1. 设置本地的连接（每台电脑仅需设置一次）
    在Bash中运行`ssh-keygen -t rsa -C "yourmail@email.com"`
    打开`.\.ssh\id_rsa.pub`文件，拷贝内容，粘贴在[GitHub SSH & GPG keys](https://github.com/settings/ssh/new)，即可添加SSH key。

1. 设置账号信息
    在Bash中运行：
    ```
    git config --global user.name "yourname"
    git config --global user.email "yourmail@email.com"
    ```
    在[GitHub Account Admin](https://github.com/settings/tokens)中创建好自己的API token。继续Bash：
    ```
    git config --global github.user "your_github_id"
    git config --global github.token your_API_token
    ```

1. 在本地创建Git库
    ```
    mkdir test_repo
    cd test_repo
    git init
    ```

1. 将远程库关联至本地库
    ```
    git remote add origin git@github.com:user_name/repo_name
    ```

# 使用GitHub
1. Pull
    保持良好习惯，每次先将最新的库同步到本地
    ```
    git pull origin master
    ```

1. 提交到暂存区
    ```
    git add some_file.py
    ```

1. 提交到工作区
    ```
    git commit some_file.py -m "some_comment"
    ```
    好像不能不commit就push

1. 提交到远程库
    ```
    git push -u origin master
    ```
