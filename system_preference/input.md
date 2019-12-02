# 输入法

## 鼠鬚管 Squirrel

```text
brew cask install squirrel
```

```text
cd ~/Library/Rime
wget https://raw.githubusercontent.com/rime/rime-double-pinyin/master/double_pinyin_flypy.schema.yaml
```

新建文件 touch ~/Library/Rime/default.custom.yaml, 内容如下

```yaml
# 以下的 default.custom.yaml 在全局范围内重新定义该组快捷键
#
# 可用的按鍵有 Caps_Lock, Shift_L, Shift_R, Control_L, control_R
# Mac 系統上的鼠须管不能区分左、右，因此只有對 Shift_L, Control_L 的設定起作用
#
# 已输入编码时按切换键，可以进一步设定输入法中西文切换的形式。
# 可选的临时切换策略有三：
# inline_ascii 在输入法的临时西文编辑区内输入字母、数字、符号、空格等，回车上屏后自动复位到中文
# commit_text 已输入的候选文字上屏并切换至西文输入模式
# commit_code 已输入的编码字符上屏并切换至西文输入模式
# 设爲 noop，屏蔽该切换键
#
# 如果要把 Caps Lock 设爲只改变字母的大小写而不做中西文切换，可将 Caps_Lock 对应的切换方式设爲 noop
# 如果要以 Caps Lock 切换到西文模式，默认输出小写字母，请置 ascii_composer/good_old_caps_lock: false
# 如果要以 Caps Lock 切换到西文模式，默认输出大写字母，请使用以下设置：

# default.custom.yaml
# Rime default settings
# encoding: utf-8

patch:
  schema_list:
    - schema: double_pinyin_flypy
    - schema: luna_pinyin_simp

  ascii_composer/good_old_caps_lock: false
  ascii_composer/switch_key:
    Caps_Lock: commit_code
    Shift_L: noop
    Shift_R: noop
    Control_L: commit_code
    Control_R: commit_code

# 以方括号 “[” 和 “]” 来换页
  "key_binder/bindings":
    - { when: paging, accept: bracketleft, send: Page_Up }
    - { when: has_menu, accept: bracketright, send: Page_Down }
```

### 模糊音

参照 [模糊音模板](https://gist.github.com/lotem/2320943) 修改 原yaml文件 speller/algebra

```yaml
- erase/^xx$/
- abbrev/^([a-z]).+$/$1/
- abbrev/^([zcs]h).+$/$1/
# - derive/^([zcs])h/$1/             # zh, ch, sh => z, c, s
# - derive/^([zcs])([^h])/$1h$2/     # z, c, s => zh, ch, sh
# - derive/^n/l/                     # n => l
# - derive/^l/n/                     # l => n
- derive/([ei])n$/$1ng/            # en => eng, in => ing
- derive/([ei])ng$/$1n/            # eng => en, ing => in
```

### 外观设定

squirrel.custom.yaml

```yaml
patch:
#  us_keyboard_layout: true                 # 键盘选项：应用美式键盘布局
  # 状态通知，适当，也可设为全开（always）全关（never）
  show_notifications_when: appropriate

  style/color_scheme: google                 # 选择配色方案
  style/horizontal: true                   # 候选窗横向显示
#  style/inline_preedit: false              # 关闭内嵌编码，这样就可以显示首行的拼音
  style/corner_radius: 3                  # 窗口圆角半径
  style/border_height: 0                   # 窗口边界高度，大于圆角半径才有效果
  style/border_width: 4                    # 窗口边界宽度，大于圆角半径才有效果
#  style/line_spacing: 1                    # 候选词的行间距
#  style/spacing: 10                         # 在非内嵌编码模式下，预编辑和候选词之间的间距
  style/font_face: "Libian SC Regular"     # 预选栏文字字体，使用中文字体
  style/font_point: 24                            # 预选栏文字字号
  style/label_font_face: "Myriad Pro Light"       # 预选栏编号字体，当前为 Monaco 使用默认西文字体：Myriad Pro Light
  style/label_font_point: 24                     # 预选栏编号字号bo
# 一些要默认英文输入的 app
  app_options/com.agilebits.onepassword4:
    ascii_mode: true
  app_options/com.runningwithcrayons.Alfred:
    ascii_mode: true
  app_options/com.googlecode.iterm2:
    ascii_mode: true
  app_options/com.jetbrains.intellij.ce:
    ascii_mode: true
  app_options/org.gnu.Emacs:
    ascii_mode: true

# 注：预设的配色方案及代码（指定为 style/color_scheme ）
#   碧水 - aqua
#   青天 - azure
#   明月 - luna
#   墨池 - ink
#   孤寺 - lost_temple
#   暗堂 - dark_temple
#   星际我争霸 - starcraft
#   谷歌 - google
#   晒经石 - solarized_rock
#   简约白 - clean_white
```

emoji 设置

