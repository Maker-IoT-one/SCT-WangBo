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
   - git clone 仓库地址
   - git clone https://github.com/Maker-IoT-one/SCT-WangBo.git
2. 推送到云端仓库
   - git push origin main

## 一些报错的解决方法
1. port 443，Couldn't connect to server
   - 出现的场景：
      - 执行`git push origin main` 进行提交时
   - 出现的原因：  
      - git在拉取或者提交项目时，中间会有git的http和https代理，但是我们本地环境本身就有SSL协议了，所以取消git的https代理即可，不行再取消http的代理。
   - 解决方法：  
      1. 科学上网
      2. 终端执行
         - git config --global --unset http.proxy 
         - git config --global --unset https.proxy

# 2023.12.22Maker Studio

版本控制工具

