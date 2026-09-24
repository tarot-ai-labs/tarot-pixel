# Workflow and prompts

[简体中文](../workflow.md) · **English**

[Home](../../README.en.md) · [Quick start](quick-start.md)

## From design to implementation

1. **Sync and check.** Sync the target region from your design tool, then confirm that its modules, text, and assets appear correctly in the local View.
2. **Describe the project goal.** Provide the full design link, target page or component, interaction states, and conventions to reuse.
3. **Read in layers.** The agent locates a module through the overview, then queries the relevant nodes' layout, styles, and assets.
4. **Choose an implementation.** Keep changing text and data in code. Use design evidence to decide whether complex decoration should become a composite image.
5. **Run and compare.** Compare at the relevant viewport, with the right fonts and state, then revisit the design data to refine the result.

Running the page and using a browser depend on your client and project tools. If the client lacks browser support, a developer can preview the page and point out differences.

## Implement a page

```text
Use Tarot Pixel to implement this design: <complete design link>.
The target is the "Campaign home" module. Follow this project's stack and component conventions.

Inspect the project and locate the design module, then query layout, styles, and assets as needed.
Keep the campaign title, price, countdown, and button states dynamic.
Use the existing requirements and API contracts for interactions; do not infer missing behavior from a static design.
Save generated images and fonts into the project's managed asset directories.
Run the project at the design's viewport, compare the result, and correct major differences.
```

## Refine a detail

```text
Continue checking this design: <complete design link>, focusing on the "Product card".
The gap between the button and price is too large, and the background decoration sits too low.
Locate the relevant nodes and query their layout, relative positions, and asset boundaries before correcting them.
Preserve the existing business logic, then compare again at the same viewport.
```

## Implement component states

```text
This design, <complete design link>, contains "Available", "Claimed", and "Expired" card states.
Review the relevant modules and compare their differences.
Use the project's business state definitions to organize them into one component.
Identify the shared structure and the text, styles, and interactions that change with each state.
Preview all three states and identify any behavior that still needs clarification in the requirements.
```

Module differences offer useful clues. Business requirements still need to define state meaning and interaction rules.

## Handle backgrounds and dynamic content

```text
Inspect the layers that make up this card's background and composite complex decoration where appropriate.
Keep the title, price, button text, and other changing data editable.
Check whether existing images already contain text or visual elements so they are not rendered twice.
Save generated assets into the project and verify their transparent edges and display dimensions.
```

## Common MCP tools

These are current MCP tool names. For everyday use, describe your task and let the agent select tools. Parameter definitions come from the tools listed by your client.

| Purpose                                     | Example tools                                                                               |
| ------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Check the connection                        | `server_status`, `design_list`                                                              |
| Explore the design                          | `design_get_overview`, `design_list_modules`                                                |
| Locate nodes                                | `design_search_nodes`, `design_get_node_map`, `design_get_module_context`                   |
| Query layout and styles                     | `design_get_d2c_context`, `design_get_d2c_context_batch`, `design_get_node_relative_offset` |
| Inspect content already baked into an image | `design_get_node_image_meta`                                                                |
| View design screenshots                     | `design_get_node_screenshot`, `design_get_module_screenshot`                                |
| Generate implementation assets              | `design_get_composite`, `design_get_multi_composite`                                        |
| Compare modules                             | `design_diff_modules`                                                                       |
| Work with local fonts                       | `font_registry_get`, `font_subset_local`                                                    |

Node maps and design screenshots provide evidence. Use composite tools when generating decorative images for an implementation. Copy assets from temporary locations into the project before referencing them; see the [FAQ](faq.md).
