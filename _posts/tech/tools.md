Win 窗口切换快捷键最优解
https://zhuanlan.zhihu.com/p/128744443

打开 IDEA 软件，并点击顶部菜单栏的"File"（文件）选项。 2. 在下拉菜单中，选择"Settings"（设置）。 3. 在弹出的设置窗口中，选择"Plugins"（插件）选项。 4. 在插件列表中，点击" Mark e tplace "（插件市场）选项。


WSL2的说明:2020年夏季更新的Windows包含一个名为WSL2的Linux内核。

关于使用Git出现“git Failed to connect to 127.0.0.1 port xxxx: Connection refused”的问题解决方案
https://blog.csdn.net/XH_jing/article/details/115095225

https://wenku.csdn.net/answer/77c9a4cf216d4d7c882e5004ef9185c9#:~:text=git%20bash%E6%80%8E%E4%B9%88%E5%88%87%E6%8D%A2%E8%B7%AF%E5%BE%84%201%20%E6%89%93%E5%BC%80%20Git%20Bash%20%E7%BB%88%E7%AB%AF%EF%BC%9B%202,%E4%BD%BF%E7%94%A8%20cd%20%E5%91%BD%E4%BB%A4%E5%8A%A0%E4%B8%8A%E8%A6%81%E5%88%87%E6%8D%A2%E7%9A%84%E8%B7%AF%E5%BE%84%EF%BC%8C%E4%BE%8B%E5%A6%82%EF%BC%9A%20cd%20%2Fc%2FUsers%2Fusername%2FDocuments%20%EF%BC%9B%203%20%E6%8C%89%E4%B8%8B%E5%9B%9E%E8%BD%A6%E9%94%AE%EF%BC%8C%E5%8D%B3%E5%8F%AF%E5%88%87%E6%8D%A2%E5%88%B0%E6%8C%87%E5%AE%9A%E7%9A%84%E8%B7%AF%E5%BE%84%E3%80%82


git remote add skeleton https://github.com/Berkeley-CS61B/skeleton-sp21.git

这个命令的作用是将 Berkeley CS61B 的 2021 年春季学期的框架代码仓库添加到你的本地 Git 仓库中作为一个远程仓库，以便于你可以从这个远程仓库拉取（git pull）或推送（git push）代码。

当你运行 `git remote add` 命令后，你实际上只是在本地 Git 仓库中添加了一个远程仓库的引用。这个操作本身不会改变你本地仓库中的文件或代码。要查看远程仓库中的内容，你需要执行额外的 Git 命令。以下是一些常见的操作：

1. **查看远程仓库列表**：
   - 运行 `git remote -v`。这将列出你的本地仓库中所有配置的远程仓库及其 URL。

2. **从远程仓库拉取代码**：
   - 使用 `git fetch skeleton`（如果你添加的远程仓库名称是 `skeleton`）。这个命令会从远程仓库下载新的数据（包括所有的分支和代码），但不会自动合并到你的当前工作。
   - 然后，你可以使用 `git merge skeleton/main`（假设你想合并 `main` 分支）来将远程仓库的更改合并到你的本地仓库。

3. **克隆远程仓库**：
   - 如果你还没有克隆仓库，可以使用 `git clone https://github.com/Berkeley-CS61B/skeleton-sp21.git` 来克隆整个仓库到你的本地计算机。

4. **查看分支**：
   - 运行 `git branch -a` 可以查看包括远程分支在内的所有分支。远程分支通常会以 `remotes/` 开头。

记住，只有当你执行了 `fetch`, `pull`, 或 `clone` 等操作后，远程仓库的内容才会出现在你的本地文件系统中。在此之前，`git remote add` 只是建立了一个可以访问远程仓库的链接。