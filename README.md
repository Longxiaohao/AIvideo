<div align="center">

# 跨境电商AI带货视频制作

**面向电商短视频创作的 Codex Skills 与实战 Prompt 工作流。**

从 Facebook 熟龄口播、DIY 视频拆解、多场景产品展示和第一人称开箱，到 Veo 3/3.1、Grok、Seedance Fast 视频提示词，以及电影感巨物视觉提示词，按用户意图自动路由到对应工作流。

本仓库保留作者实际使用的原始 Prompt。Skill 只负责任务识别、输入检查和分支调度，不对实践 Prompt 做二创、压缩或改写。

[![GitHub stars](https://img.shields.io/github/stars/Longxiaohao/AIvideo?style=flat)](https://github.com/Longxiaohao/AIvideo/stargazers)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](./LICENSE)
[![Codex Skills](https://img.shields.io/badge/Codex-Skills-black.svg)](./skills)
[![Video Tools](https://img.shields.io/badge/video-Veo%20%7C%20Grok%20%7C%20Seedance-orange.svg)](#自动路由)

</div>

---

## 能做什么

- **Facebook 熟龄口播**：根据产品图生成面向 35–45 岁北美受众的自然口播脚本。
- **DIY 视频拆解复刻**：分析参考视频中的制作步骤，生成 15 秒 Facebook AI 视频脚本。
- **多场景产品展示**：口播完成后，默认生成 3 张不同场景、独立输出的 9:16 产品图。
- **第一人称开箱**：识别到开箱意图后，切换到工厂老头第一人称开箱分支。
- **Veo / Grok 视频 Prompt**：处理真人口播、人物展示、纯产品、一镜到底和多场景跳切，明确区分运镜与切镜。
- **Seedance Fast Prompt**：根据产品真实使用方法生成紧凑、连续、物理可执行的视频单元提示词。
- **电影感巨物视觉**：生成中国龙、神明、巨物、神秘存在和灾难尺度场景的图像或视频提示词。

## 适合哪些场景

| 场景 | 对应能力 | 关键输入 |
| --- | --- | --- |
| Facebook 商品口播 | 熟龄口播脚本 | 产品成品图、产品事实、目标时长 |
| DIY 套件短视频 | 参考视频拆解复刻 | 产品图、参考视频、真实制作方法 |
| 口播后的产品陈列 | 3 张独立多场景展示图 | 产品图、尺寸对照图 |
| 工厂开箱画面 | 第一人称开箱分支 | 图一产品与尺寸、图二至图四动作参考 |
| Veo 3 / 3.1 或 Grok 视频 | 连续多角度运镜或多场景跳切 | 首帧、产品图、尺寸图、台词、动作、时长 |
| Seedance Fast 视频 | 真实手机感动作单元 | 产品图、正确使用方法、时长、画幅 |
| 巨物、神明、中国龙画面 | 电影感图像或视频 Prompt | 主体、现实场景、画幅、运动要求 |

## 自动路由

`facebook-diy-video-workflow` 会根据自然语言自动选择分支：

| 用户提到 | 自动执行 |
| --- | --- |
| `Seedance` | 优先进入 Seedance Fast 分支 |
| `Veo`、`Veo 3/3.1`、`Grok` | 进入 Veo/Grok 多场景连续多角度运镜分支 |
| 开箱、打开包装、unboxing | 进入工厂老头第一人称开箱分支 |
| Facebook 口播、熟龄口播、GPT 全流程 | 进入 Facebook 熟龄口播分支 |
| DIY、参考视频拆解、制作步骤复刻 | 进入 DIY 视频拆解复刻分支 |
| 口播完成且未触发开箱或视频工具分支 | 默认进入 3 张独立多场景产品展示分支 |

如果同时明确要求 Seedance 和 Veo/Grok，Skill 会按用户指定顺序分别输出，不会合并两套原始 Prompt。

## 安装

### 方式一：让 AI 助手安装（推荐）

把下面这段话发给 Codex：

> 帮我从 GitHub 安装 AIvideo Skills：
>
> https://github.com/Longxiaohao/AIvideo
>
> 安装 `facebook-diy-video-workflow` 和 `cinematic-giant-visual-prompts`，完成后校验 Skill 并告诉我是否需要刷新会话。

### 方式二：手动安装

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
- 视频首帧、人物母图或包装参考图。
- 必须逐字保留的口播、旁白和声音要求。
- 目标工具、时长、画幅、场景数量和是否允许跳切。
- DIY 任务中的参考视频和经过确认的真实制作步骤。

缺少会改变产品尺寸、制作方法或关键动作的信息时，Skill 会先询问，不会自行补造。

## 项目结构

```text
AIvideo/
├── README.md
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
- [`veo-grok-multi-scene-prompt.md`](./skills/facebook-diy-video-workflow/references/veo-grok-multi-scene-prompt.md)：Veo/Grok 连续多角度运镜与多场景视频。
- [`seedance-fast-10s-prompt.md`](./skills/facebook-diy-video-workflow/references/seedance-fast-10s-prompt.md)：Seedance Fast 视频单元。
- [`original-prompt.md`](./skills/cinematic-giant-visual-prompts/references/original-prompt.md)：电影感巨物图像与视频提示词。

Skill 外壳可以继续完善触发和路由，但上述参考 Prompt 默认视为不可改写的原始文本。

## 仓库边界

仓库只保留 Skill 运行所需的指令和 Prompt，不提交产品图、参考视频、生成图片、分析缓存或压缩包。实际素材在运行时作为附件提供，避免把客户产品和项目资产公开到 GitHub。

## 贡献

欢迎通过 [Issues](https://github.com/Longxiaohao/AIvideo/issues) 提交：

- 新的视频工具触发分支。
- 产品一致性、运镜和多场景生成中的真实失败案例。
- 不修改原始 Prompt 前提下的路由改进建议。
- Skill 安装、识别和跨平台兼容问题。

## License

MIT，详见 [LICENSE](./LICENSE)。
