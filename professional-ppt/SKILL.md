---
name: professional-ppt
description: "使用 Nano Banana Pro 服务生成专业的 PPT"
license: MIT
metadata:
  version: "0.3"
  category: productivity
  sources:
    - https://github.com/shenxy/skills/professional-ppt
  openclaw: {}
---

# 专业 PPT 生成

## 简介

本技能根据用户提供的内容，使用 Nano Banana Pro 服务生成专业的 PPT（pptx 文件）。

## 工作流程

### 第1步: 获取 PPT 内容

如果用户没有提供 PPT 的内容，或者提供的信息不明确，请主动提问澄清，不要自己编造内容。

### 第2步: 规划 PPT 大纲

请根据用户提供的主题和内容规划 PPT 的大纲（各页面的标题和内容）。

每页的内容要完整、清晰，以便后续步骤能生成高质量的 PPT 页面。除非必要，内容请始终使用中文。

除非内容只有 1 页，否则都要在第 1 页增加标题页，包含 PPT 的标题、日期等信息；在最后增加致谢页，感谢观众的聆听。

### 第3步: 确定 PPT 风格

除非用户特别指定风格，否则所有页面都使用以下风格：
1. 总体风格可以参考 McKinsey/BCG 的风格，布局清晰、专业、简洁，不需要背景图片，不需要周边装饰元素，不需要页码、不需要公司名称或 logo;
2. 使用白色背景、深色（#333333）文本、蓝色（#1F3F87）点缀、红色（#C13324）强调的配色方案;
3. 选择简洁现代的字体（如Arial、微软雅黑），标题加粗，正文常规字体（不加粗）;

除非用户特别指定风格，所有内容页面（除了标题页和致谢页）都使用以下风格：
1. 顶部标题行使用较大字号（如 36pt）并且加粗，正文使用较小字号（如 24-28pt）;
2. 顶部标题行文字前添加蓝色（#1F3F87）粗竖条 "▌" 作为视觉标识;
3. 不需要副标题;
4. Use FIGURATIVE ILLUSTRATIONS (people, robots, scenes, objects, icons) to represent roles and relationships. Minimal text, maximum visual storytelling;

### 第4步: 生成 PPT 页面

调用 Nano Banana Pro 服务生成每个 PPT 页面图。（如果没有安装 nano-banana-pro 技能，请先安装并配置好 API Key。）

在生成每个页面（除了标题页和致谢页）时，要告知 Nano Banana Pro 以下内容：
1. 页面的标题、内容;
2. 前面第 3 步确定的设计风格、配色方案和字体;
3. 生成 2K 分辨率、16:9 比例的 PPT 页面图像。

如果可用，使用 subagents 来并行生成 PPT 页面图，最多 5 个并行。

### 第5步: 质量检查（强制执行）

检查生成的每个 PPT 页面图，确保内容完整且设计符合要求。如果发现问题，请重新生成有问题的页面图。

### 第6步: 合并生成 PPT 文件

将生成的所有 PPT 页面图合并成一个完整的 pptx 文件。

### 第7步: 提供下载链接

将生成的 pptx 文件拷贝到桌面，并提供下载链接给用户。