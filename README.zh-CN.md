# 概念摄影计划

[English](README.md) | **简体中文**

`conceptual-photography-plan` 是一个面向 Codex 的原创概念摄影 Skill。它可以根据一个词、一个具体物件、一张素材图或一个主题，扩展候选创意，筛掉牵强和物理上不成立的方案，并默认直接生成对应的写实图片。

它不追求把两个形状相似的东西简单拼在一起，而是寻找一条真正成立的新关系：物件仍然能够被认出，原有功能或动作仍然有效，连接、承重、路径、光线和场景也经得起检查。

> **一句话目标：**让荒诞只发生在 10% 的关键关系上，其余 90% 都像真实世界。

## 示例作品

<table>
  <tr>
    <td width="33%" align="center">
      <img src="assets/examples/cassette-ponytail.png" alt="倒带马尾" width="100%"><br>
      <strong>倒带马尾</strong><br>
      磁带盒保留卷带结构，磁带成为能够被“倒带”的马尾。
    </td>
    <td width="33%" align="center">
      <img src="assets/examples/eyebrow-lawn.png" alt="眉毛草坪" width="100%"><br>
      <strong>眉毛草坪</strong><br>
      微型割草机沿眉毛行进，接触点与修剪结果同时可见。
    </td>
    <td width="33%" align="center">
      <img src="assets/examples/blind-skirt.png" alt="百叶裙" width="100%"><br>
      <strong>百叶裙</strong><br>
      百叶窗保留叶片、梯绳和拉绳系统，接管裙摆的开合功能。
    </td>
  </tr>
  <tr>
    <td width="33%" align="center">
      <img src="assets/examples/sharpen-candle.png" alt="削亮一支蜡烛" width="100%"><br>
      <strong>削亮一支蜡烛</strong><br>
      卷笔刀真实削动蜡烛，削屑、刀口和烛芯形成完整动作证据。
    </td>
    <td width="33%" align="center">
      <img src="assets/examples/tear-wiper.png" alt="给眼泪装雨刷" width="100%"><br>
      <strong>给眼泪装雨刷</strong><br>
      外贴式微型雨刷沿泪痕工作，把“擦去眼泪”变成真实机械动作。
    </td>
    <td width="33%" align="center">
      <img src="assets/examples/apple-corkscrew.png" alt="给苹果开瓶" width="100%"><br>
      <strong>给苹果开瓶</strong><br>
      开瓶器旋入带果皮的苹果芯，完整保留旋入、受力和提拉路径。
    </td>
  </tr>
</table>

这些案例分别使用了动作错置、功能替身和尺度转换，但都遵守同一原则：**不是借外形做装饰，而是让功能、动作和结果共同成立。**

## 它能做什么

- **指定元素创意：**输入香蕉、玫瑰、梳子、蜡烛等元素，生成彼此不同的原创方向。
- **主题创意：**围绕爱情、情人节、孤独、时间等主题，寻找可被单帧照片直接表达的关系。
- **素材图驱动：**先从参考图中判断能否提取结构完整、功能明确的“物件锚点”；有锚点时优先保留其真实结构和功能，无法提取时才退回纯风格参考。
- **场景改造：**保留原图约 80%–90% 的空间、人物、透视和光线，只改变一个关键关系。
- **逻辑校对：**检查连接点、承重、铰链、工具方向、液体路径、开合方式、投影和动作因果。
- **连续迭代：**理解“下一个”“继续”“pass”“保留人物，只改道具”等短反馈，并锁定未被点名的部分。
- **直接生成图片：**默认同时交付筛选后的创意和对应图片，不需要另外补充“出图”。

## 核心方法

### 1. 先找共享动词

一个创意至少需要：

```text
原物件 + 意外目标 + 双方共享的真实动作
```

例如，割草机与眉毛共享“修剪”，雨刷与眼泪共享“擦除”，开瓶器与苹果共享“旋入并提起”。只有颜色、轮廓或大小相似，而没有共享动作的组合会被优先淘汰。

### 2. 先否决，再评分

候选必须先通过物件辨识、动作完整、天然功能联系、物理闭环、摄影美感和原创距离六项硬门槛；任何关键结构不成立，都不能靠高概念分补救。

通过硬门槛后，再按以下权重选优：

- 观念新鲜度：40%
- 情绪或含义：20%
- 视觉冲击力：10%
- 一眼可读性：10%
- 原创距离：10%
- 可拍摄性：10%

### 3. 把创意变成单帧证据

最终画面需要让观众依次看到：

```text
原物件身份 → 接触或连接 → 变化结果
```

如果画面必须依赖标题才能看懂，或者只能被描述成“把某物放在某处”，该构图不会进入生成阶段。

## 安装

### 方法一：让 Codex 安装（推荐）

在 Codex 中发送：

```text
使用 $skill-installer，从 https://github.com/natsany/conceptual-photography-plan 安装这个 Skill。
```

安装完成后，在下一轮对话或新任务中调用即可。

### 方法二：使用 Git 克隆

#### Windows PowerShell

```powershell
$skillRoot = if ($env:CODEX_HOME) {
    Join-Path $env:CODEX_HOME 'skills'
} else {
    Join-Path $env:USERPROFILE '.codex\skills'
}

New-Item -ItemType Directory -Path $skillRoot -Force | Out-Null
git clone https://github.com/natsany/conceptual-photography-plan.git `
    (Join-Path $skillRoot 'conceptual-photography-plan')
```

#### macOS / Linux

```bash
skill_root="${CODEX_HOME:-$HOME/.codex}/skills"
mkdir -p "$skill_root"
git clone https://github.com/natsany/conceptual-photography-plan.git \
  "$skill_root/conceptual-photography-plan"
```

安装目录中应直接包含 `SKILL.md`：

```text
conceptual-photography-plan/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── calibration.md
    ├── logic-audit.md
    └── prompt-patterns.md
```

> 默认安装位置是 `$CODEX_HOME/skills`；未设置 `CODEX_HOME` 时使用 `~/.codex/skills`。安装后请新开一个任务，让 Codex 重新加载 Skill。

## 使用方法

在提示词中明确写出 `$conceptual-photography-plan`，再提供元素、主题或素材图。

### 根据一个元素生成两个创意和图片

```text
使用 $conceptual-photography-plan，根据香蕉做2个新创意。
```

### 根据主题生成指定数量的创意

```text
使用 $conceptual-photography-plan，根据“情人节”做4个创意并直接出图。
```

### 使用素材图

先上传图片，再发送：

```text
使用 $conceptual-photography-plan，用这张素材图测试，筛选最佳创意并直接生成3:4图片。
```

Skill 会先判断素材图是编辑目标、场景底图、物件锚点还是纯风格参考，不会因为用户说了“参考图”就直接复制原图构图。

### 精准修改当前图片

```text
保留人物、场景和光线，只把雨刷改成外贴式微型道具。
```

简短反馈默认修改当前选中图片；未被点名的构图、人物、材质和光线会尽量保持不变。

### 只看创意，不生成图片

```text
使用 $conceptual-photography-plan，根据玫瑰做2个新创意。只要方案，不要出图。
```

## 默认输出

- 只指定一个元素且未写数量时：默认给出 **2 个不同创意 + 2 张对应图片**。
- 上传素材图并说“用这个试试”时：默认筛选 **1 个最佳方向 + 1 张图片**。
- 指定数量时：每个创意分别生成一张图，不用拼贴代替多张成图。
- 默认画幅：竖版 **3:4**、全画幅、无白边、无圆角。
- 默认风格：写实摄影；动作型概念优先真实场景与自然光。
- 每张图只保留一个异常关系，不添加解释文字、箭头、标签或魔法光效。

## 适合的任务

- 原创概念摄影与视觉隐喻
- 广告创意、编辑摄影、社交媒体视觉
- 从参考图提取机制但避免近似抄袭
- 对 AI 成图进行结构、动作和物理合理性校对
- 连续产出一组机制不同、视觉语言统一的作品

它不是一个“随机拼贴器”。如果创意无法在一句话内说清、无法在一秒内识别，或现实结构无法闭环，它会优先换方向，而不是用复杂说明替画面辩护。
