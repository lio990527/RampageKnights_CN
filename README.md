# RampageKnights中文补丁
========================================

安装
----
方式 A（一键）：
    1. 把 RampageKnights_CHS 整个文件夹放进游戏安装目录
       （就是有 rampage_knights.exe 的那一层）
    2. 双击 install.bat

方式 B（手动）：
    把 data 和 scripts 两个文件夹拖进游戏目录，提示合并时选“是”。

还原
----
双击 uninstall.bat，会用本包 _original 里的官方原版文件覆盖回去。
不需要重新下载游戏。也可以直接 Steam 校验文件完整性。

本版修复
--------
v1.1 修复了 v1.0 的致命问题：标题字体图集用了 4096x2048，超出引擎
单边 2048 像素的硬上限，导致 orgy 字体加载失败。
表现是：NPC 名字、对话标题、鼠标悬停提示（tip）、帽子名、成就名、
HUD 数字全部不显示，并且因为每帧重试加载纹理而严重掉帧。
现在标题图集改为 2048x2048，字号在引擎允许范围内取到最大。

文件清单
--------
data/text.txt.bin                     文本库（1342 条译文）
data/font/komika.fnt / .png           羊皮纸黑字
data/font/komika_white.fnt / .png     正文、对话、菜单
data/font/orgy2.fnt / .png            标题、提示、HUD、成就
data/ui/camp_menu.png                 挑战面板 + 营地横幅
data/ui/camp_menu2.png                营地菜单五条卷轴
data/ui/cards.png                     挑战卡牌名
data/ui/surgery_cloth.png             手术布
data/ui/intro/intro_text.png          片头字幕
scripts/entities/GameOver.nut.bin
scripts/hud/HUD_ingame_menu.nut.bin
scripts/menu/MainMenu.nut.bin
scripts/menu/LobbySubMenu.nut.bin
scripts/menu/PagedSubMenu.nut.bin

常见问题
--------
Q: 文字全空白
A: 字体文件没复制全。确认 data/font 下六个文件（.fnt 与 .png 各三套）
   都被覆盖了。

Q: 只有标题/提示不显示
A: 是 orgy2 字体没加载。检查 data/font/orgy2.png 是不是 2048x2048。
   引擎硬性限制单边不能超过 2048 像素。

Q: 出现方块或问号
A: 字体图集不完整，重新覆盖一次 data/font。

Q: 覆盖了但没变化
A: 多半覆盖到了别的目录。data 和 scripts 必须和 rampage_knights.exe
   在同一层。

Q: 卡顿
A: 字体纹理加载失败时引擎会反复重试，就会卡。换成本版（v1.1）即可。

注意
----
Steam 的“校验游戏文件完整性”会把所有改动还原成英文。
校验之后重新覆盖一次即可。
