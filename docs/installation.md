# 安装与连接

**简体中文** · [English](en/installation.md)

[返回首页](../README.md) · [快速开始](quick-start.md) · [支持范围](compatibility.md)

## 环境要求

| 项目         | 要求                                                       |
| ------------ | ---------------------------------------------------------- |
| Node.js      | 20.19.0 或更高，客户端启动环境能找到 `node` 和 `npx`       |
| Coding Agent | 支持 stdio MCP；安装 Qoder 插件时还需插件支持              |
| 网络         | 使用 npm Runtime 时，首次启动需要访问 npm 公共仓库         |
| 渲染浏览器   | 本机安装 Chrome、Chromium、Edge 或 Brave，供截图、合图使用 |
| 设计工具     | Figma 或 Sketch                                            |

## Qoder 插件

Qoder 插件包含 MCP 服务配置和指导 Agent 使用设计数据的 Skill。

1. 打开 [Tarot Pixel 的 Qoder 插件市场页面](https://qoder.com/zh/marketplace/plugin?id=tarot-pixel)，按页面指引安装。
2. 在 Qoder 中确认 Tarot Pixel 已启用。
3. 新建任务，让 Agent 调用 `server_status` 验证连接。

也可以在 Qoder 的插件市场中搜索 `Tarot Pixel`。使用其他 MCP 客户端时，按下方说明配置公开 npm Runtime。Qoder 界面操作可参考[官方插件说明](https://docs.qoder.com/qoder/plugins)。

## 直接配置 MCP

在兼容客户端的自定义 MCP 配置中添加：

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

- `latest` 使用 npm 当前最新发布版本。团队需要固定环境时，可根据[包发布信息](https://www.npmjs.com/package/@tarot-ai/pixel)替换为已经验证的具体版本。
- 已有 `mcpServers` 时，只添加 `tarot-pixel` 条目，保留其他服务。
- 有些客户端只接收单个服务对象，应按客户端配置格式填入相应内容。
- 已使用 Qoder 插件启动服务时，无需再配置第二条同名 MCP 服务。
- 直接配置 MCP 提供工具能力；可使用[工作流提示词](workflow.md)引导 Agent 查询和实现。

Qoder 自定义 MCP 的入口见[官方 Connectors 说明](https://docs.qoder.com/qoder/connectors)。

## Figma 插件

1. 打开 [Tarot Pixel 的 Figma Community 页面](https://www.figma.com/community/plugin/1635645029043726171)，或在 Figma 插件搜索中搜索 `Tarot Pixel`。
2. 打开设计文件，选择要同步的 Frame 或图层。
3. 确认本机 Runtime 已由客户端启动，运行插件并点击“同步设计稿”。
4. 打开同步结果中的本地链接，确认设计已出现在 View。

## Sketch 插件

要求 Sketch 80.0 或更高版本。

1. [下载插件 ZIP](https://unpkg.com/@tarot-ai/tarot-pixel-sketch-release@latest/Tarot-Pixel.sketchplugin.zip)并解压。
2. 双击解压得到的 `.sketchplugin` 完成安装。
3. 打开设计文档，选择画板或图层，运行 Tarot Pixel。
4. 确认本机 Runtime 已启动，点击“同步设计稿”。插件安装后会检查后续更新。

Sketch 插件与 Runtime 的版本独立。反馈问题时，尽量同时记录两个版本。

## 验证安装

让 Agent 调用 `server_status` 和 `design_list`。连接成功且 `view.ready` 为 `true` 后，再到设计工具中同步。终端能找到 `npx`、桌面客户端却找不到时，需要检查客户端的启动环境或为 `command` 配置实际可执行文件路径。

出现问题时，请参考[常见问题](faq.md)，或[提交问题反馈](https://github.com/tarot-ai-labs/tarot-pixel/issues/new?template=bug-report.yml)。
