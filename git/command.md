# 1 强制推送代码到多个远程仓库

```
git push -f origin master 注释： origin 远程仓库名， master 分支名， -f 为force，意为：强行、强制。
```
# git bach 保存密码

```
echo "[credential]" >> .git/config     
echo "    helper = store" >> .git/config  
```

### 切换分支

```
git checkout 分支
```

### 合并分支

```
git merge dev

```
合并dev 到当前分支
### 创建新项目

>Create a new repository

```
git clone http://git.ztosys.com/houwenlong/test.git
cd test
touch README.md
git add README.md
git commit -m "add README"
git push -u origin master
```
>Existing folder
```
cd existing_folder
git init
git remote add origin http://git.ztosys.com/houwenlong/test.git
git add .
git commit -m "Initial commit"
git push -u origin master
```
>Existing Git repository
```
cd existing_repo
git remote add origin http://git.ztosys.com/houwenlong/test.git
git push -u origin --all
git push -u origin --tags
```