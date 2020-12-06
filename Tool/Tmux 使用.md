# Tmux 使用

tmux是一个 Terminal Multiplexer（终端复用器），它可以启动一系列终端会话。

安装

```bash
# Ubuntu 或 Debian
$ sudo apt-get install tmux

# CentOS 或 Fedora
$ sudo yum install tmux

# Mac
$ brew install tmux
```

### 名词

- session

-  window

- pane

### 启动

```
tmux
```

```
tmux new -s <session-name>
```

### 退出

```
exit
```

```
tmux detach
```



## 前缀+快捷键

Tmux 窗口有大量的快捷键。所有快捷键都要通过前缀键唤起。默认的前缀键是`Ctrl+b`，即先按下`Ctrl+b`，快捷键才会生效。

举例来说，帮助命令的快捷键是`Ctrl+b ?`。它的用法是，在 Tmux 窗口中，先按下`Ctrl+b`，再按下`?`，就会显示帮助信息。

然后，按下 ESC 键或`q`键，就可以退出帮助。

```bash
# ——————  session
# 查看当前所有的 Tmux 会话
tmux ls
# 重新接入某个已存在的会话
tmux attach -t <session-No>
tmux attach -t <session-name>
# kill某个会话
tmux kill-session -t <session-No>
tmux kill-session -t <session-name>
# 使用会话编号
$ tmux switch -t 0
# 使用会话名称
$ tmux switch -t <session-name>
# 重命名会话名
tmux rename-session -t 0 <new-name>



# ——————  window 
$ tmux new-window
# 新建一个指定名称的窗口
$ tmux new-window -n <window-name>
# 切换到指定编号的窗口
$ tmux select-window -t <window-number>
# 切换到指定名称的窗口
$ tmux select-window -t <window-name>
# 重命名窗口
tmux rename-window <new-name>


# ——————  pane 
# 划分上下两个窗格
$ tmux split-window
# 划分左右两个窗格
$ tmux split-window -h
#####################
# 开启鼠标模式就不需要了#
####################
# 光标切换到上方窗格
$ tmux select-pane -U
# 光标切换到下方窗格
$ tmux select-pane -D
# 光标切换到左边窗格
$ tmux select-pane -L
# 光标切换到右边窗格
$ tmux select-pane -R
#####################

# 重载配置
$ tmux source-file ~/.tmux.conf
```



Tip 按下快捷键前缀然后再按快捷键

### 窗格操作 pane

- `%` 左右平分出两个窗格
- `"` 上下平分出两个窗格
- `x` 关闭当前窗格
- `{` 当前窗格前移
- `}` 当前窗格后移
- `;` 选择上次使用的窗格
- `o` 选择下一个窗格，也可以使用上下左右方向键来选择
- `space` 切换窗格布局，tmux 内置了五种窗格布局，也可以通过 `⌥1` 至 `⌥5`来切换
- `z` 最大化当前窗格，再次执行可恢复原来大小
- `q` 显示所有窗格的序号，在序号出现期间按下对应的数字，即可跳转至对应的窗格

### 窗口操作 window

tmux 除了窗格以外，还有窗口（window） 的概念。依次使用以下快捷键来熟悉 tmux 的窗口操作：

- `c` 新建窗口，此时当前窗口会切换至新窗口，不影响原有窗口的状态
- `p` 切换至上一窗口
- `n` 切换至下一窗口
- `w` 窗口列表选择，注意 macOS 下使用 `⌃p` 和 `⌃n` 进行上下选择
- `&` 关闭当前窗口
- `,` 重命名窗口，可以使用中文，重命名后能在 tmux 状态栏更快速的识别窗口 id
- `0` 切换至 0 号窗口，使用其他数字 id 切换至对应窗口
- `f` 根据窗口名搜索选择窗口，可模糊匹配



#### 参考

[阮一峰 教程](https://www.ruanyifeng.com/blog/2019/10/tmux.html)

