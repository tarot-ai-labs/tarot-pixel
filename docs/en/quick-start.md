# Quick start

[简体中文](../quick-start.md) · **English**

[Home](../../README.en.md) · [Installation](installation.md) · [FAQ](faq.md)

Install Node.js 20.19.0 or later and Chrome, Chromium, Edge, or Brave. Run Qoder and your design tool on the same computer.

## 1. Enable Tarot Pixel

Install Tarot Pixel from the [Qoder marketplace](https://qoder.com/zh/marketplace/plugin?id=tarot-pixel) and enable it for your task. For other MCP clients, see [installation](installation.md#configure-mcp-directly).

## 2. Sync a design

1. Install the [Figma plugin](https://www.figma.com/community/plugin/1635645029043726171) or [Sketch plugin](https://unpkg.com/@tarot-ai/tarot-pixel-sketch-release@latest/Tarot-Pixel.sketchplugin.zip).
2. Keep Qoder running, select the target frames, artboards, or layers in your design tool, and open Tarot Pixel.
3. Choose **Sync design**. Open the returned link to inspect the design and copy the complete address.

Sync again whenever you update the source design.

## 3. Give Qoder a task

Open your frontend project and send the design link with your requirements:

```text
Use Tarot Pixel to implement this design: <complete synced design link>.
Build the product card using our existing components and styling conventions.
Keep the title, price, and button dynamic, and save images into the project's asset directory.
Run the page, compare it with the design, and refine the details.
```

Continue with a correction when needed:

```text
The button is too far from the price, and the card corners differ from the design.
Look up the relevant layout and styles, correct them, and preview the result again.
```

[More workflows and prompts →](workflow.md)
