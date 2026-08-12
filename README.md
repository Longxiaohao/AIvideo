<div align="center">

# 跨境电商 AI 带货视频制作

**一套面向低成本、复杂 AI 带货视频制作的 Codex Skills 与实战 Prompt SOP。**

先写脚本与口播，再出图、图生视频、处理人脸遮罩、制作爆款开头，并通过 Codex 或 Claude 拆解参考视频。

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
    C --> D["Veo / Grok / Seedance<br/>图生视频"]
    D --> E["豆包人脸遮罩"]
    E --> F["宫格爆款开头"]
    F --> G["剪辑与成片"]
```

1. 使用 Codex 或 Claude 拆解爆款参考视频，提取开头结构、镜头、制作动作和节奏。
2. 根据产品事实先写脚本和口播，锁定受众、台词、场景和视频时长。
3. 根据产品图、尺寸图和脚本生成产品展示图、亲子 DIY 图、开箱图或视频首尾帧。
4. 根据预算和任务难度选择 Veo 3.1、Grok 或免费的豆包 Seedance Fast 进行图生视频。
5. 使用豆包人脸遮罩处理人物一致性或局部画面问题。
6. 使用宫格素材制作爆款开头，再进入常规剪辑、声音和成片流程。

## 工具降级策略

同一套脚本与素材可以根据预算、排队时间和生成效果切换工具，而不必推翻整个流程。

| 任务 | 优先工具 | 低成本或降级方案 | Skill 负责什么 |
| --- | --- | --- | --- |
| 爆款视频拆解 | Codex / Claude | 任选可读取视频和图片的 Agent | 提取镜头、动作、节奏与可复刻结构 |
| 复杂多场景视频 | Veo 3.1 | Grok | 输出跳切时间、多角度运镜和一致性锁定 |
| 快速图生视频 | Grok / Veo | 豆包 Seedance Fast | 压缩成物理可执行的短视频单元 |
| 真人画面修正 | 豆包人脸遮罩 | 回到首帧或人物母图重新生成 | 保留人物、产品与台词锚点 |
| 爆款开头 | 独立宫格素材 | 从现有画面重新编排 | 拆解开头结构并组织镜头顺序 |

工具降级只改变执行工具，不改变产品事实、口播台词、尺寸关系、制作步骤和原始 Prompt。

## 能做什么

- **Facebook 熟龄口播**：根据产品图生成面向 35–45 岁北美受众的自然口播脚本。
- **DIY 视频拆解复刻**：分析参考视频中的制作步骤，生成 15 秒 Facebook AI 视频脚本。
- **亲子 DIY 图片转视频**：先用 GPT Image 2 逐张生成 3 张独立的美国家庭亲子 DIY 竖图，再生成 Veo 3.1 或 Grok 首尾帧视频提示词。
- **多场景产品展示**：口播完成后，默认生成 3 张不同场景、独立输出的 9:16 产品图。
- **第一人称开箱**：识别到开箱意图后，切换到工厂老头第一人称开箱分支。
- **Veo / Grok 视频 Prompt**：处理真人口播、人物展示、纯产品、一镜到底和多场景跳切，明确区分运镜与切镜。
- **Seedance Fast Prompt**：根据产品真实使用方法生成紧凑、连续、物理可执行的视频单元提示词。
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

## 仓库边界

仓库只保留 Skill 运行所需的指令和 Prompt，不提交产品图、参考视频、生成图片、分析缓存或压缩包。实际素材在运行时作为附件提供，避免把客户产品和项目资产公开到 GitHub。

## 贡献

欢迎通过 [Issues](https://github.com/Longxiaohao/AIvideo/issues) 提交新的视频工具触发分支、真实失败案例、路由改进建议，以及 Skill 安装和兼容问题。

## License

MIT，详见 [LICENSE](./LICENSE)。
