# 快速开始

**简体中文** · [English](en/quick-start.md)

[返回首页](../README.md) · [安装指南](installation.md) · [常见问题](faq.md)

准备 Node.js 20.19.0 或更高版本，以及 Chrome、Chromium、Edge 或 Brave。Qoder 与设计工具应运行在同一台机器上。

## 1. 启用 Tarot Pixel

在 [Qoder 插件市场](https://qoder.com/zh/marketplace/plugin?id=tarot-pixel)安装 Tarot Pixel，并在任务中启用。其他 MCP 客户端的接入方式见[安装指南](installation.md#直接配置-mcp)。

## 2. 同步设计

1. 安装 [Figma 插件](https://www.figma.com/community/plugin/1635645029043726171)或 [Sketch 插件](https://unpkg.com/@tarot-ai/tarot-pixel-sketch-release@latest/Tarot-Pixel.sketchplugin.zip)。
2. 保持 Qoder 运行，在设计工具中选中目标 Frame、画板或图层，打开 Tarot Pixel。
3. 点击“同步设计稿”。完成后打开返回的链接，查看设计并复制完整地址。

设计修改后，重新同步即可更新数据。

## 3. 交给 Qoder

打开你的前端项目，发送设计链接与需求：

```text
请使用 Tarot Pixel 实现这个设计：<同步后的完整设计链接>。
目标是「商品卡片」模块，复用当前项目已有组件和样式规范。
标题、价格和按钮支持动态内容，图片保存到项目资源目录。
完成后运行页面，对照设计稿修正细节。
```

发现偏差后，可以继续对话：

```text
按钮与价格之间的间距偏大，卡片圆角也不一致。
请回查对应节点的布局和样式，修正后再预览一次。
```

[更多使用场景与提示词 →](workflow.md)
