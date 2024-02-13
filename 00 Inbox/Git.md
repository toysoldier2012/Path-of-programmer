**. gitignore 只能忽略未被 track 的文件，**而 git 本地缓存。**如果某些文件已经被纳入了版本管理中，则修改. gitignore 是无效的**
git rm -r --cached .
git add .
git commit -m 'update .gitignore'