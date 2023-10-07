### 1. Git 初始化

```
git config --global user.name Sakura0213
git config --global user.email zengxin@email.cn
ssh-keygen -t rsa -C "zengxin@email.cn"
cat ~/.ssh/id_rsa.pub
```

### 2. 仓库初始化

```bash
git init
git add .
git commit -m "first book" 
git remote add origin https://github.com/zengxin0213/OCQDocument.git
git push -u origin master
```

### 3. 添加提交推送

```
git add .
git commit -m "zx" 
git push -u origin master
```
