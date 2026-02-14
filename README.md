# Enterprise Sankey Diagram Template for Power BI

[🇺🇸 English](README.md) | [🇪🇸 Español](README_ES.md)

![Power BI](https://img.shields.io/badge/Power%20BI-Desktop-F2C811?style=flat&logo=powerbi)
![Deneb](https://img.shields.io/badge/Visual-Deneb%20(Vega)-blue?style=flat)
![Status](https://img.shields.io/badge/Status-Stable-green)

![Sankey Diagram Preview](preview.png)

> [!TIP]
> **[ View Live Interactive Demo](https://app.powerbi.com/view?r=eyJrIjoiODAwYjlkYTYtZWYyNi00ODZlLWJjZWQtZTRiMmY2YzY2ODFlIiwidCI6IjYwZDMyOGIyLTE5ZTAtNDJhZi1hZThlLWYxMDEyOTkzMTUzNCJ9)**

A high-performance, parametric Sankey Diagram template designed for corporate operational analysis and complex data flows. Built using **Deneb (Vega)**, this visual overcomes standard Power BI limitations, offering granular control over node ordering, zero-value handling, and aesthetic customization.

## Key Features

This template is engineered for analysts who need more than the default visuals:

* **100% Parametric Configuration**: Driven by `Signals` in the Vega specification. You can rename columns in your dataset without breaking the visual—just update the signal mappings in the JSON header.
* **Zero-Ghosting Logic**: Integrated algorithms automatically filter out nodes with zero values, ensuring a clean and accurate visualization even when complex slicers interact with the data.
* **Hero Metric Alignment**: Features a conceptual "Hero Node" alignment capability (e.g., centering "Total Revenue" or "Gross Production") to establish an immediate visual benchmark for stakeholders.
* **manual Stack Ordering**: Includes support for a dedicated ordering column, allowing you to force a specific narrative flow (e.g., *Input -> Process -> Output*) regardless of data volume.

## Prerequisites

* **Power BI Desktop**: Latest version recommended.
* **Deneb Visual**: You must have the [Deneb custom visual](https://deneb-viz.github.io/) installed from AppSource (Version 1.8+ recommended).

## Repository Contents

| File / Folder                      | Description                                                                                                            |
| :--------------------------------- | :--------------------------------------------------------------------------------------------------------------------- |
| `SankeyDiagram.pbix`             | **Ready-to-use Demo**. Open this file to see the visual in action with sample data.                              |
| `SankeyDiagramPBIP/`             | **Power BI Project**. The unpacked project folder structure, ideal for version control and CI/CD pipelines.      |
| `Sankey_Universal_Template.json` | **Source Code**. The raw Vega/JSON specification for the Sankey diagram. Copy this into the Deneb editor.        |
| `dataset_Example.xlsx`           | **Data Template**. An Excel file showing the recommended tabular structure (Source, Target, Value, Depth/Level). |

## How to Use

1. **Prepare Data**: Ensure your data is in a transactional format (From -> To -> Value). See `dataset_Example.xlsx` for the ideal structure.
2. **Import Deneb**: Add the Deneb visual to your Power BI report canvas.
3. **Map Fields**: Drag your data fields into the Deneb visual placeholders (Source, Target, Value).
4. **Apply Template**:
   * Click on the visual header -> *Edit*.
   * Paste the content of `Sankey_Universal_Template.json` into the **Specification** tab.
   * *Note: If the JSON file is empty, use the configuration from the provided .pbix file.*
5. **Customize**: Update the `signals` section at the top of the JSON to match your specific field names if they differ from the defaults.

## Synthetic Data Generation (Yupay)

The sample data in this project (Agro-industrial Mass Balance) mimics a realistic production environment. It was generated using **Yupay**, an open-source synthetic data engine built with **Polars**.

> **Yupay** allows for the creation of large-scale, mathematically consistent datasets for testing complex analytics scenarios.
> *[Learn more about Yupay](https://github.com/yupay-dev/yupay)*

## Contributing

Contributions are welcome! Please verify that any changes to the Vega specification maintain compatibility with the "Zero-Ghosting" logic before submitting a Pull Request.

---

*Developed by Manuel Vasquez Abanto - Analytics Engineer & Development Lead.*
