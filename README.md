# net-lab：计算机网络协议栈实验框架

实验指导书：<https://comp-network.p.cs-lab.top/>

本仓库用于逐步实现 Ethernet、ARP、IP、ICMP、UDP、TCP 和 HTTP。开发环境、协议实现要求、测试方法及提交与自检流程请参考实验指导书。

## 保存实验进度与同步课程更新

本仓库保留课程仓库的提交历史和 `net-lab-base` 标签，配置了两个远程仓库：

- `origin`：个人 GitHub 仓库 <https://github.com/CuO114/net-lab>，用于保存实验进度。
- `upstream`：课程仓库 <https://git.cs-lab.top/cslab/net-lab.git>，用于获取课程更新。

### 保存实验进度

在项目目录中执行，先通过 `git status` 核对需要保存的文件：

```sh
git status
git add -A
git commit -m "完成本次实验内容"
git push
```

`main` 跟踪个人仓库的 `origin/main`，默认推送到个人 GitHub。

### 同步课程更新

先提交当前实验修改，确保 `git status` 显示工作区干净，再执行：

```sh
git fetch upstream
git merge upstream/main
git push
```

合并会保留自己的实验提交和课程更新。若出现冲突，编辑 Git 标出的文件，保留需要的内容并删除冲突标记，然后执行 `git add <已解决的文件>` 和 `git commit`，最后 `git push`。要取消本次合并，可在合并尚未完成时执行 `git merge --abort`。

### 换电脑后恢复配置

远程仓库配置不会随代码克隆，换电脑时执行：

```sh
git clone https://github.com/CuO114/net-lab.git
cd net-lab
git remote add upstream https://git.cs-lab.top/cslab/net-lab.git
git config remote.pushDefault origin
git config branch.main.pushRemote origin
git config pull.ff only
git fetch upstream
```

克隆或推送私有仓库前，需要登录有访问权限的 GitHub 账号。课程初始版本标签缺失时，可以执行 `git fetch upstream tag net-lab-base`。
