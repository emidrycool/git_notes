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
   git remote add origin https://github.com/test/Demo.git
   ```

5. 推送：把本地仓库的代码推送到远程仓库Github上

   ```sh
   git push (-u) origin master
   ```

常见错误：新建远程仓库的时候勾选Initialize this repository with a README，推送时可能会报failed to push some refs to https://github.com/test/Demo.git的错

解决方案：这是由于你新创建的那个仓库里面的README文件不在本地仓库目录中，这时可以同步内容。

```sh
# 从远程仓库获取最新的更改，并将这些更改应用到你当前的分支上
git pull --rebase origin master

# 然后再进行
git push origin master
```

## Undo Commit，Revert Commit，Drop Commit区别

**Undo Commit**

适用情况：代码修改完了，已经Commit了，但是还未push，然后发现还有地方需要修改，但是又不想增加一个新的Commit记录。这时可以进行Undo Commit，修改后再重新Commit。

**Revert Commit**

会新建一个 Revert “xxx Commit”的Commit记录，该记录进行的操作是将"xxx Commit"中对代码进行的修改全部撤销掉。

**Drop Commit（慎用）**

未push的Commit记录：会删除Commit记录，同时Commit中对代码进行的修改也会全部被删除

已push的Commit记录：区别在于线上的Commit记录不会被删除
