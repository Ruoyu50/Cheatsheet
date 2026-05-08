# Git Cheatsheet

## 一、初始化与删除仓库

```bash
git init
```

初始化本地仓库

```bash
rm -rf .git
```

删除本地仓库（彻底清空版本控制）

```bash
rm -rf Terminal/.git
```

删除子目录里的 Git 仓库

```bash
rm -rf docs && npx @11ty/eleventy
```

删除 Eleventy 网页 output 的历史文件

```bash
git config advice.forceDeleteBranch false
```

```bash
git config --global init.defaultBranch <name>
```

设置默认初始分支名

```bash
git branch -m <name>
```

重命名当前分支

---

## 二、分支管理

```bash
git branch
```

查看本地分支

```bash
git branch -r
```

查看远程分支

```bash
git branch <name>
```

创建新分支

```bash
git branch -d <name>
```

删除已合并的本地分支

```bash
git branch -D <name>
```

强制删除本地分支

```bash
git checkout <branch>
```

切换到分支

```bash
git checkout <branch> -- .
```

目标分支覆盖当前分支

```bash
git checkout <commitID>
```

切换到特定提交（分离 HEAD）

```bash
git checkout -b <new-branch>
```

创建并切换到新分支

```bash
git checkout -b <new-branch> <commitID>
```

从指定 commit 创建分支

```bash
git checkout --orphan <branchName>
```

创建孤儿分支（无历史）

---

## 三、查看仓库状态

```bash
git status
```

查看当前仓库状态

```bash
git log --oneline
```

压缩形式查看提交历史

```bash
git log --oneline --all --graph --decorate
```

带分支结构的图形化提交历史

```bash
git reflog
```

查看 HEAD 和分支的移动历史（包括 reset、checkout 等操作）

```bash
git ls-files
```

查看 Git 跟踪的文件

```bash
git diff
```

查看工作区未暂存的修改

```bash
git diff <commitA> <commitB>
```

比较两个 commit 的差异

```bash
git diff <branchA> <branchB>
```

比较两个分支的差异

---

## 四、暂存与提交

```bash
git add .
```

添加所有修改（新文件 / 改动 / 删除）到暂存区

```bash
git add <file>
```

添加指定文件到暂存区

```bash
git rm <file>
```

删除文件并记录到暂存区

```bash
git rm -rf .
```

删除所有文件

```bash
git commit -m "message"
```

提交暂存区内容，所在 branch(main) 指针前进到新 commit

```bash
git commit -a -m "message"
```

跳过 git add，直接提交已修改过的文件（不包含新文件）

---

## 五、回退与修改历史

```bash
git reset --soft <commitID>
```

软回退，保留暂存区修改

```bash
git reset --mixed <commitID>
```

默认回退，保留工作区修改，清空暂存区

```bash
git reset --hard <commitID>
```

硬回退，丢弃工作区和暂存区修改

```bash
git checkout <commitID>
```

游离 HEAD 到某个 commit（不修改分支指针）

```bash
git rebase <branch>
```

将当前分支的提交移到目标分支最后

```bash
git diff <commitA> <commitB>
```

比较两个 commit 的差异

---

## 六、远程仓库操作

```bash
git remote -v
```

查看远程地址

```bash
git remote add origin <url>
```

添加远程仓库

```bash
git remote set-url origin <url>
```

修改远程仓库地址

```bash
git push -u origin main
```

首次推送并绑定分支

```bash
git push
```

推送到已绑定的远程分支

```bash
git push origin <branch>
```

推送指定分支到远程

```bash
git push -f origin main
```

强制推送，覆盖远程 main

```bash
git push -f origin <local>:<remote>
```

强制推送，本地分支覆盖远程目标分支

```bash
git push origin --delete <branch>
```

远程删除已 push 的分支

```bash
git pull origin main --rebase
```

拉取远程最新代码并 rebase

```bash
git pull
```

拉取远程最新代码并合并

### 远程强制覆盖本地

```bash
git fetch origin
git reset --hard origin/main
```

---

## 七、子模块 / 嵌套仓库

```bash
git rm --cached Terminal
```

移除误加的子仓库

---

## 八、清理与维护

```bash
git gc
```

垃圾回收，清理未引用的提交或对象

```bash
git config --global pager.branch false
```

关闭分支分页显示

```bash
git config --global pager.reflog false
```

关闭 reflog 分页显示

---

## 九、Commit Message 常见前缀

| 前缀       | 意义      |
| -------- | ------- |
| feat     | 新功能     |
| fix      | 修 bug   |
| refactor | 重构      |
| docs     | 文档      |
| style    | 格式      |
| test     | 测试      |
| chore    | 杂项 / 维护 |

示例：

```bash
git commit -m "chore: ignore .DS_Store"
```
