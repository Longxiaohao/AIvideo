# Ecommerce AI Workflow Skills

面向 AI 电商视频与视觉提示词的 Codex Skill 集合。仓库仅保留 Skill 运行所需的指令和作者实践 Prompt，不包含产品图、参考视频、生成图片、分析缓存或压缩包。

## Skills

### Facebook DIY Video Workflow

从产品图生成 Facebook 熟龄口播脚本，或分析 DIY 参考视频并生成 15 秒拆解复刻脚本。

路径：`skills/facebook-diy-video-workflow`

### Cinematic Giant Visual Prompts

生成巨物、中国龙、神明、神秘存在和灾难尺度场景的写实电影感图像或视频提示词。

路径：`skills/cinematic-giant-visual-prompts`

## 安装

将需要的 Skill 目录放入 Codex Skill 目录：

```text
~/.codex/skills/<skill-name>
```

## Prompt 完整性

- `gpt-full-workflow.md` 直接复制自作者指定的 `流程1-Facebook熟龄口播脚本(改进版).md`。
- `video-breakdown-recreation-prompt.md` 按作者提供的原始文本收录。
- `original-prompt.md` 直接复制自原有的电影感巨物 Prompt。
- Skill 只负责触发、路由和输入要求，不改写上述实践 Prompt。

## License

[MIT](LICENSE)
