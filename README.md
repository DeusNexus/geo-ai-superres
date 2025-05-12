# GeoAI Super-Resolution Pipeline

## Overview

This project aims to enhance the spatial resolution of satellite imagery and analyze temporal changes for applications such as land cover classification, slope detection, and urban growth prediction. This is especially relevant for terrain assessment in areas prone to flooding or landslides, or to evaluate land for potential real estate development.

## Features

- Super-resolution of Sentinel-2 imagery using a hybrid CNN-Transformer architecture.
- Land cover classification enhanced by high-resolution outputs.
- Temporal analysis of urban growth and vegetation change.
- Predictive modeling for future land use and construction trends.

## Project Structure

- `data/`: Contains raw and processed datasets.
- `notebooks/`: Jupyter notebooks for data preparation, model training, and analysis.
- `models/`: Trained model weights and checkpoints.
- `src/`: Modular source code for preprocessing, modeling, and visualization.
- `outputs/`: Maps, plots, and reports generated during analysis.

```
geo-ai-superres/
│
├── data/
│   ├── raw/                 # Original satellite imagery (Sentinel-1, Sentinel-2, DEM)
│   ├── processed/           # Preprocessed data (cloud-masked, normalized)
│   ├── superres/            # Super-resolved outputs
│   ├── temporal/            # Time-series datasets
│   └── masks/               # NDVI, land cover, slope, water bodies
│
├── notebooks/
│   ├── 01_data_preparation.ipynb
│   ├── 02_superresolution_training.ipynb
│   ├── 03_land_cover_classification.ipynb
│   ├── 04_temporal_analysis.ipynb
│   └── 05_urban_growth_prediction.ipynb
│
├── models/
│   ├── superres_model.pth
│   ├── landcover_model.pth
│   └── urban_growth_model.pth
│
├── src/
│   ├── data_processing/
│   ├── models/
│   ├── utils/
│   └── visualization/
│
├── outputs/
│   ├── maps/
│   ├── charts/
│   └── reports/
│
├── requirements.txt
└── README.md
```

## Installation

```bash
git clone https://github.com/deusnexus/geo-ai-superres.git
cd geo-ai-superres
pip install -r requirements.txt
```

## Model Architecture

For the super-resolution task, we employ **EHNet (Efficient Hybrid Network)**, a modern hybrid architecture that combines a **U-Net backbone** with **Swin Transformer** blocks. This allows us to effectively capture both **local textures** (via CNNs) and **global context** (via Transformers), making it especially well-suited for complex satellite scenes that include mixed landforms like vegetation, rivers, roads, and slopes.

### Why EHNet?

This model was selected based on the following criteria:

- ✅ Strong benchmark results on remote sensing super-resolution tasks  
- ✅ Lightweight and scalable for large satellite datasets (e.g., Sentinel-2)  
- ✅ Transformer modules allow learning long-range dependencies critical in geospatial imagery  

---

### 📖 Citation (APA 7th Edition)

Lu, H., Li, D., Xue, J., & Zhan, Y. (2024). *An efficient hybrid CNN-transformer approach for remote sensing image super-resolution*. *Remote Sensing, 16*(5), 880. https://doi.org/10.3390/rs16050880

🔗 [Read the full paper here](https://www.mdpi.com/2072-4292/16/5/880)

---

## License

[MIT License](LICENSE)

---

If you need further assistance with setting up the repository or implementing specific modules, feel free to ask!

