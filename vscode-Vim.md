# Vscode+Vim：丝滑开发~
## 参考资料
- [指尖飞舞：vscode + vim 高效开发（系列视频）](https://www.bilibili.com/video/BV1z541177Jy/?spm_id_from=333.337.search-card.all.click)

## 配置
- 由于搭配Vscode使用，加上`CTrl+C`、`Ctrl+V`、等常用快捷键是在太习惯了，难以放弃，这里这里禁用掉Vim中所有与Ctrl相关的快捷键,`settings.json`文件中设置如下：
> "vim.useCtrlKeys": false, //禁用Vim中Ctrl相关快捷键

个人完整配置供参考：
```json
{
  "vim.useCtrlKeys": false, //禁用Vim中Ctrl相关快捷键
  "vim.easymotion": true,   // 启用 EasyMotion 插件功能,可以快速跳转到屏幕上的任意位置，
  "vim.incsearch": true,    // 启用增量搜索,输入搜索词时实时高亮匹配结果
  "vim.useSystemClipboard": true,   //使用系统剪贴板
  "vim.hlsearch": true, // 高亮所有搜索结果
  "vim.timeout": 180 ,  // 按键序列超时时间(ms)

  // 插入模式自定义按键映射
  "vim.insertModeKeyBindings": [
    {
      "before": ["j", "j"],
      "after": ["<Esc>"]
    },
    {
      "before":["j","<leader>"],
      "after":[" ", "=", " "]
    },
    {
      "before":["k","<leader>"],
      "after":[" ", "+", " "]
    },
    {
      "before":["i","<leader>"],
      "after":["("]
    },
    {
      "before":["o","<leader>"],
      "after":["_"]
    },
    {
      "before":["l","<leader>"],
      "after":["j", "j", "l", "a"]
    },
    {
      "before":["i","i"],
      "after":["*"]
    },
    {
      "before":["u","u"],
      "after":["&"]
    },
    {
      "before":["e","e"],
      "after":["Escape", "A"],
    },
    {
      "before":["a","a"],
      "after":["Escape", "I"]
    },
  ],


  // 普通模式自定义按键映射
  "vim.normalModeKeyBindingsNonRecursive": [
    {
      "before": ["<leader>","j"],
      "after": ["1","0","j"]
    },
    {
      "before": ["<leader>","k"],
      "after": ["1","0","k"]
    },
    {
      "before": ["K"],
      "commands": ["lineBreakInsert"],
      "silent": true
    },
    {
      "before": ["<leader>","t"],
      "commands": ["workbench.action.terminal.focus"]
    }   // 聚焦到 VSCode 终端
  ],

  // 命令行模式自定义按键映射
  "vim.commandLineModeKeyBindings": [],   
  "vim.leader": "<space>",
  "vim.handleKeys": {
    "<C-a>": false,
    "<C-f>": false
  },    // 禁用 Vim 对 Ctrl+A 和 Ctrl+F 的接管
}
```

## 快捷键

| 快捷键                                        | 说明                                     |
| :-------------------------------------------- | :--------------------------------------- |
| `ci + 符号`                                   | 清除符号中的内容并修改,例如： <br> `ci'` 清除引号内容并修改;<br> `cib'` 清除括号内容并修改（b 指 block）; <br> `ciw'` 删除当前光标所在的单词并进入插入模式;<br> `cie'` 修改整个文件;<br> `cit'` 修改标签（HTML 中 div、body 中常用）; |                   |
| `ca + 符号`                                   | 清除所有内容（包括符号）并修改           |
| 上面命令中 `c` 可改成 `y`、`d`、`v`           | 修改 / 复制 / 删除 / 可视选择，实现同类操作  |
| `数字 + dd`                                   | 向下删除几行（包括光标所在行）           |
| `df_` / `cf_` / `yf_`                         | 删除到 / 修改到 / 复制到（指定字符）     |
| `die`                                         | 删除整个文件                             |
| `gd`                                          | 跳转到函数源代码                         |
| `gh`                                          | 显示语法相关信息                         |
| `gt`                                          | 跳转到下一个文件；`4gt` 跳转到第四个文件 |
| `gT`                                          | 跳转到上一个文件                         |
| `CTRL + 0`                                    | 跳转到侧边栏                             |
| `CTRL + 1`                                    | 回到主编辑器                             |
| `空格 + 空格 + s + 指定字母`                  | 快速移动光标到指定字母处                 |
| `cs + 原符号 + 新符号`                        | 将原符号修改成新符号                     |
| `ds + 符号`                                   | 将单词两侧的符号删除                     |
| `ysiw + 符号`                                 | 给单词两侧加上符号                       |
| 按多次 `gb` 可选中多个单词，再按 `c` 批量修改 | 批量选中并修改相同单词                   |
| 按下两次单引号（`''`）                        | 回到上次光标所在位置                     |
