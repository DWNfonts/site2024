---
layout: mypost
title: 中文 Windows Vista 发展史未曾注意到的一瞥——上·宋体 3.05
categories: [宋体]
---
> [原文链接](https://gist.github.com/diaowinner/b0244f05721981d778ca40164e4ea6bb)。在 2024 年 6 月 27 日导入此博客

Windows 可能是世界上最受欢迎的桌面操作系统了。在 Windows 的发展史上有一个版本总是被当今的互联网提及——Windows Vista。Pre-Reset Longhorn、发布后的舆论、Mojave 项目…这样的事情已经重复了千万遍，我也不必多说。

而今天我要说的，则是 Windows 鲜为人知的 typography。简中互联网多数以 Segoe UI 来「代表」Windows Vista 在字体方面的新颖之处，当然 Segoe UI 也并不新颖，在后来的 Windows 中皆有使用。而今天我要讲的，则是 Windows Vista 简体中文字体的故事。
> 实际上，这是一篇回忆录。原先的资料已经走向了他们的 `/dev/null`，所以这篇文章很多地方都没有图，再加上我本人未完全掌握相关知识，如有勘误请见谅

## 初印象：Vista 正式版和 Pre-Reset 构建
大家即使没有用过 Vista 也可能看到别人在用 Vista。对我来说，Vista 最初的记忆莫过于 oeasy 的各种教程了（[这就是一例](https://www.bilibili.com/video/BV1cs411o7yM)）。后来我加入了哔哩哔哩，看到了各种科技视频，于是就从「MSDN 我告诉你」下载了一张 Windows Vista 的镜像拿来玩。这字体跟 Windows 7 没什么区别（跟现在的 Windows 10 比杂了，并且那不是这篇文章讨论的对象），在我肉眼里，唯一的区别，可能就是「微软雅黑」的西文有点大。

接着，某次，我尝试了一款 Pre-Reset Longhorn 构建——Longhorn 4093。这个构建附带了多种语言的字体。我打开了这个构建的 Internet Explorer，看到了她的字体——怎么跟 XP 一模一样啊喂！
## 构建号 5384：故事在这里开始
> 14 年前，电视上放映着大大怪和小小怪误操作将机械石投到四个报废的机车的片段。这，即是《开心宝贝》（现名《开心超人联盟》）的开端。同样，我也有这么一个线索，和我的思绪一起，拉向 19 年前。

在 ～2021 年，我刷到了一个视频——这个系统附带了一个奇特的宋体。我于是把手机凑近眼睛，在标题上面看到了构建号：5384。

我下载了 5384 的 ISO 文件，提取了附带的 `simsun.ttc`，发到了几个群里。

然后这事就过去了，风平浪静…
## 宋体 3.05
说到我提取的 `simsun.ttc` 这是一个很奇怪的预发布版宋体——冠以「3.05」的版本号，而[非 Vista RTM 上的 5.0](https://learn.microsoft.com/en-us/typography/font-list/simsun)。

首先，FontForge 读不了点阵。（当然了，FontForge 读不了点阵的多了）

那么 FontLab Studio 呢？多亏了 Wine，我们现在不用装虚拟机就能用 FontLab 了。（就是有点慢）

![打开宋体的 Fontlab](/posts/2024/06/09/337981828-bbd3a0c5-a6c8-4363-b857-059736bb547f.png)

然后，让我们：

1. 点开一个字形
2. 点击 TrueType Hinting
3. ~~反正我是等着进度条走完了，似乎不走也行~~
4. 点击 Bitmap Tool 和 Preview Panel

![Preview Panel](/posts/2024/06/09/337981849-12d5c7e0-8cc1-460f-88f2-8c9048425f5d.png)


这个 Preview Panel 看起来可能是唯一的点阵预览面板了。还不能直接输入文字，必须转换成类似 `\u8FD9\u6837` 的形式才能认，反人类啊。

看到那个红色的 12、14、16 吗？这就是这款宋体附带的 3 款点阵。用过 FontForge 开 Vista RTM（往后的也在这一点几乎相同）宋体、FontLab Studio 开 XP 宋体的都知道，这些宋体基本上都附带 12-16 五套点阵（XP 外加 18px 点阵，Vista RTM 的宋体似乎带 17px 点阵？）

![四行 12px、14px、16px 的示例文本，内容：谁知道这只全身雪白的狐狸竟然直起身体，用她的右前爪和我握手。](/posts/2024/06/09/337981871-5fc410c5-107a-488e-b1b3-7341977ea9f8.png)


这是宋体的样张，每套点阵从上到下依次为 Vista Build 5384 的宋体和…呃… **Solaris 10 的方正宋体。** 不过这「方正宋体」参考的点阵部分几乎和 Vista RTM 的点阵一样，就当成 Vista RTM 宋体吧（你咋这么不要脸！）

可以看到在 12px 和 14px 方面，Build 5384 的宋体的中宫明显缩小了，而在 16px 部分则有一丝残留的 Windows XP 宋体气味。不过这个字体总体来说偏向 Vista RTM 一些。

并且，在 Build 5384 中的宋体甚至覆盖到了 CJKUI 扩展 A 区。

在 Windows 2000/XP 中，CJKUI 扩展 A 区的显示是使用一个什么「GB18030 适配包」，附带的字体「宋体-GB18030」（记不清了应该是这个名字）就含有这种点阵（字形和 Vista RTM 差不多）。而这个 Build 的点阵却和这个什么「宋体-GB18030」也不一样。

那为什么会出现这样的情况呢？我在 2024 年初上完课的时候就探索了这一问题，但这是后事了。

（待续）