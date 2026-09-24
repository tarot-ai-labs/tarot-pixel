# Supported capabilities

[简体中文](../compatibility.md) · **English**

[Home](../../README.en.md) · [Installation](installation.md)

This page describes the current local MCP product. Configuration examples use `latest` to select the latest npm runtime release. Design tool plugins are released independently and do not need matching version numbers.

## Integrations

| Component         | Current support                                                                                                                                                      |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Qoder             | Install [Tarot Pixel from the Qoder marketplace](https://qoder.com/zh/marketplace/plugin?id=tarot-pixel), or configure MCP directly                                  |
| Other MCP clients | Connect through stdio MCP; configuration, resource reading, and browser capabilities depend on the client. Full compatibility has not been verified for every client |
| Figma             | A public plugin syncs selected frames or layers                                                                                                                      |
| Sketch            | A public plugin ZIP is available; requires Sketch 80.0 or later                                                                                                      |
| Local View        | Starts with the runtime and lets you browse designs, layers, and assets                                                                                              |

## Available capabilities

- Browse designs, modules, and nodes; search text and layers.
- Query layout, dimensions, spacing, styles, and relative positions.
- Retrieve layered D2C context and context for batches of nodes.
- Render annotated node maps, design screenshots, and single-node or multi-node composites.
- Compare modules, inspect image content metadata, and generate local font subsets.

## Boundaries

- Agents and the View use MCP for reading, analysis, and rendering. Design tools sync through a dedicated import channel.
- The local product does not include the general REST query interface, embedded visual Chat Agent, or interactive TUI discussed in earlier explorations.
- Node maps display annotations. They do not promise to identify a corresponding node from an arbitrary uploaded image.
- Module differences help the agent compare artboards. Requirements still need to describe business states and interaction rules.
- Changes to the source design require another sync. An imported snapshot does not automatically follow source changes.
- Composites, screenshots, and font appearance depend on design export, local fonts, browser, and viewport conditions.
- Browser previews, business code execution, and testing depend on your client and project tools.

## Runtime requirements

The runtime requires Node.js 20.19.0 or later. Screenshots and composites need Chrome, Chromium, Edge, or Brave. This repository has not yet published a complete verification matrix of operating systems and clients. Include your operating system and versions when [reporting an environment issue](https://github.com/tarot-ai-labs/tarot-pixel/issues/new?template=bug-report.en.yml).
