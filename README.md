<div align="center">

# 跨境电商 AI 带货视频制作

**一套面向低成本、复杂 AI 带货视频制作的 Codex Skills 与实战 Prompt SOP。**

先写脚本与口播，再生成并验收真人首帧和产品图、处理人脸遮罩参考图、图生视频、制作爆款开头，并通过 Codex 或 Claude 拆解参考视频。

[![GitHub stars](https://img.shields.io/github/stars/Longxiaohao/AIvideo?style=flat-square)](https://github.com/Longxiaohao/AIvideo/stargazers)
[![License](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](./LICENSE)
[![Codex Skills](https://img.shields.io/badge/Codex-Skills-black.svg?style=flat-square)](./skills)
[![Video Tools](https://img.shields.io/badge/video-Veo%20%7C%20Grok%20%7C%20Seedance-orange.svg?style=flat-square)](#自动路由)

**中文** | [English](./README.en.md)

</div>

---

## 我为什么做这个项目

我做这套 Skills，不是因为市面上缺 AI 工具，而是因为我自己做跨境电商带货视频时，发现最现实的问题一直都是：怎么把成本压下来，同时还能把片子做出来。我的实际感受是，很多时候不一定非要上昂贵的商业工具。免费的豆包 Seedance Fast，再搭配 Grok、Veo，已经能完成脚本、出图和图生视频里的大部分工作。

所以我把自己实际跑过、改过、踩过坑之后留下来的 Prompt 和路由规则，整理成了这套可以重复使用的 SOP。我希望它不只对做跨境电商视频的人有用，也能帮到正在找 AI 视频制作岗位、需要快速做作品集和积累项目经验的人。

在产品资料和参考素材比较齐的情况下，我现在会用这套流程灵活切换不同工具，目标是在 1 小时内搓出一条结构比较复杂的 AI 带货视频。但这不是说每个产品都一定能在 1 小时内完成，生成排队、产品难度和返工次数都会影响时间。

这个仓库里保留的都是我实际使用的原始 Prompt。Skill 只负责任务识别、输入检查和分支调度，我不会为了看起来更短、更“专业”就把这些实践 Prompt 二创、压缩或改写。

## 核心工作流

```mermaid
flowchart LR
    A["Codex / Claude<br/>拆解爆款视频"] --> B["脚本与口播"]
    B --> C["真人模特首帧<br/>产品图与场景图"]
    C --> D["人脸遮罩<br/>参考图预处理"]
    D --> E["Veo / Grok / Seedance<br/>图生视频"]
    E --> F["宫格爆款开头"]
    F --> G["剪辑与成片"]
```

1. 使用 Codex 或 Claude 拆解爆款参考视频，提取开头结构、镜头、制作动作和节奏。
2. 根据产品事实先写脚本和口播，锁定受众、台词、场景和视频时长。
3. 根据人物要求、产品图、尺寸图和脚本生成真人模特首帧、产品展示图、亲子 DIY 图、开箱图或视频首尾帧，并先完成静态图验收。
4. 真人素材需要遮罩时，保留原图并生成独立的人脸处理参考图。
5. 根据预算和任务难度选择 Veo 3.1、Grok 或免费的豆包 Seedance Fast 进行图生视频。
6. 使用宫格素材制作爆款开头，再进入常规剪辑、声音和成片流程。

## 真人模特首帧模块

> **这套流程主要是图生视频，所以图决定了视频的真实感。**

我实际做下来，真人视频最不能省的就是首帧。人物的脸、皮肤、发丝、手指、嘴部遮挡、产品比例和拿产品的动作，只要在图里已经错了，Veo、Grok 或 Seedance 不会在视频里自动修好，很多时候反而会把问题放大。所以我会先把真人首帧单独做准，放大检查通过以后，才继续做人脸遮罩和图生视频。

我把目前在用的两个真人 Prompt 分开保存在英文目录 [`human-model-prompts`](./skills/facebook-diy-video-workflow/references/human-model-prompts/)，不会把它们揉成一个新 Prompt：

| 模块 | 我在什么情况下用 | 运行时还要提供什么 |
| --- | --- | --- |
| [`natural-lifestyle-first-frame-prompt.md`](./skills/facebook-diy-video-workflow/references/human-model-prompts/natural-lifestyle-first-frame-prompt.md) | 温婉、自然、非网红脸的生活化真人模特，需要根据产品调整人物和动作 | 简要人物与穿搭、人物与产品的真实动作、产品图和必要的尺寸图 |
| [`beauty-presenter-first-frame-prompt.md`](./skills/facebook-diy-video-workflow/references/human-model-prompts/beauty-presenter-first-frame-prompt.md) | 9:16 中国年轻护肤博主正面半身口播首帧，需要更细的皮肤、妆容、服装、灯光和负面限制 | `参考的妆容.jpg`、`发箍.png`、`服装.png`，以及需要同框时的产品参考 |

两个文件都保留我给出的原始文字。案例一里的“简要描述人物+穿搭”和“人物与产品的动作”由实际项目素材单独提供，不写回原文件；案例二点名的参考图缺一张，我就先补齐素材，不假装模型已经看过。最后把选中的原始 Prompt、参考图和单独提供的项目事实一起放进 GPT Web，使用 [GPT Image 2](https://developers.openai.com/api/docs/models/gpt-image-2) 出图。

首帧出来后，我会检查人脸是否自然、全身裸露皮肤质感是否统一、双手和手指是否正确、眼睛和嘴是否被挡、产品结构和尺寸是否正确、人与产品的接触关系是否成立，以及画面里有没有多余文字或界面。任何一个关键项不对，我都会先重出图，不直接进入视频阶段。

## 工具降级策略

同一套脚本与素材可以根据预算、排队时间和生成效果切换工具，而不必推翻整个流程。

| 任务 | 优先工具 | 低成本或降级方案 | Skill 负责什么 |
| --- | --- | --- | --- |
| 爆款视频拆解 | Codex / Claude | 任选可读取视频和图片的 Agent | 提取镜头、动作、节奏与可复刻结构 |
| 真人模特首帧 | GPT Web / GPT Image 2 | 补齐人物与产品参考，未通过就重出首帧 | 锁定人物、皮肤、手部、产品比例和首帧构图 |
| 复杂多场景视频 | Veo 3.1 | Grok | 输出跳切时间、多角度运镜和一致性锁定 |
| 快速图生视频 | Grok / Veo | 豆包 Seedance Fast | 压缩成物理可执行的短视频单元 |
| 人脸参考图预处理 | PromptHub 人脸工具箱 | 保留原图并生成独立遮罩图 | 保留人物、产品与台词锚点 |
| 爆款开头 | 独立宫格素材 | 从现有画面重新编排 | 拆解开头结构并组织镜头顺序 |

工具降级只改变执行工具，不改变产品事实、口播台词、尺寸关系、制作步骤和原始 Prompt。

## 人脸遮罩模块

我在 Seedance 里使用真人参考图时，会先对人脸区域做一张处理图，再把人物原图和处理图一起用于后续视频生成。我目前用的是 [PromptHub 人脸工具箱](https://prompthub.xin/lab/face-tools)，直接通过[邮箱账号登录](https://prompthub.xin/en/auth/login)，我现在使用的人脸处理功能是免费的。

我把它放在这里，只是因为我自己用下来觉得免费、顺手，不是广告，也没有赞助或商业合作。第三方网站以后可能会调整登录方式、免费范围和功能，所以还是要以网站当时的页面为准。你要上传人物素材时，也要先确认自己有权使用这些素材，并接受网站的隐私条款。

### 工具入口

进入 PromptHub 后，在“提示词工作台”中选择“人脸工具箱”。

![PromptHub 人脸工具箱入口](./docs/images/prompthub-face-tools-entry.png)

### 我现在怎么用

1. 保留未经处理的人物原图，作为人物身份、发型、服装和姿态的主参考。
2. 上传人物图，只圈选需要处理的人脸区域，不遮挡产品、双手或身体动作。
3. 根据任务选择黑色鱼线、涂抹遮罩、雾化马赛克、人脸分离或拼图等方式。
4. 下载处理结果并单独保存，不覆盖原图。
5. 在后续 Seedance 视频生成中同时提供人物原图和人脸处理图，再继续使用原始 Seedance Prompt。

![PromptHub 黑色鱼线人脸遮罩处理示例](./docs/images/prompthub-face-mask-example.png)

人脸遮罩只负责准备参考图，不负责修改产品、台词、动作、场景或视频 Prompt。

## 我踩过的坑：复杂产品真的很难生成

这个坑我在实际项目里踩过：不是所有产品都适合直接丢给 GPT Image 2 出图，再拿生成图去做视频。产品只要边边角角特别多、线路会交叉、连接关系复杂，或者有很多重复的小零件，AI 就很容易把透视和结构做错。

![复杂线路产品示例](./docs/images/complex-wired-product-example.jpg)

拿上图这种一拖二线路产品来说，它不只是两个插座这么简单。线从哪里分出去、怎么弯、怎么卷、最后接到哪里，插头和插座朝哪个方向，全部都要对。我的实际测试是，AI 可以把它做得“看起来像”，但经常会把线路接错、凭空多接一根线、把两个连接合在一起，或者做出物理上根本不成立的透视。

还有那种带很多晾衣小夹子的产品，也是同样的问题。GPT Image 2 经常连图片都生不准，小夹子的数量、方向和连接位置会乱，拿这种错误图片继续做视频，最后基本都没法用。

### 生成前我先判断这个镜头要不要做

我的原则很直接：只要镜头要求 AI 准确还原复杂线路、多个接口、大量重复零件、完整拆解过程或严格的安装顺序，我都会优先建议不做这类生成镜头。不是说完全不能抽出来，而是返工次数和生成成本通常不值得。

如果是在公司做项目，我会先把产品结构风险和后续抽卡成本说清楚，再和上级或项目负责人沟通换镜头。可以把复杂拆解改成成品结果展示、人物拿产品口播、局部细节、包装展示、旁白说明，或者直接换成真实产品素材。先把镜头目的保留下来，不一定非要让 AI 演完整个复杂过程。

即使前面的分镜图、宫格图已经生成成功，也不能说明后面的视频就能做成。静态图只需要某一帧看起来成立，图生视频却要连续保持线路走向、零件数量、接口位置、手部接触和空间透视。我的实际感受是，这一步会进入很难受的反复抽卡，首帧看着没问题，产品一动还是可能马上变形、断线、增减零件或接错结构。

### 如果一定要做，我会先转化镜头

- 我不会让 AI 在一个镜头里完成长时间拆解、组装、穿线或多个结构变化，而是优先改成“正确成品状态＋旁白说明”，把复杂过程从画面动作里拿掉。
- 必须交代操作时，我会把镜头缩到一个局部、一个接口或一个简单动作；关键结构和真实使用关系优先用实拍特写、真实产品图或人工校正素材。
- 人物、房间、氛围、包装和普通展示可以交给 AI，产品本身尽量保持静止，只做很轻的运镜和环境变化，不同时叠加复杂手部动作、产品运动和大幅运镜。
- 如果公司仍然要求生成，我会提前说明失败率和返工成本。分镜图或宫格图通过不等于视频可用，必须给后续多次抽卡留出时间和额度。
- 连续尝试仍然出现结构漂移时，我会停止这个生成分支，改用实拍、静态图轻推拉或剪辑转场，不再继续消耗视频额度。

## 能做什么

- **Facebook 熟龄口播**：根据产品图生成面向 35–45 岁北美受众的自然口播脚本。
- **真人模特首帧**：按自然生活模特或护肤博主两个独立 Prompt，用 GPT Image 2 生成并验收图生视频的人物母图。
- **DIY 视频拆解复刻**：分析参考视频中的制作步骤，生成 15 秒 Facebook AI 视频脚本。
- **亲子 DIY 图片转视频**：先用 GPT Image 2 逐张生成 3 张独立的美国家庭亲子 DIY 竖图，再生成 Veo 3.1 或 Grok 首尾帧视频提示词。
- **多场景产品展示**：口播完成后，默认生成 3 张不同场景、独立输出的 9:16 产品图。
- **第一人称开箱**：识别到开箱意图后，切换到工厂老头第一人称开箱分支。
- **Veo / Grok 视频 Prompt**：处理真人口播、人物展示、纯产品、一镜到底和多场景跳切，明确区分运镜与切镜。
- **Seedance Fast Prompt**：根据产品真实使用方法生成紧凑、连续、物理可执行的视频单元提示词。
- **人脸遮罩预处理**：在 Seedance 前生成独立的人脸遮罩参考图，并保留原图作为人物身份锚点。
- **复杂产品风险检查**：在出图前识别线路、接口、夹子、重复零件和拆解风险，默认先建议不做复杂生成镜头，并给出公司沟通、镜头转化或实拍方案。
- **电影感巨物视觉**：生成中国龙、神明、巨物、神秘存在和灾难尺度场景的图像或视频提示词。

## 适合哪些人

- 正在制作 TikTok、Facebook 或其他跨境电商带货视频的个人与团队。
- 希望通过免费或低成本工具建立稳定 AI 视频生产流程的创作者。
- 正在寻找 AI 视频制作、AIGC 内容或跨境电商素材岗位的求职者。
- 需要在短时间内完成作品集、测试片或复杂视频样片的人。

## 自动路由

`facebook-diy-video-workflow` 会根据自然语言自动选择分支：

| 用户提到 | 自动执行 |
| --- | --- |
| 真人模块、真人模特首帧、口播人物母图 | 先选择一个真人原始 Prompt，用 GPT Image 2 出图并验收，再进入视频分支 |
| `Seedance` | 优先进入 Seedance Fast 分支 |
| 人脸遮罩、黑色鱼线、涂抹遮罩、人脸分离 | 先生成独立的人脸处理参考图，再继续 Seedance 视频分支 |
| 复杂线路、多接口、大量夹子、拆解或安装过程 | 默认建议不做复杂生成镜头；公司项目先沟通换镜头，必须做时转成结果展示、局部实拍或简单动作 |
| 亲子 DIY、母女 DIY、家庭亲子手作 | 先用 GPT Image 2 生成 3 张独立竖图，再进入 Veo/Grok 首尾帧视频分支 |
| `Veo`、`Veo 3/3.1`、`Grok` | 进入 Veo/Grok 多场景连续多角度运镜分支 |
| 开箱、打开包装、unboxing | 进入工厂老头第一人称开箱分支 |
| Facebook 口播、熟龄口播、GPT 全流程 | 进入 Facebook 熟龄口播分支 |
| DIY、参考视频拆解、制作步骤复刻 | 进入 DIY 视频拆解复刻分支 |
| 口播完成且未触发开箱或视频工具分支 | 默认进入 3 张独立多场景产品展示分支 |

明确点名 Seedance 时优先执行 Seedance 分支。亲子 DIY 会覆盖普通多场景图片、开箱和直接 Veo/Grok 路由，除非用户明确要求把它们作为额外交付物。若同时明确要求 Seedance 和 Veo/Grok，Skill 会按用户指定顺序分别输出，不会合并两套原始 Prompt。

## 安装

### 让 AI 助手安装（推荐）

把下面这段话发给 Codex：

> 帮我从 GitHub 安装 AIvideo Skills：
>
> https://github.com/Longxiaohao/AIvideo
>
> 安装 `facebook-diy-video-workflow` 和 `cinematic-giant-visual-prompts`，完成后校验 Skill 并告诉我是否需要刷新会话。

### 手动安装

先克隆仓库：

```bash
git clone https://github.com/Longxiaohao/AIvideo.git
cd AIvideo
```

Windows PowerShell：

```powershell
Copy-Item -Recurse -Force .\skills\facebook-diy-video-workflow "$env:USERPROFILE\.codex\skills\facebook-diy-video-workflow"
Copy-Item -Recurse -Force .\skills\cinematic-giant-visual-prompts "$env:USERPROFILE\.codex\skills\cinematic-giant-visual-prompts"
```

macOS / Linux：

```bash
mkdir -p ~/.codex/skills
cp -R skills/facebook-diy-video-workflow ~/.codex/skills/
cp -R skills/cinematic-giant-visual-prompts ~/.codex/skills/
```

安装或更新后，刷新当前会话，让 Codex 重新发现 Skill。

## 怎么用

安装完成后直接使用自然语言，不需要手动指定参考文件。

| 你可以这样说 | Skill 会做什么 |
| --- | --- |
| 「用自然生活模特 Prompt 给这个产品做一张真人首帧」 | 要求人物穿搭与产品动作，调用案例一并先验收首帧 |
| 「用护肤博主 Prompt 做 9:16 口播人物母图」 | 检查妆容、发箍和服装参考图，调用案例二生成首帧 |
| 「根据这个产品图写一条 Facebook 熟龄口播脚本」 | 运行 GPT 全流程口播 Prompt |
| 「分析这个 DIY 参考视频并复刻制作步骤」 | 运行 DIY 视频拆解复刻 Prompt |
| 「给这个产品做亲子 DIY 场景，再用 Veo 3.1 出视频」 | 用 Image 2 逐张生成 3 张独立亲子图，再把第 1、3 张作为首尾帧生成视频 Prompt |
| 「口播完成后给产品做 3 个不同场景展示」 | 要求产品图和尺寸对照图，生成 3 张独立 9:16 图 |
| 「给这个产品做工厂第一人称开箱」 | 要求产品尺寸图和动作参考图，进入开箱分支 |
| 「把这段脚本写成 Veo 3.1 多场景视频提示词」 | 输出模式判定、锁定卡、运镜路径、时间轴和 Veo Final Prompt |
| 「给我一版 Grok 多角度产品视频提示词」 | 使用 Veo/Grok 连续多角度运镜规则 |
| 「根据真实使用方法写 Seedance 10 秒提示词」 | 优先进入 Seedance Fast 分支 |
| 「先给这张人物图做人脸遮罩，再生成 Seedance 视频」 | 保留原图，生成独立遮罩参考图后进入 Seedance 分支 |
| 「这个产品线路和接口很复杂，先判断 AI 能不能做」 | 检查拓扑、透视和重复零件风险，给出生成、拆镜或实拍方案 |
| 「生成暴雨城市中的中国龙视频提示词」 | 使用电影感巨物视觉 Skill |

也可以显式调用：

```text
Use $facebook-diy-video-workflow to turn my product facts and reference images into a Veo 3.1 prompt.
```

```text
Use $cinematic-giant-visual-prompts to create a realistic Chinese dragon video prompt.
```

## 建议提供的素材

- 产品成品图、正侧面图和细节图。
- 产品尺寸图或与手掌、人物、常见物体的尺寸对照图。
- 正确使用方法、安装顺序、接触点和动作结果。
- 爆款参考视频、视频首帧、人物母图或包装参考图。
- 真人首帧所需的简要人物与穿搭、人物与产品动作；护肤博主案例还需要妆容、发箍和服装参考图。
- 亲子 DIY 所需的产品图、尺寸图、材料包、DIY 工具和图片说明书参考图。
- 必须逐字保留的口播、旁白和声音要求。
- 目标工具、时长、画幅、场景数量和是否允许跳切。

缺少会改变产品尺寸、制作方法或关键动作的信息时，Skill 会先询问，不会自行补造。

## 项目结构

```text
AIvideo/
├── README.md
├── README.en.md
├── LICENSE
├── docs/
│   └── images/
│       ├── prompthub-face-tools-entry.png
│       ├── prompthub-face-mask-example.png
│       └── complex-wired-product-example.jpg
└── skills/
    ├── facebook-diy-video-workflow/
    │   ├── SKILL.md
    │   ├── agents/
    │   │   └── openai.yaml
    │   └── references/
    │       ├── gpt-full-workflow.md
    │       ├── video-breakdown-recreation-prompt.md
    │       ├── multi-scene-product-display-prompt.md
    │       ├── factory-old-man-unboxing-prompt.md
    │       ├── parent-child-diy-image-prompt.md
    │       ├── human-model-prompts/
    │       │   ├── natural-lifestyle-first-frame-prompt.md
    │       │   └── beauty-presenter-first-frame-prompt.md
    │       ├── face-mask-preprocessing.md
    │       ├── complex-product-generation-risks.md
    │       ├── veo-grok-multi-scene-prompt.md
    │       └── seedance-fast-10s-prompt.md
    └── cinematic-giant-visual-prompts/
        ├── SKILL.md
        ├── agents/
        │   └── openai.yaml
        └── references/
            └── original-prompt.md
```

## Prompt 完整性

下面这些参考 Prompt 都来自我实际在跑的工作流：

- [`gpt-full-workflow.md`](./skills/facebook-diy-video-workflow/references/gpt-full-workflow.md)：Facebook 熟龄口播 GPT 全流程。
- [`video-breakdown-recreation-prompt.md`](./skills/facebook-diy-video-workflow/references/video-breakdown-recreation-prompt.md)：DIY 视频拆解复刻。
- [`multi-scene-product-display-prompt.md`](./skills/facebook-diy-video-workflow/references/multi-scene-product-display-prompt.md)：3 张独立多场景产品展示。
- [`factory-old-man-unboxing-prompt.md`](./skills/facebook-diy-video-workflow/references/factory-old-man-unboxing-prompt.md)：工厂第一人称开箱。
- [`parent-child-diy-image-prompt.md`](./skills/facebook-diy-video-workflow/references/parent-child-diy-image-prompt.md)：3 张独立亲子 DIY 场景图。
- [`natural-lifestyle-first-frame-prompt.md`](./skills/facebook-diy-video-workflow/references/human-model-prompts/natural-lifestyle-first-frame-prompt.md)：温婉自然、非网红脸的真人模特首帧。
- [`beauty-presenter-first-frame-prompt.md`](./skills/facebook-diy-video-workflow/references/human-model-prompts/beauty-presenter-first-frame-prompt.md)：9:16 护肤博主真人口播首帧。
- [`veo-grok-multi-scene-prompt.md`](./skills/facebook-diy-video-workflow/references/veo-grok-multi-scene-prompt.md)：Veo/Grok 连续多角度运镜与多场景视频。
- [`seedance-fast-10s-prompt.md`](./skills/facebook-diy-video-workflow/references/seedance-fast-10s-prompt.md)：Seedance Fast 视频单元。
- [`original-prompt.md`](./skills/cinematic-giant-visual-prompts/references/original-prompt.md)：电影感巨物图像与视频提示词。

我会继续完善 Skill 外壳的触发和路由，但上面这些参考 Prompt 默认都是不能改写的原始文本。

人脸遮罩与复杂产品风险属于操作模块，不会改写上述实践 Prompt：

- [`face-mask-preprocessing.md`](./skills/facebook-diy-video-workflow/references/face-mask-preprocessing.md)：人脸参考图预处理流程。
- [`complex-product-generation-risks.md`](./skills/facebook-diy-video-workflow/references/complex-product-generation-risks.md)：复杂产品可生成性检查与降级规则。

## 仓库边界

仓库只保留 Skill 运行所需的指令、Prompt，以及经用户明确授权公开的文档示例图。其他产品图、参考视频、生成图片、分析缓存或压缩包不提交；实际客户素材在运行时作为附件提供，避免把客户资产公开到 GitHub。

## 贡献

欢迎通过 [Issues](https://github.com/Longxiaohao/AIvideo/issues) 提交新的视频工具触发分支、真实失败案例、路由改进建议，以及 Skill 安装和兼容问题。

## License

MIT，详见 [LICENSE](./LICENSE)。
