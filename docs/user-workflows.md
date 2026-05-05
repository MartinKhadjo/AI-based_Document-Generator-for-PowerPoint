# User workflows

The shipping user experience is centered on the **Document Generator** task pane. The add-in does not rely on a separate production ribbon tab; all main features are available in the task pane.

## Task pane layout

| Area | Purpose |
|---|---|
| Top strip | Opens service configuration for Azure OpenAI, OpenAI Direct, Kroki and analysis endpoints. |
| Logo strip | Displays the embedded logo and scales with pane width. |
| Tabs | Bullets, Images, Charts and Analysis. |

## Bullets workflow

1. User writes or continues a conversation in the Bullets tab.
2. The tab maintains a multi-turn transcript with a sliding memory window.
3. User selects language and bullet format.
4. The configured chat model generates bullet points.
5. User reviews and adjusts font family, size and color.
6. `Update Slide` inserts formatted text boxes into the active slide.

## Images workflow

1. User enters a prompt or uploads a base image.
2. The system calls the configured image provider.
3. The generated or edited image is stored as an image asset with lineage metadata.
4. The preview and history gallery allow the user to select previous versions.
5. User inserts the selected image into the current PowerPoint slide.

## Charts and diagrams workflow

1. User enters a natural-language description or raw DSL.
2. If a chart GPT provider is configured, the system generates a Vega-Lite or diagram DSL specification.
3. Kroki renders the specification to an image.
4. The rendered output can be previewed and inserted into the slide.

Supported diagram/chart families include Vega-Lite, Mermaid, D2, PlantUML and Graphviz.

## Image analysis workflow

1. User uploads an image and enters an analysis prompt.
2. The system sends a multimodal chat-completion request containing a base64 data URL.
3. A vision-capable GPT model returns an analysis result.
4. The result can be converted into bullet points and inserted into the current slide.

![Runtime workflows](assets/runtime-flows.svg)
