# Tmux 使用

Tip 按下快捷键前缀然后再按快捷键



新建会话

`tmux new -s <session name>`

分离会话

`tmux detach`

接入会话

`tmux attach -t <session name>`

杀死会话

`tmux kill-session -t <session name>`

切换会话

`tmux switch -t <session name>`

重命名会话

`tmux rename-session -t <session-id> <new name>`

重载配置

`tmux source-file ~/.tmux.conf`

![](https://raw.githubusercontent.com/Jabari-z/PicGoRepo/master/img/%E6%88%AA%E5%B1%8F2020-09-24%20%E4%B8%8B%E5%8D%883.26.13.png?token=ALYX5XZRA3UKKMXZEDFLK4C7NRFGE)

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

