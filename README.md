# 🎨 Colorspace QGIS XML Style

This repository contains a single **QGIS color style file (`Colorspace.xml`)** derived from the **R Colorspace** package.  
It provides a perceptually uniform and cartographically sound color ramp that can be used directly in **QGIS** projects.

---

## 📁 Repository Contents

```text
Colorspace-qgis-xml/
│
├── Colorspace.xml
└── README.md
```

- **`Colorspace.xml`** — The QGIS color ramp file that defines a Colorspace-based palette.

---

## 📘 Description

The **Colorspace** package in R provides a scientific approach to color selection using the **HCL (Hue–Chroma–Luminance)** color model.  
This XML style brings those high-quality palettes into **QGIS**, allowing cartographers and GIS analysts to apply consistent and perceptually balanced color ramps for maps, data visualizations, and thematic symbology.

---

## 🧠 About HCL Colors

**HCL (Hue–Chroma–Luminance)** color space is based on human color perception:

- **Hue (H):** the color type (e.g., red, green, blue)  
- **Chroma (C):** the intensity or saturation of color  
- **Luminance (L):** the perceived brightness  

Using this model, the Colorspace palette ensures even transitions and clear data distinctions in your maps.

---

## 🔧 How to Use in QGIS

### Option 1: Import via Style Manager
1. Open **QGIS**.  
2. Go to **Settings → Style Manager**.  
3. Click **Import/Export → Import from file...**  
4. Select the file **`Colorspace.xml`**.  
5. The color ramp will appear in your QGIS color ramps list.

### Option 2: Use in Layer Symbology
1. Open your layer’s **Properties → Symbology**.  
2. Choose **Graduated** or **Categorized** rendering.  
3. Under **Color ramp**, click the dropdown and select **Colorspace**.

---
## Video Tutorial 
https://github.com/user-attachments/assets/8e32e0e1-24c8-4002-9606-418d9a736815


---

## 🧾 Citation

If you use this palette, please cite the original **Colorspace** package:

> Zeileis, A., Hornik, K., & Murrell, P. (2009).  
> *Escaping RGBland: Selecting colors for statistical graphics.*  
> Computational Statistics & Data Analysis, 53(9), 3259–3270.  
> DOI: [10.1016/j.csda.2008.11.033](https://doi.org/10.1016/j.csda.2008.11.033)

---

## 🧑‍💻 Author

**Hemed Lungo**  
📧 [hemedlungo@gmail.com](mailto:hemedlungo@gmail.com)  
🗺️ GIS & Remote Sensing Analyst | QGIS & R Enthusiast  

---

## 🪪 License

This work is released under the **MIT License**.  
Color design and structure based on the **R Colorspace** package © Achim Zeileis, Kurt Hornik, Paul Murrell.

---

## ⭐ Acknowledgements

- [R Colorspace Package](https://cran.r-project.org/package=colorspace)  
- [QGIS Project](https://qgis.org)
