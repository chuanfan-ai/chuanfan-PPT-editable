# chuanfan-PPT-editable

一个面向 Codex 的 PPT 生成 skill，用来制作高审美、中文优先、尽量可编辑的演示文稿。

它的目标是把两类能力合在一起：

- **HTML-first 高保真设计流程**：先做浏览器可演示的 deck，再按需要导出 PDF / PPTX。
- **更强的 PPT 审美与版式系统**：吸收瑞士风、电子杂志风、商务汇报和课程课件的设计规则。
- **可编辑 PPTX 优先级**：标题、正文、标签、结构图文字尽量保留为 PowerPoint 可编辑对象。
- **内容驱动配图**：根据内容判断是否需要真实素材、结构图、信息图或 AI 生成图，不默认堆装饰图。
- **视觉锚点与主体抠图**：品牌案例优先找 logo、角色、产品、包装等标志物，LABUBU、雪王、红包、CS50 Duck 这类素材优先抠成透明 PNG 后参与排版。
- **候选池式配图流程**：逐页生成搜索关键词，真实搜图和 AI 生图双通道获取素材，经过相关性与质量过滤后，再由版式阶段决定最终使用的图片。

## 适合什么场景

- 中文 PPT / 幻灯片 / deck
- AI、科技、教育、商业汇报
- 课程课件、讲座分享、路演稿
- 希望比普通 PPT 生成器更有审美，同时又希望 PPTX 能编辑
- 希望融合 `huashu-design` 的 HTML 高保真思路和 `guizang-ppt-skill` 的演示风格

## 不适合什么场景

- 只想要完全传统、无设计感的公司模板填空
- 需要 100% 像素级还原 HTML 到可编辑 PPTX
- 需要大量 Excel 式表格维护的重数据文档
- 没有人工复核就直接对外发布的严肃事实报告

## 安装

用 Codex 的 skill installer 从 GitHub 安装：

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo chuanfan-ai/chuanfan-PPT-editable \
  --path . \
  --name chuanfan-ppt-editable
```

安装后重启 Codex，让新 skill 被加载。

## 调用示例

```text
用 chuanfan-PPT-editable 做一份 6 页 PPT，主题是高校如何拥抱 AI
```

```text
用 chuanfan-PPT-editable 根据这份资料做一份路演 deck，需要可编辑 PPTX
```

```text
用 chuanfan-PPT-editable 做一份瑞士风的 AI 教育政策分享 PPT，控制在 8 页
```

## 工作流

这个 skill 默认按以下顺序工作：

1. 判断主题、受众、资料来源和最终格式。
2. 把内容整理成页级叙事表。
3. 根据内容选择视觉系统：瑞士风、电子杂志风、商务汇报或课程课件。
4. 逐页判断视觉锚点：真实图片、logo、标志物、主体抠图、结构图、AI 概念图或纯文字。
5. 为需要配图的页面生成 1-3 个搜索关键词和必要的 AI 生图提示词。
6. 用真实搜图和 AI 生图双通道建立候选图片池。
7. 对候选图片做相关性过滤和质量过滤。
8. 在版式设计阶段选择 `selected_images`，不把搜索结果直接塞进页面。
9. 先做 HTML deck 作为源文件。
10. 按需要导出 PDF / 可编辑 PPTX。
11. 检查页面、配图、文字溢出、PPTX 可编辑性和导出结果。

## 文件说明

```text
chuanfan-ppt-editable/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── style-system.md
    ├── editable-pptx-rules.md
    ├── image-policy.md
    └── quality-checklist.md
```

- `SKILL.md`：Codex 触发和执行这个 skill 的主规则。
- `style-system.md`：不同内容场景下的风格选择。
- `editable-pptx-rules.md`：从 HTML 到可编辑 PPTX 时要遵守的约束。
- `image-policy.md`：配图、真实素材和 AI 生成图的判断规则。
- `quality-checklist.md`：交付前检查清单。

## 设计原则

- 内容决定风格，不先套模板。
- HTML/PDF 负责完整视觉效果，PPTX 负责可编辑和实用。
- 图片必须服务信息，不做无意义装饰。
- 品牌案例先找最小但最有识别度的视觉锚点，不机械塞大图。
- 角色、产品、包装、红包等素材优先做透明背景主体抠图。
- 搜图结果和 AI 生图结果必须先进候选池，经过相关性和视觉质量过滤后才可进入页面。
- 最终用哪张图由版式决定；没有合格图片时宁可用结构图、纯文字或无图。
- 真实学校、品牌、产品、人物和数据要优先使用真实来源。
- 可编辑文字优先于把整页截图塞进 PPTX。
