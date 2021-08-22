### 快捷键列表

| Alt + /              | 补全代码的声明                        |
| -------------------- | ------------------------------------- |
| Ctrl + 1             | 快速修复                              |
| Ctrl + Shift + O     | 批量导包                              |
| Ctrl + /             | 切换单行注释                          |
| Ctrl + shift + /     | 使用多行注释                          |
| Ctrl + shift + \     | 取消多行注释                          |
| Ctrl + alt + down/up | 复制指定行代码                        |
| Ctrl + D             | 删除指定代码                          |
| Alt + up/down        | 代码上下移动                          |
| Shift+enter          | 给代码下添加一行                      |
| ctrl + shift + enter | 代码上添加一行                        |
| Ctrl + 点击指定结构  | 查看源代码                            |
| Ctrl + Shift + t     | 搜索，查看源代码                      |
| Alt + left           | 退回前一个编辑页面                    |
| Alt + Right          | 到达下一个编辑页面                    |
| Ctrl + T             | 查看继承树结构                        |
| Ctrl + C             | 复制                                  |
| Ctrl + V             | 粘贴                                  |
| Ctrl + Shift + F     | 格式化代码                            |
| Ctrl + Y             | 反撤銷                                |
| Ctrl + S             | 保存                                  |
| Ctrl + A             | 全选                                  |
| Tab                  | 选中数行整体后移                      |
| Shift + tab          | 选中数行，整体前移                    |
| Ctrl + O             | 寻找需要找到的类                      |
| Alt + Shift + R      | 对多个变量进行改名                    |
| Ctrl + F             | 寻找文本，替换                        |
| Alt + Shift + S      | 自动生成getter/setter/构造器的结构    |
| Ctrl + Shift + y     | 变成小写                              |
| Ctrl + Shift + x     | 变成大写                              |
| Alt + Enter          | 显示文件的属性                        |
| Ctrl + K             | 快速查找 - 根据当前选中的word向下查找 |
| Ctrl + W             | 关闭当前窗口                          |
| Ctrl + Shift + W     | 关闭所有窗口                          |
| Ctrl + alt + g       | 查看指定结构使用过的地方              |
| Ctrl + f             | 查找和替换                            |
| Ctrl + m             | 最大化当前的View                      |
| Home  (Fn+6)         | 本行首位                              |
| End  (Fn+7)          | 本行末尾                              |

#### 注意

在使用批量导包时，有可能弹出提示 -- 这是因为存在同名的类，需要手动选择

#### 配置快捷键

`Windows`-`Preferences`-`Java`-`Editor`-`Content Assistant` 改成所有字符就可以实现输入任何字符都进行联想补全

`Windows`-`Preferences`-`General`-`Keys`修改自定义快捷键

### Eclipse Debug

加入断点（双击代码行数）

程序的入口都是main方法，不停执行到程序结束；我们加入断点以后，就可以让程序每次执行到断点暂停

Debug as Java Application（不能选择Run as java application）

点击step over,表示运行下一行代码

点击step into，表示进入当前代码所运行的方法内部

点击step return，表示从方法内部退出，回到之前所在的位置（如main方法）

点击Drop to frame，表示回到方法的首行

有的人发现 step into没有反应，并没有进入方法的代码实现 -- 这是因为我们没有使用jdk，而是jre