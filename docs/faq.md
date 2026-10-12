# 常见问题

**简体中文** · [English](en/faq.md)

[返回首页](../README.md) · [提交问题](https://github.com/tarot-ai-labs/tarot-pixel/issues/new?template=bug-report.yml)

## Agent 看不到 Tarot Pixel 工具

确认插件已启用，在新会话中让 Agent 调用 `server_status`。手动配置 MCP 时，检查 Node.js 版本、网络和客户端能否找到 `npx`。配置示例见[安装指南](installation.md)。

## 设计无法同步

先启动已启用 Tarot Pixel 的客户端，让 Agent 检查 `server_status`；确认 `view.ready` 为 `true` 后，再同步设计。设计工具与客户端应运行在同一台机器上。

## 查不到设计或节点

先在设计工具中同步，打开返回的链接确认设计已出现。设计修改后重新同步，并复制最新的完整链接交给 Agent。

## 设计链接打不开

保持客户端运行，使用当前同步结果返回的地址。检查是否重复配置了 Tarot Pixel MCP 服务，必要时禁用重复配置后重启客户端。

## 截图或合图失败

确认本机安装了 Chrome、Chromium、Edge 或 Brave，且本地设计预览已就绪。先用一个小模块重试，仍失败时可附上错误信息[提交问题](https://github.com/tarot-ai-labs/tarot-pixel/issues/new?template=bug-report.yml)。

## 字体或文字换行与设计不同

安装设计使用的字体，核对字重、字号、行高和页面宽度，再重新预览。

## 图片里的文字重复出现

让 Agent 检查图片中已包含的内容，避免再用代码绘制一遍。需要动态更新的文字，单独用代码实现。

## 图片部署后失效

将图片复制到项目资源目录，再使用项目内路径引用。本地临时地址仅用于读取和转存。

## 能把本地设计链接发给同事吗？

本地链接只在当前机器有效。同事需要在自己的机器上同步设计。

## 如何实现不同状态和交互？

把各状态的设计与业务条件一起交给 Agent，说明按钮动作、数据来源和状态切换规则。

## 设计数据保存在哪里？

同步后的设计数据和资源保存在本机。Agent 调用模型时，读取的设计内容可能随上下文发送给模型服务。
