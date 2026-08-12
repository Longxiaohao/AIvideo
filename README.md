<div align="center">

# 跨境电商 AI 带货视频制作

**一套面向低成本、复杂 AI 带货视频制作的 Codex Skills 与实战 Prompt SOP。**

先写脚本与口播，再出图、处理人脸遮罩参考图、图生视频、制作爆款开头，并通过 Codex 或 Claude 拆解参考视频。

[![GitHub stars](https://img.shields.io/github/stars/Longxiaohao/AIvideo?style=flat-square)](https://github.com/Longxiaohao/AIvideo/stargazers)
[![License](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](./LICENSE)
[![Codex Skills](https://img.shields.io/badge/Codex-Skills-black.svg?style=flat-square)](./skills)
[![Video Tools](https://img.shields.io/badge/video-Veo%20%7C%20Grok%20%7C%20Seedance-orange.svg?style=flat-square)](#自动路由)

**中文** | [English](./README.en.md)

</div>

---

## 为什么做这个项目

现在制作跨境电商带货视频，最大的现实问题不是缺少模型，而是如何用更低的成本稳定做出可用效果。商业工具并不总是必要条件：免费的豆包 Seedance Fast，以及 Grok、Veo 等现有工具，已经足以覆盖脚本、画面和视频生成中的大量工作。

这套 Skills 把实际操作中成熟的 Prompt 和路由规则整理成一套可复用 SOP。它主要服务两类人：需要低成本批量制作跨境电商视频的创作者，以及仍在寻找 AI 视频制作岗位、希望快速建立作品和工作流经验的求职者。

完成素材准备后，这套 SOP 可以灵活组合不同工具，并在 1 小时内完成一条结构较复杂的 AI 带货视频。这里的“1 小时”是工作流目标，不是对所有产品、网络环境和生成队列的固定承诺。

本仓库保留作者实际使用的原始 Prompt。Skill 只负责任务识别、输入检查和分支调度，不对实践 Prompt 做二创、压缩或改写。

## 核心工作流

```mermaid
flowchart LR
    A["Codex / Claude<br/>拆解爆款视频"] --> B["脚本与口播"]
    B --> C["产品图与场景图"]
    C --> D["人脸遮罩<br/>参考图预处理"]
    D --> E["Veo / Grok / Seedance<br/>图生视频"]
    E --> F["宫格爆款开头"]
    F --> G["剪辑与成片"]
```

1. 使用 Codex 或 Claude 拆解爆款参考视频，提取开头结构、镜头、制作动作和节奏。
2. 根据产品事实先写脚本和口播，锁定受众、台词、场景和视频时长。
3. 根据产品图、尺寸图和脚本生成产品展示图、亲子 DIY 图、开箱图或视频首尾帧。
4. 真人素材需要遮罩时，保留原图并生成独立的人脸处理参考图。
5. 根据预算和任务难度选择 Veo 3.1、Grok 或免费的豆包 Seedance Fast 进行图生视频。
6. 使用宫格素材制作爆款开头，再进入常规剪辑、声音和成片流程。

## 工具降级策略

同一套脚本与素材可以根据预算、排队时间和生成效果切换工具，而不必推翻整个流程。

| 任务 | 优先工具 | 低成本或降级方案 | Skill 负责什么 |
| --- | --- | --- | --- |
| 爆款视频拆解 | Codex / Claude | 任选可读取视频和图片的 Agent | 提取镜头、动作、节奏与可复刻结构 |
| 复杂多场景视频 | Veo 3.1 | Grok | 输出跳切时间、多角度运镜和一致性锁定 |
| 快速图生视频 | Grok / Veo | 豆包 Seedance Fast | 压缩成物理可执行的短视频单元 |
| 人脸参考图预处理 | PromptHub 人脸工具箱 | 保留原图并生成独立遮罩图 | 保留人物、产品与台词锚点 |
| 爆款开头 | 独立宫格素材 | 从现有画面重新编排 | 拆解开头结构并组织镜头顺序 |

工具降级只改变执行工具，不改变产品事实、口播台词、尺寸关系、制作步骤和原始 Prompt。

## 人脸遮罩模块

当 Seedance 使用真人参考图时，可以先对人脸区域进行参考图预处理，再把原图与处理图一起用于后续视频生成。本项目推荐使用 [PromptHub 人脸工具箱](https://prompthub.xin/lab/face-tools)：作者目前通过[邮箱账号登录](https://prompthub.xin/en/auth/login)使用其中的免费人脸处理功能。

这只是作者认为免费且好用的工具自荐，不是广告、赞助或商业合作。第三方网站的登录方式、免费范围和功能可能随时调整，请以网站实际页面为准。将人物素材上传到外部网站前，应确认自己拥有使用权限并接受对应隐私条款。

### 工具入口

进入 PromptHub 后，在“提示词工作台”中选择“人脸工具箱”。

![PromptHub 人脸工具箱入口](./docs/images/prompthub-face-tools-entry.png)

### 操作流程

1. 保留未经处理的人物原图，作为人物身份、发型、服装和姿态的主参考。
2. 上传人物图，只圈选需要处理的人脸区域，不遮挡产品、双手或身体动作。
3. 根据任务选择黑色鱼线、涂抹遮罩、雾化马赛克、人脸分离或拼图等方式。
4. 下载处理结果并单独保存，不覆盖原图。
5. 在后续 Seedance 视频生成中同时提供人物原图和人脸处理图，再继续使用原始 Seedance Prompt。

![PromptHub 黑色鱼线人脸遮罩处理示例](./docs/images/prompthub-face-mask-example.png)

人脸遮罩只负责准备参考图，不负责修改产品、台词、动作、场景或视频 Prompt。

## 实际项目经验：复杂产品的 AI 生成边界

实际项目中，并不是所有产品都适合直接使用 GPT Image 2 出图再做图生视频。边边角角很多、线路交叉、连接关系复杂、重复小零件数量多的产品，很容易在生成时出现透视、拓扑和结构错误。

![复杂线路产品示例](./docs/images/complex-wired-product-example.jpg)

以上双分支线路产品同时包含线缆路径、多个弯曲与卷绕区域、分支关系、插头、插座和明确连接点。AI 可以简单展示外观，但经常会改错线路去向、合并或新增连接、改变接口方向，或者生成物理上无法成立的透视。类似风险也常见于带有大量晾衣小夹子、挂钩、齿、环或重复固定件的产品：一个零件数量或连接关系错误，就会让整条视频无法使用。

### 生成前检查

- 记录准确的线路路径、分支数量、端点、接口方向、重复零件数量、产品尺寸和正确使用状态。
- 第一张生成图必须放大检查，结构不对就不能继续做图生视频。
- 不要指望运镜遮住错误；视频模型通常会保留或放大首帧中的结构问题。

### 推荐降级方案

- 关键产品镜头使用真实产品图、实拍视频或人工校正的合成图，只让 AI 生成轻微运镜和环境变化。
- 把复杂使用过程拆成多个局部特写，每个镜头只展示一个接口、一段线路、一组夹子或一个动作。
- 人物、房间、氛围和包装镜头可以由 AI 生成；线路、结构和使用关系必须精确的镜头优先保留真实素材。
- 若所有生成图都无法通过结构检查，就停止该生成分支，改用实拍，不继续消耗视频生成额度。

## 能做什么

- **Facebook 熟龄口播**：根据产品图生成面向 35–45 岁北美受众的自然口播脚本。
- **DIY 视频拆解复刻**：分析参考视频中的制作步骤，生成 15 秒 Facebook AI 视频脚本。
- **亲子 DIY 图片转视频**：先用 GPT Image 2 逐张生成 3 张独立的美国家庭亲子 DIY 竖图，再生成 Veo 3.1 或 Grok 首尾帧视频提示词。
- **多场景产品展示**：口播完成后，默认生成 3 张不同场景、独立输出的 9:16 产品图。
- **第一人称开箱**：识别到开箱意图后，切换到工厂老头第一人称开箱分支。
- **Veo / Grok 视频 Prompt**：处理真人口播、人物展示、纯产品、一镜到底和多场景跳切，明确区分运镜与切镜。
- **Seedance Fast Prompt**：根据产品真实使用方法生成紧凑、连续、物理可执行的视频单元提示词。
- **人脸遮罩预处理**：在 Seedance 前生成独立的人脸遮罩参考图，并保留原图作为人物身份锚点。
- **复杂产品风险检查**：在出图前识别线路、接口、夹子和重复零件风险，决定生成、拆镜或实拍降级方案。
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
| `Seedance` | 优先进入 Seedance Fast 分支 |
| 人脸遮罩、黑色鱼线、涂抹遮罩、人脸分离 | 先生成独立的人脸处理参考图，再继续 Seedance 视频分支 |
| 复杂线路、多接口、大量夹子或重复零件 | 先执行复杂产品风险检查，未通过结构验收时切换实拍或拆镜方案 |
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

本仓库中的参考 Prompt 来自作者实际工作流：

- [`gpt-full-workflow.md`](./skills/facebook-diy-video-workflow/references/gpt-full-workflow.md)：Facebook 熟龄口播 GPT 全流程。
- [`video-breakdown-recreation-prompt.md`](./skills/facebook-diy-video-workflow/references/video-breakdown-recreation-prompt.md)：DIY 视频拆解复刻。
- [`multi-scene-product-display-prompt.md`](./skills/facebook-diy-video-workflow/references/multi-scene-product-display-prompt.md)：3 张独立多场景产品展示。
- [`factory-old-man-unboxing-prompt.md`](./skills/facebook-diy-video-workflow/references/factory-old-man-unboxing-prompt.md)：工厂第一人称开箱。
- [`parent-child-diy-image-prompt.md`](./skills/facebook-diy-video-workflow/references/parent-child-diy-image-prompt.md)：3 张独立亲子 DIY 场景图。
- [`veo-grok-multi-scene-prompt.md`](./skills/facebook-diy-video-workflow/references/veo-grok-multi-scene-prompt.md)：Veo/Grok 连续多角度运镜与多场景视频。
- [`seedance-fast-10s-prompt.md`](./skills/facebook-diy-video-workflow/references/seedance-fast-10s-prompt.md)：Seedance Fast 视频单元。
- [`original-prompt.md`](./skills/cinematic-giant-visual-prompts/references/original-prompt.md)：电影感巨物图像与视频提示词。

Skill 外壳可以继续完善触发和路由，但上述参考 Prompt 默认视为不可改写的原始文本。

人脸遮罩与复杂产品风险属于操作模块，不会改写上述实践 Prompt：

- [`face-mask-preprocessing.md`](./skills/facebook-diy-video-workflow/references/face-mask-preprocessing.md)：人脸参考图预处理流程。
- [`complex-product-generation-risks.md`](./skills/facebook-diy-video-workflow/references/complex-product-generation-risks.md)：复杂产品可生成性检查与降级规则。

## 仓库边界

仓库只保留 Skill 运行所需的指令、Prompt，以及经用户明确授权公开的文档示例图。其他产品图、参考视频、生成图片、分析缓存或压缩包不提交；实际客户素材在运行时作为附件提供，避免把客户资产公开到 GitHub。

## 贡献

欢迎通过 [Issues](https://github.com/Longxiaohao/AIvideo/issues) 提交新的视频工具触发分支、真实失败案例、路由改进建议，以及 Skill 安装和兼容问题。

## License

MIT，详见 [LICENSE](./LICENSE)。
