# git学习笔记

## 将本地代码提交到远程仓库的常用步骤

1. 初始化：本地建库（即文件夹）

   ```sh
   git init
   ```

2. 添加到仓库：代码文件放入本地库

   ```sh
   git add .
   ```

3. 提交： 提交到本地仓库

   ```sh
   git commit -m "注释内容"
   ```

4. 关联远程仓库：新建一个远程仓库， 使用下面指令进行关联

   ```sh
   git remote add origin https://github.com/xu-xiaoya/Elegent.git
   ```

5. 推送：把本地仓库的代码推送到远程仓库Github上

   ```sh
   git push (-u) origin master
   ```

常见错误：新建远程仓库的时候勾选Initialize this repository with a README，推送时可能会报failed to push some refs to https://github.com/test_name/Demo.git的错

解决方案：这是由于你新创建的那个仓库里面的README文件不在本地仓库目录中，这时可以同步内容。

```sh
# 从远程仓库获取最新的更改，并将这些更改应用到你当前的分支上
git pull --rebase origin master

# 然后再进行
git push origin master
```

