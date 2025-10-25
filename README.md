# 🎨 Colorspace QGIS XML Styles

This repository provides **QGIS color style files (`.xml`)** generated from the **R Colorspace package**, enabling cartographers, GIS analysts, and data visualization experts to easily apply scientifically designed color palettes within **QGIS**.

---

## 📘 Overview

The **Colorspace** package (R) provides a robust framework for creating **qualitative**, **sequential**, and **diverging** color palettes based on the **HCL (Hue–Chroma–Luminance)** color model.  
These palettes are known for their **perceptual uniformity**, **color vision deficiency friendliness**, and **balanced visual contrast**, making them ideal for cartographic design and thematic mapping.

This project converts those palettes into **QGIS XML style files** (`.xml`), allowing direct use in QGIS layer symbology, categorized maps, and graduated color ramps.

---

## 📁 Repository Structure

```text
Colorspace-QGIS/
│
├── qualitative/
│   ├── Dark2.xml
│   ├── Set2.xml
│   └── Pastel1.xml
│
├── sequential/
│   ├── Blues.xml
│   ├── Greens.xml
│   └── Viridis.xml
│
├── diverging/
│   ├── RdBu.xml
│   ├── PiYG.xml
│   └── Spectral.xml
│
├── palettes_preview/
│   ├── qualitative.png
│   ├── sequential.png
│   └── diverging.png
│
└── README.md
```

Each `.xml` file corresponds to a **color ramp** that can be imported directly into QGIS.

---

## 🧠 Color Model Background

**HCL (Hue–Chroma–Luminance)** color space aligns closely with human perception:

- **Hue (H):** type of color (e.g., red, green, blue)  
- **Chroma (C):** color intensity or saturation  
- **Luminance (L):** brightness or lightness  

By defining palettes in this space, **Colorspace** ensures visual balance and interpretability across different data ranges and audiences.

---

## 🔧 How to Use in QGIS

### Option 1: Import via QGIS Style Manager

1. Open **QGIS**.  
2. Go to **Settings → Style Manager**.  
3. Click **Import/Export → Import from file...**  
4. Select a `.xml` file (e.g., `Blues.xml`).  
5. The color ramp will appear in your QGIS color ramps list.

### Option 2: Use Directly in Symbology

1. Open **Layer Properties → Symbology**.  
2. Choose **Graduated** or **Categorized** rendering.  
3. Under **Color ramp**, click the dropdown → select **your imported Colorspace palette**.

---

## 🧩 Palette Categories

| Type | Description | Example Palettes |
|------|--------------|------------------|
| 🎨 **Qualitative** | Best for categorical data (e.g., land cover types, regions) | `Set2`, `Pastel1`, `Dark2` |
| 🌈 **Sequential** | Ideal for continuous numeric data (e.g., temperature, elevation) | `Blues`, `Greens`, `Viridis` |
| 🔀 **Diverging** | Used for centered data (e.g., anomalies, differences) | `RdBu`, `PiYG`, `Spectral` |

---

## 🧰 Generate Your Own XML from R

If you want to convert any Colorspace palette yourself:

```r
# Install and load required packages
if (!require(colorspace)) install.packages("colorspace")
library(colorspace)

# Example: Export "Viridis" palette
pal <- colorspace::sequential_hcl(9, "Viridis")

# Write to QGIS XML format
write_qgis_xml <- function(name, colors) {
  cat(sprintf('<qgis_style version="2">\n  <colorramps>\n    <colorramp type="gradient" name="%s">\n', name))
  cat(sprintf('      <prop k="color1" v="%s"/>\n', colors[1]))
  cat(sprintf('      <prop k="color2" v="%s"/>\n', tail(colors, 1)))
  cat('      <prop k="discrete" v="0"/>\n')
  cat('      <prop k="stops" v="')
  for (i in seq_along(colors)) {
    cat(sprintf('%f;%s', (i - 1) / (length(colors) - 1), colors[i]))
    if (i < length(colors)) cat(':')
  }
  cat('"/>\n    </colorramp>\n  </colorramps>\n</qgis_style>')
}

write_qgis_xml("Viridis", pal)
```

Save the output as `Viridis.xml` and import it into QGIS.

---

## 🧾 Citation

If you use these palettes, please cite the original **Colorspace** package:

> Zeileis, A., Hornik, K., & Murrell, P. (2009). Escaping RGBland: Selecting colors for statistical graphics.  
> *Computational Statistics & Data Analysis*, 53(9), 3259–3270.  
> DOI: [10.1016/j.csda.2008.11.033](https://doi.org/10.1016/j.csda.2008.11.033)

---

## 🖼️ Example Visualization

| Type | Preview |
|------|----------|
| Qualitative | ![Qualitative palettes](palettes_preview/qualitative.png) |
| Sequential | ![Sequential palettes](palettes_preview/sequential.png) |
| Diverging | ![Diverging palettes](palettes_preview/diverging.png) |

---

## 🧑‍💻 Author

**Hemed Lungo**  
📧 [hemedlungo@gmail.com](mailto:hemedlungo@gmail.com)  
🗺️ GIS & Remote Sensing Analyst | QGIS & R Enthusiast  

---

## 🪪 License

This collection is released under the **MIT License**.  
Color palettes are derived from the **R Colorspace** package, © Achim Zeileis, Kurt Hornik, Paul Murrell.

---

## ⭐ Acknowledgements

- [R Colorspace Package](https://cran.r-project.org/package=colorspace)  
- [QGIS Project](https://qgis.org)  
- [Cartography & Visualization Community](https://twitter.com/qgis)
