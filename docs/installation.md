# 安装与连接

**简体中文** · [English](en/installation.md)

[返回首页](../README.md) · [快速开始](quick-start.md) · [常见问题](faq.md)

## 环境要求

- Node.js 20.19.0 或更高版本，客户端能找到 `node` 和 `npx`。
- Qoder 或支持 stdio MCP 的客户端。
- Chrome、Chromium、Edge 或 Brave，用于截图和合图。
- Figma 或 Sketch，与客户端运行在同一台机器上。
- 首次启动需要访问 npm 公共仓库。

## Qoder 插件

1. 打开 [Tarot Pixel 插件页面](https://qoder.com/zh/marketplace/plugin?id=tarot-pixel)，按指引安装。
2. 在 Qoder 任务中启用 Tarot Pixel。
3. 保持 Qoder 运行，前往设计工具同步设计。

## Figma 插件

1. 在 [Figma Community](https://www.figma.com/community/plugin/1635645029043726171) 中打开 Tarot Pixel。
2. 选择目标 Frame 或图层，运行插件。
3. 点击“同步设计稿”，打开返回的链接查看设计。

## Sketch 插件

支持 Sketch 80.0 及以上。

1. [下载插件 ZIP](https://unpkg.com/@tarot-ai/tarot-pixel-sketch-release@latest/Tarot-Pixel.sketchplugin.zip)并解压。
2. 双击 `.sketchplugin` 文件完成安装。
3. 选择画板或图层，运行 Tarot Pixel，点击“同步设计稿”。

## 直接配置 MCP

使用其他兼容客户端时，在 MCP 配置中添加：

```json
{
  "mcpServers": {
    "tarot-pixel": {
      "type": "stdio",
      "command": "npx",
      "args": ["--yes", "--package=@tarot-ai/pixel@latest", "--", "tarot-pixel"]
    }
  }
}
```

已有 MCP 配置时，只添加 `tarot-pixel` 条目。已启用 Qoder 插件时，无需重复配置。

[开始同步设计 →](quick-start.md) · [连接问题排查](faq.md)
