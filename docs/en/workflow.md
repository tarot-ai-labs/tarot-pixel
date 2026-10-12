# Workflow and prompts

[简体中文](../workflow.md) · **English**

[Home](../../README.en.md) · [Quick start](quick-start.md)

After syncing, send the complete design link and the page or component you want to build. Describe existing components to reuse, dynamic content, and interactions, then preview the implementation and compare it with the design.

## Implement a page

```text
Use Tarot Pixel to implement this design: <complete design link>.
Build the campaign homepage using our existing stack and component conventions.
Read layout, styles, and images as needed, and save assets into the project.
Keep the campaign title, price, countdown, and button states dynamic.
Implement interactions using the project's requirements and API contracts, then preview and refine the result against the design.
```

## Refine a detail

```text
Continue checking this design: <complete design link>. Focus on the product card.
The button is too far from the price, and the background decoration sits too low.
Look up the relevant layout and styles, preserve the business logic, and preview the corrections.
```

## Build a component with multiple states

```text
This design: <complete design link> includes available, claimed, and expired states.
Compare the related modules and organize them into one component using the project's state definitions.
Reuse shared structure, vary text, styling, and interactions by state, and preview all three states.
```

## Handle backgrounds and dynamic content

```text
Create a composite image for this card's complex background decoration as needed.
Implement the title, price, and button in code so their content can change.
Check which elements are already included in the images to avoid duplicates, and save assets into the project.
```

[Need help? Read the FAQ →](faq.md)
