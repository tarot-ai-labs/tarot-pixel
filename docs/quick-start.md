# 快速开始

**简体中文** · [English](en/quick-start.md)

[返回首页](../README.md) · [安装指南](installation.md) · [遇到问题](faq.md)

目标：同步一个小组件，让 Agent 在你的项目里实现，并完成一次视觉核对。

## 1. 准备环境

- 一个支持 stdio MCP 的 Coding Agent 客户端；Qoder 可使用 Tarot Pixel 插件。
- Node.js 20.19.0 或更高版本。
- 本机安装 Chrome、Chromium、Edge 或 Brave，用于截图和合图。
- Figma 或 Sketch 中的一张卡片、一个按钮组或其他小模块。

## 2. 连接 Tarot Pixel

在 [Qoder 插件市场](https://qoder.com/zh/marketplace/plugin?id=tarot-pixel)安装并启用 Tarot Pixel。使用其他 MCP 客户端，或希望直接配置 MCP 时，添加以下服务：

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

示例使用 npm 当前最新发布版本 `latest`。首次启动需要访问 npm；客户端负责启动服务，无需额外在终端常驻运行同一实例。已有其他 MCP 配置时，只合并 `tarot-pixel` 条目。不同客户端的配置入口和字段可能不同，详见[安装指南](installation.md)。

让 Agent 检查连接：

```text
请调用 Tarot Pixel 的 server_status，确认本地 View 已就绪，
再调用 design_list 查看当前设计稿。首次使用时列表为空是正常的。
```

`server_status` 的 `view.ready` 应为 `true`。如果连接或 View 未就绪，先按[常见问题](faq.md)排查。

## 3. 同步设计

1. 安装 [Figma 插件](https://www.figma.com/community/plugin/1635645029043726171)或 [Sketch 插件](https://unpkg.com/@tarot-ai/tarot-pixel-sketch-release@latest/Tarot-Pixel.sketchplugin.zip)。
2. 在设计工具中选中目标 Frame、画板或图层，打开 Tarot Pixel。
3. 点击“同步设计稿”，等待同步完成。
4. 打开或复制插件返回的完整本地链接，在 View 中确认目标模块和图层已出现。

设计工具与 Runtime 应运行在同一台机器上。链接通常形如 `http://127.0.0.1:18276/design/<designId>`，以同步返回的实际地址为准。

## 4. 在项目中实现

打开要修改的前端项目，把下面的提示词发送给 Agent，并替换链接和组件名：

```text
请使用 Tarot Pixel 实现这个设计：<同步后的完整设计链接>。
目标是「商品卡片」模块。

先阅读当前项目，复用已有组件、样式规范和资源目录。
通过设计概览定位模块，按需读取节点的布局、样式和图片信息。
标题、价格和按钮保留为可变内容，复杂装饰可以使用合图。
生成的资源保存到当前项目管理的资源目录，再由业务代码引用。
完成后运行项目，在对应视口下预览并对照设计稿，修正主要视觉偏差。
```

## 5. 完成一次修正

指出你观察到的偏差，让 Agent 回查对应设计数据：

```text
按钮与价格之间的间距偏大，卡片背景的圆角也不一致。
请查询对应节点的布局和样式后修正，再预览一次。
```

完成标志：View 中能看到正确设计；Agent 能读取目标模块；组件可在项目中运行；资源已落到项目目录；页面完成了预览对照。

下一步：[完整使用流程与提示词](workflow.md)。
