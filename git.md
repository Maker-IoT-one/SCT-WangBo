# git&github教学

## 前置准备工作

>官网下载：Git：https://git-scm.com/download/win  
>注册登录github账号，创建代码仓  
> 示例代码仓位置：https://github.com/Maker-IoT-one/SCT-WangBo/tree/main

## git部分
1. 绑定用户和邮箱（复制粘贴可能存在中英文问题）  
   - git config --global user.email "you@example.com"  
   - git config --global user.name "Your Name"
2. 本地创建仓库
   - 选择创建仓库的文件夹
   - 在该文件夹执行git init
3. 将所有修改提交到暂存区
   - git add . 
4. 将所有修改提交到git仓库
   - git commit -m "xxx"
5. 查看提交日志（查看commit id）
   - git log  
   - git log --stat
6. git回溯
   - git reset --hard[commit id]
   - git checkout [commit id]
7. 查看当前分支
   - git branch
   - master分支为默认分支
8. 创建并使用分支
   - git branch
   - git checkout to a new branch '分支的 commit id'
9. 合并分支
   - 先提交到暂存区和仓库
   - 执行命令：git checkout master 切换到master分支
   - 执行合并：git merge 分支名
## github部分
1. 拉取仓库到本地
   - git clone https://github.com/Maker-IoT-one/SCT-WangBo.git
2. 推送到云端仓库
   - git push origin main
3. 待补充报错等其他内容