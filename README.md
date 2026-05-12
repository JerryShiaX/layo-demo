# Layo — Engineered Garments, Beyond Boundaries.

> v3 · 极简电影感重写。
> 灵感来源：**Bottega Veneta · Aesop · Loro Piana · Hassan Rahim · Acne Studios · Yohji Yamamoto**
> 信条：内容越少，气质越高。

## 怎么看

```bash
cd "/Users/xiachenjie/Desktop/Big Project/layo-redesign-demo"
python3 -m http.server 7788
# 打开 http://localhost:7788
```

或者直接双击 `index.html`。

## v3 相对 v2 做减法（不是加法）

| v2 旧 | v3 现在 |
|---|---|
| 15 个 sections（marquee / 4 卡 / 9 行列表 / 3 篇 press …）| **6 个 Acts** + Footer。每屏一个想法。 |
| 4 种字体粗细 + 3 字体家族 | **Cormorant Garamond + Inter** 两家族，三种字重 |
| 米白 + 沙色 + 暖灰 + 雾蓝 + 深炭 + ember | **Bone (#F4EFE8) + Ink (#0A0908)** 两色 |
| 多个 hover 卡片 / 跑马灯 / 数据表 | **横向 sticky 滑动 + 字幕式 manifesto + 整屏单数字** |
| 数字带 `$300M / 30 / 80+ / 120` 像 dashboard | **数字 = 诗**：每个数字独占整屏，下面一句诗式 italic Cormorant |
| 联系区有完整表单 | 默认只显示 **"Begin a brief."** 大字 + 三行联系方式；点 CTA 才滑出 overlay 表单 |

## 六个 Acts（每个 Act 一屏，一念，一图）

### Act I · Horizon（hero）
- 全屏山脉夕阳，Ken Burns 慢速 18 秒缓推
- **"Engineered Garments, *Beyond Boundaries.*"** 巨号细衬线
- 右中 "Agility / Speed / Materiality" + 斜体副标
- 右下 VOL. 03 · SS 26 / "Since nineteen ninety-six." 
- 左下 SCROLL 提示线动画

### Act II · Manifesto（字幕式揭示）
- 米白底，居中
- 一句长 manifesto 被切成 6 个 phrase
- 滚动驱动逐 phrase 显形（电影字幕感）
- 底部 6 个 dash 进度条同步
- 一句话花 5 屏的高度阅读

### Act III · The Layo World（sticky 横滑）
- 4 张自然图：LAND / AIR / YONDER / OCEAN
- 占用 4 屏高的 sticky container
- 你纵向滚 → 页面横向滑过 4 张全屏图
- 每张图：超大半透明 L / A / Y / O 字母 + 底部 name + italic Cormorant 描述
- 底部 pager 4 dashes 同步进度

### Act IV · In Numbers（三屏单数字）
- 每个数字独占整屏（cream / dark / cream 交替）
- **30Y** / **80+** / **120**，巨号细衬线
- 数字下一句 italic Cormorant：
  - "Years of fabric. Three apparel generations, one obsession with finish."
  - "Countries shipped. From Milano boutiques to Vancouver flagships."
  - "Brand partners on the floor. *Quietly,* across two decades."
- 进入视区从 0 滚到目标，缓动 4 次方

### Act V · A Garment Study（单件研究）
- 黑底，左右分屏
- 左 ½：标题 + italic Cormorant + 数据小行（Seamless / Recycled / 195 GSM / SS 26 Sample 04）
- 右 ½：单张技术服装大图

### Act VI · Begin（联系）
- 米白底
- **"Begin a *brief.*"** 巨号细衬线
- 右下：italic 引导 + **"OPEN THE FORM"** 黑色 CTA 按钮（磁吸）
- 底部 3 列联系：EMAIL / DIRECT LINE / STUDIO

### Footer · Sign-off
- 黑底
- 巨号 **"Layo."** 居中（滚入时字符从下浮起）
- 一行小字：© 2026 / Engineered Garments · Beyond Boundaries. / Privacy · Terms · Site map

## "让人爱不释手"的交互（你逐项可以验收）

✅ **Curtain Loader**：黑色幕布从中央分裂上下打开，揭示 hero
- 4 个字母 L A Y O 错峰浮起（每 150ms）
- 底部 italic tagline "Engineered Garments · Beyond Boundaries."
- 进度条从左到右填满 2.2 秒

✅ **自定义鼠标**：白点 + 圆环 + 内嵌 label
- 默认 5px dot + 32px ring
- hover 链接：ring 扩大到 78px，dot 缩到 0，label 显示 "view" / "tap" / "open" / "send" / "close"
- 全屏 difference 混色

✅ **Manifesto 字幕式揭示**：滚动时一句话分 6 段逐次显形
- 已显形的字 100% 黑色
- 未显形的字 18% 灰
- 底部 progress dash 同步

✅ **Sticky 横向 LAYO World**：垂直滚 = 横向滑过 4 张图
- 当前活跃 panel 图像 zoom 1→1.06
- pager 4 dashes 显示当前位置
- 移动端自动降级为纵向 4 panel 叠放

✅ **数字 counter-up**：滚到 50% 视区从 0 数到目标
- 2.2 秒 + 4 次方 ease-out 缓动
- 数字下面是 italic Cormorant 诗

✅ **磁吸 CTA**：鼠标靠近 "Open the form" / "Send the brief" 按钮时
- 按钮 transform 朝鼠标方向位移 22-32%
- 离开 0.5s 弹性回位

✅ **Overlay 询盘**：点 "OPEN THE FORM" → 黑色全屏 overlay 从底滑上
- 表单内 label 浮动效果（聚焦 / 填充时 label 上移 + 缩小 + 变白）
- 提交后按钮变 "Sending…" → "✓ Brief received" → 自动收起
- ESC 关闭

✅ **Nav 主题感知**：滚到 Act I / III / V / Footer 这些黑色板块时
- nav 文字自动变白
- 0.8s ease 过渡

✅ **滚动平滑锚点**：所有 # 锚点链接平滑滚动

✅ **Mobile**：汉堡菜单全屏抽屉 + LAYO World 横滑降级为纵向 + 表单单列 + WhatsApp/cursor 隐藏

✅ **0 个 console error**

✅ **SEO**：完整 title / description / OG / favicon / `<html lang="en">`

## 字体（全部免费）

- **Cormorant Garamond** — Google Fonts，做所有标题和品牌字。轻盈、克制、有呼吸感。和 Aesop / Bottega 同款审美方向。
- **Inter** — Google Fonts，做小字、meta、nav、表单 input。

只用 2 个字体家族，每个家族 3 种字重。

## 颜色（极致 2 色）

```
--bone:  #F4EFE8   主底
--ink:   #0A0908   黑色板块底 + 主文字
--mute:  rgba(10,9,8,0.42)   小字
```

完。不需要更多。

## 文件清单

```
layo-redesign-demo/
├── index.html        ← 1570 行（HTML + 内联 CSS + JS，0 依赖）
├── README.md         ← 你正在看的
└── screenshots/      ← 12 张桌面+移动验证截图
    ├── v3-01-curtain.jpeg       Curtain Loader
    ├── v3-02-hero.jpeg          Act I · Horizon
    ├── v3-03-manifesto.jpeg     Act II · Manifesto (开始)
    ├── v3-04-manifesto-deep.jpeg Act II · Manifesto (深处)
    ├── v3-05-world-land.jpeg    Act III · World (Land→Air 过渡)
    ├── v3-06-num30.jpeg         Act IV · 30Y
    ├── v3-07-num80.jpeg         Act IV · 80+ (dark)
    ├── v3-08-garment.jpeg       Act V · Garment Study
    ├── v3-09-begin.jpeg         Act VI · Begin a brief
    ├── v3-10-footer.jpeg        Footer Layo.
    ├── v3-mob-01-hero.jpeg      手机 Hero
    └── v3-mob-02-world.jpeg     手机 World
```

## 给乙方/客户看时强调这些点

1. **"每一屏只有一个想法"** —— 极简不是少做，是更难做。每个 Act 都被精心设计成可以放在一张 Vogue 内页上不违和。
2. **"内容是节奏"** —— 这个网站不是浏览网页，是看一段电影。鼠标只是镜头，滚动是时间。
3. **"字体是语调"** —— 全站只有 Cormorant Garamond + Inter。轻、安静、不喧哗。
4. **"功能藏在简单后面"** —— 表面只有大字 + 大图，但每个像素都在工作：横滑、磁吸、字幕、计数、curtain、自定义鼠标、主题感知、表单 overlay。
5. **"减得动是奢侈"** —— 一线奢侈品官网都做得起加法，做得起减法的只有 Bottega Loro Aesop。这一版 Layo 在那个组里。
