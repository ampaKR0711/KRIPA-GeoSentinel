# 🛰️ KRIPA GeoSentinel
### 🌊 Satellite-Based Coastal Freshwater & Surface-Water Intelligence System

<p align="center">
  <img src="https://img.shields.io/badge/Project-Geospatial%20AI-0B7285?style=for-the-badge&logo=googleearth&logoColor=white"/>
  <img src="https://img.shields.io/badge/Domain-Remote%20Sensing-146C94?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Satellite-Landsat%208-198754?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Status-Research%20in%20Progress-orange?style=for-the-badge"/>
</p>

<p align="center">
  <b>Geospatial Intelligence • Satellite Remote Sensing • Environmental Monitoring • GIS • Python</b>
</p>

---

## 🌍 1. Project Overview

**KRIPA GeoSentinel** is a satellite-based geospatial research initiative focused on analysing surface-water distribution and developing an analytical framework for coastal freshwater monitoring.

The project explores how satellite remote sensing, geospatial data processing, environmental indicators and spatial analysis can be integrated to investigate water-related environmental patterns.

Using multispectral satellite imagery and Geographic Information System (GIS) techniques, the project develops a structured workflow for:

- 🛰️ Satellite imagery discovery and acquisition
- 🌐 Geospatial data processing and validation
- ☁️ Cloud and atmospheric quality assessment
- 💧 Surface-water index computation
- 🗺️ Spatial distribution analysis
- 📊 Water-candidate classification and comparison
- 🔬 Environmental monitoring and research-oriented interpretation

The long-term objective is to develop a reproducible geospatial intelligence framework that can support coastal water-resource monitoring and future freshwater-stress investigations.

> **KRIPA** represents an independent research initiative combining geospatial technology, satellite intelligence and environmental analysis.

---

## ❗ 2. Problem Statement

Coastal environments are dynamic systems where surface-water distribution and freshwater availability can be influenced by:

- 🌊 Tidal variations and coastal processes
- 🌧️ Seasonal rainfall variability
- 🏭 Urbanisation and industrial development
- 🌱 Changes in land cover and vegetation
- 💧 Surface-water availability and distribution
- 🌍 Environmental and climatic variations

Conventional field-based monitoring can be resource-intensive and may not provide continuous spatial coverage.

Satellite remote sensing offers an opportunity to observe large geographical areas repeatedly and analyse changes in surface characteristics.

### 🎯 Research Problem

Develop a geospatial processing and analytical framework capable of using multispectral satellite imagery to:

✅ Identify potential surface-water regions.

✅ Analyse spatial water-distribution patterns.

✅ Compare water-sensitive spectral indices.

✅ Investigate temporal changes using multi-date satellite observations.

✅ Establish a foundation for future coastal freshwater-stress assessment.

---

## 🎯 3. Project Objectives

The major objectives of KRIPA GeoSentinel are:

1. **Satellite Data Acquisition**  
   Discover and retrieve suitable satellite imagery through cloud-based geospatial catalogues.

2. **Geospatial Preprocessing**  
   Validate raster dimensions, coordinate reference systems, spatial resolution and data integrity.

3. **Satellite Quality Assessment**  
   Decode pixel-quality information and identify cloud, shadow, snow, fill and saturation conditions.

4. **Spectral Index Computation**  
   Calculate NDWI and MNDWI for preliminary surface-water analysis.

5. **Water-Candidate Identification**  
   Investigate potential water pixels using index thresholds and comparative analysis.

6. **Spatial Analysis**  
   Examine spatial distribution, connected regions and geographical patterns.

7. **Environmental Monitoring Framework**  
   Establish a foundation for multi-temporal analysis and coastal freshwater-stress investigations.

---

## 🏗️ 4. Proposed System Architecture

The current research workflow follows a structured satellite-to-analysis pipeline.

```text
             SATELLITE DATA DISCOVERY
                       │
                       ▼
             STAC CATALOGUE SEARCH
                       │
                       ▼
             SCENE QUALITY SCREENING
                       │
                       ▼
             SATELLITE SCENE SELECTION
                       │
                       ▼
              ASSET URL SIGNING
                       │
                       ▼
              SATELLITE DATA DOWNLOAD
                       │
                       ▼
             RASTER DATA VALIDATION
                       │
                       ▼
             SPECTRAL DATA PREPROCESSING
                       │
                       ▼
               QA_PIXEL / QA_RADSAT
                       │
                       ▼
                 QUALITY MASKING
                       │
              ┌────────┴────────┐
              ▼                 ▼
           NDWI              MNDWI
              │                 │
              ▼                 ▼
       WATER-CANDIDATE    WATER-CANDIDATE
       IDENTIFICATION     IDENTIFICATION
              │                 │
              └────────┬────────┘
                       ▼
              THRESHOLD ANALYSIS
                       │
                       ▼
              SPATIAL COMPARISON
                       │
                       ▼
             FUTURE VALIDATION
                       │
                       ▼
          COASTAL WATER MONITORING
```

*Note: The architecture represents the intended research workflow. Spatial validation and subsequent monitoring stages remain under development.*

---

## 🛰️ 5. Satellite Data & Acquisition

### Landsat 8 Collection 2 Level-2

The initial implementation uses **Landsat 8 Collection 2 Level-2 Surface Reflectance data**.

| Parameter | Selected Scene Details |
|---|---|
| Satellite | Landsat 8 |
| Data Collection | Landsat Collection 2 |
| Processing Level | Level-2 Surface Reflectance |
| Product | Landsat 8 OLI/TIRS |
| Acquisition Date | 25 May 2015 |
| Product ID | LC08_L2SP_140046_20150525_20200909_02_T1 |
| STAC Collection | landsat-c2-l2 |
| CRS | EPSG:32645 |
| Spatial Resolution | 30 metres |
| Raster Dimensions | 7671 × 7821 |

### 🔍 Satellite Data Discovery

The project uses the **SpatioTemporal Asset Catalog (STAC)** approach to discover and organise satellite imagery.

The acquisition workflow includes:

- STAC catalogue searches
- Acquisition-date grouping
- Cloud-cover screening
- Scene-footprint coverage assessment
- Temporal relevance assessment
- Asset inventory generation
- Signed satellite asset access
- Automated data download
- Download verification

### 📊 Acquisition Screening Results

| Screening Parameter | Result |
|---|---:|
| Unique satellite scenes discovered | 871 |
| Acquisition-date groups | 228 |
| Successful STAC searches | 36 |
| Failed STAC searches | 0 |
| Preliminary shortlisted scenes | 186 |
| Selected test scene | 1 |

The preliminary shortlist used a heuristic ranking system based on:

- Cloud-cover score: 40%
- Footprint-coverage score: 35%
- Temporal-proximity score: 25%

These are project-specific screening weights, not established scientific standards.

---

## ⚙️ 6. Satellite Data Preprocessing

Before performing spectral analysis, the acquired satellite imagery undergoes structural and numerical validation.

### 🧪 Raster Validation

The downloaded spectral and quality-assessment assets were checked for:

- Raster readability
- Image dimensions
- Coordinate reference system
- Spatial resolution
- Geotransform
- Spatial bounds
- Data type
- NoData values
- Pixel-level validity

### 📁 Acquired Satellite Assets

The selected Landsat scene contains eight downloaded raster assets:

| Asset | Description |
|---|---|
| SR_B2 | Blue |
| SR_B3 | Green |
| SR_B4 | Red |
| SR_B5 | Near Infrared |
| SR_B6 | Shortwave Infrared 1 |
| SR_B7 | Shortwave Infrared 2 |
| QA_PIXEL | Pixel Quality Assessment |
| QA_RADSAT | Radiometric Saturation Assessment |

### 📐 Reflectance Conversion

Landsat Collection 2 Level-2 surface-reflectance values are converted using the metadata-provided scaling parameters:

```python
reflectance = DN * 0.0000275 - 0.2
```

The Level-2 scaling values are retrieved from the scene metadata rather than assumed from the raster's internal scale fields.

**Important:** The reflectance transformation is applied to the spectral surface-reflectance bands, not the QA bands.

---

## ☁️ 7. Satellite Quality Assessment

Satellite imagery may contain cloud contamination, cloud shadows, atmospheric interference and saturated pixels.

KRIPA GeoSentinel incorporates pixel-level quality assessment before computing water-sensitive indices.

### QA_PIXEL Analysis

The QA_PIXEL raster is decoded using individual bit flags and confidence fields.

The examined conditions include:

- Fill pixels
- Dilated cloud
- Cirrus
- Cloud
- Cloud shadow
- Snow
- Clear flag
- Water flag
- Cloud confidence
- Cloud-shadow confidence
- Snow confidence
- Cirrus confidence

### QA_RADSAT Analysis

Radiometric saturation information is inspected to identify affected spectral bands.

The processing also considers the dropped-pixel flag and relevant saturation conditions before generating index-specific masks.

### 📊 Preliminary Quality Mask Results

| Parameter | Result |
|---|---:|
| Total scene pixels | 59,994,891 |
| Initially eligible pixels | 34,934,242 |
| Initially excluded pixels | 25,060,649 |
| Initially eligible percentage | 58.229% |

The NDWI and MNDWI masks are independently constructed using their contributing spectral bands and relevant saturation conditions.

### Final Index Eligibility

| Index | Eligible Pixels |
|---|---:|
| NDWI | 34,934,237 |
| MNDWI | 34,934,232 |

The masks represent preliminary QA-based eligibility, not a guarantee of cloud-free or scientifically validated observations.

---

## 💧 8. Spectral Water Indices

Two widely used spectral indices are implemented for preliminary surface-water analysis.

### 🌊 A. Normalized Difference Water Index (NDWI)

NDWI uses Green and Near-Infrared reflectance to investigate water-sensitive spectral behaviour.

**Formula:**

\[
NDWI = \frac{Green-NIR}{Green+NIR}
\]

Landsat 8 bands:

- Green: Band 3
- NIR: Band 5

### 🌊 B. Modified Normalized Difference Water Index (MNDWI)

MNDWI replaces the NIR band with Shortwave Infrared 1 to improve water-related feature discrimination in certain environments.

**Formula:**

\[
MNDWI = \frac{Green-SWIR1}{Green+SWIR1}
\]

Landsat 8 bands:

- Green: Band 3
- SWIR1: Band 6

### 🧠 Why Use Both Indices?

Using both indices enables comparative analysis of their responses to different surface characteristics.

This is particularly useful in coastal and urban environments, where built-up surfaces, soil and water may produce different spectral responses.

---

## 📈 9. Experimental Results

The initial test scene was processed using the QA-filtered spectral data.

### NDWI Results

| Metric | Value |
|---|---:|
| Valid pixels | 34,934,237 |
| Minimum | -0.789450 |
| Maximum | 0.691630 |
| Mean | -0.478524 |
| Median | -0.487901 |

### MNDWI Results

| Metric | Value |
|---|---:|
| Valid pixels | 34,934,232 |
| Minimum | -0.874723 |
| Maximum | 0.630711 |
| Mean | -0.421223 |
| Median | -0.438153 |

Both index outputs were exported as georeferenced GeoTIFF files.

### 📁 Generated Index Products

```text
water_indices/
│
├── LC08_L2SP_140046_20150525_02_T1_NDWI.tif
│
└── LC08_L2SP_140046_20150525_02_T1_MNDWI.tif
```

Output specifications:

- Raster dimensions: 7671 × 7821
- CRS: EPSG:32645
- Spatial resolution: 30 metres
- Data type: Float32
- NoData value: -9999

---

## 🔬 10. Preliminary Water-Candidate Classification

An initial threshold-based investigation was performed using an index threshold greater than zero.

The classification is exploratory and is not yet a validated water-body extraction model.

### Initial Classification Results

| Parameter | NDWI | MNDWI |
|---|---:|---:|
| Valid pixels | 34,934,237 | 34,934,232 |
| Candidate pixels | 551,360 | 707,730 |
| Candidate percentage | 1.5783% | 2.0259% |
| Candidate area | 496.224 km² | 636.957 km² |

*Candidate area is calculated using 30 m × 30 m pixels and the respective index masks.*

### 🔍 Comparative Analysis

The common-valid-area comparison produced the following results:

| Classification | Pixels | Area |
|---|---:|---:|
| Detected by both indices | 551,032 | 495.9288 km² |
| NDWI only | 328 | 0.2952 km² |
| MNDWI only | 156,698 | 141.0282 km² |
| Detected by either index | 708,058 | 637.2522 km² |

The comparison indicates that MNDWI identifies additional candidate pixels that are not classified by NDWI at the same threshold.

This difference requires further spatial investigation and validation before determining which index performs better for the study area.

---

## 📊 11. Threshold Sensitivity Analysis

To investigate the influence of threshold selection, six threshold values were examined.

| Threshold | NDWI Area (km²) | MNDWI Area (km²) |
|---:|---:|---:|
| -0.2 | 720.3357 | 834.9669 |
| -0.1 | 613.7352 | 729.7335 |
| 0.0 | 496.2240 | 636.9570 |
| 0.1 | 349.2837 | 514.4679 |
| 0.2 | 209.2437 | 379.1007 |
| 0.3 | 101.6082 | 233.1342 |

### Key Observations

- Candidate area decreases as the threshold becomes more restrictive.
- MNDWI consistently produces a larger candidate area than NDWI in the examined scene.
- Threshold selection significantly influences the resulting candidate area.
- A single threshold cannot establish the accuracy of a water classification.

The threshold sensitivity results have been exported as a CSV analysis report.

**Scientific limitation:** These are preliminary index-positive areas across the valid scene. They should not be interpreted as confirmed water-body area, freshwater availability or freshwater stress.

---

## 🧰 12. Technologies & Tools Used

| Technology | Purpose |
|---|---|
| Python | Core programming and analysis |
| Jupyter Notebook | Interactive research environment |
| NumPy | Numerical and raster-array processing |
| Pandas | Data organisation and analysis |
| Rasterio | Geospatial raster processing |
| GeoPandas | Vector geospatial analysis |
| STAC | Satellite imagery discovery |
| Planetary Computer | Satellite asset access and signing |
| Landsat 8 | Multispectral satellite imagery |
| GIS / Remote Sensing | Spatial and environmental analysis |
| Matplotlib | Scientific visualisation |
| Git & GitHub | Version control and project documentation |
| QGIS | Planned spatial inspection and mapping |

---

## 🔬 13. Research Challenges & Technical Solutions

### ☁️ Satellite Cloud Contamination

**Challenge:** Satellite observations may contain cloud and cloud-shadow interference.

**Approach:** Decode QA_PIXEL and apply preliminary quality masks.

### 🔐 Satellite Asset Access

**Challenge:** Original unsigned Azure Blob asset URLs returned HTTP 409 errors.

**Approach:** Implement Planetary Computer asset signing and verify access using HTTP Range requests.

### 🛰️ Raster Alignment

**Challenge:** Spectral and QA bands must share the same spatial grid for reliable pixel-level analysis.

**Approach:** Validate dimensions, CRS, transform, bounds and resolution across all eight assets.

### 📉 Reflectance Scaling

**Challenge:** Raw digital numbers cannot be directly interpreted as surface reflectance.

**Approach:** Retrieve the official Level-2 scaling parameters from the scene metadata.

### ☁️ Pixel Quality and Saturation

**Challenge:** Invalid and saturated pixels may affect spectral index calculations.

**Approach:** Decode QA_PIXEL and QA_RADSAT and create index-specific eligibility masks.

### 🌊 Threshold Selection

**Challenge:** Different thresholds generate substantially different candidate areas.

**Approach:** Conduct multi-threshold sensitivity analysis and plan independent spatial validation.

---

## 🚀 14. Future Development Roadmap

The project is intended to evolve from initial satellite processing into a broader geospatial environmental monitoring framework.

### 🛰️ Stage 1 — Satellite Data Acquisition
- Multi-date Landsat imagery acquisition
- Additional satellite datasets
- Automated scene screening
- Acquisition metadata management

### 🧪 Stage 2 — Advanced Preprocessing
- Improved cloud and shadow masking
- Multi-date raster harmonisation
- Study-area extraction
- Improved data-quality assessment

### 💧 Stage 3 — Water Classification
- Connected-region analysis
- Threshold optimisation
- Spatial feature extraction
- Water-body boundary analysis

### 🗺️ Stage 4 — GIS & Spatial Validation
- Geographic study-area definition
- Reference-data comparison
- Spatial validation
- Classification accuracy assessment

### 🌍 Stage 5 — Environmental Monitoring
- Seasonal and temporal water analysis
- Surface-water change detection
- Coastal environmental indicators
- Freshwater-stress research framework

### 📊 Stage 6 — Intelligence & Visualisation
- Interactive GIS maps
- Environmental monitoring dashboard
- Spatial trend analysis
- Research reporting and visualisation

*These are planned development stages, not claims of completed implementation.*

---

## 🌐 15. Research Significance

KRIPA GeoSentinel explores the application of satellite remote sensing and geospatial analytics to environmental monitoring.

Potential research applications include:

- Surface-water distribution analysis
- Coastal environmental observation
- Seasonal water-extent monitoring
- Land-water interaction studies
- Geospatial change detection
- Satellite-based environmental intelligence

The project aims to develop practical experience in remote sensing, raster processing, satellite data acquisition and geospatial research methodology.

It is an exploratory research initiative and is not a clinically or operationally validated freshwater-monitoring system.

---

## 👨‍💻 16. Project Information

| Field | Details |
|---|---|
| Project Name | KRIPA GeoSentinel |
| Project Category | Geospatial Research Project |
| Domain | Remote Sensing & GIS |
| Research Focus | Coastal Freshwater and Surface-Water Monitoring |
| Primary Satellite | Landsat 8 |
| Programming Language | Python |
| Development Environment | Jupyter Notebook |
| Institution | KIIT University |
| Academic Batch | 2027 |
| Project Developer | Ampa Ranjan |
| Development Status | Research in Progress |

### 👨‍💻 Individual Project Contribution

**Ampa Ranjan**

📌 Satellite Data Acquisition, Geospatial Processing, Spectral Analysis & Research Documentation

#### 🔬 Technical Contributions

- Developed the initial satellite imagery discovery and screening workflow.
- Implemented STAC-based satellite scene searches and metadata organisation.
- Performed preliminary scene ranking using cloud cover, footprint coverage and temporal relevance.
- Implemented signed satellite asset access using Planetary Computer.
- Acquired and verified eight Landsat 8 spectral and quality-assessment assets.
- Conducted raster structural validation and spatial alignment checks.
- Retrieved Level-2 reflectance scaling parameters from satellite metadata.
- Implemented QA_PIXEL and QA_RADSAT bit-level inspection.
- Developed preliminary pixel-quality and index-specific eligibility masks.
- Computed NDWI and MNDWI using Landsat 8 surface-reflectance bands.
- Exported georeferenced spectral-index GeoTIFF products.
- Performed preliminary threshold-based water-candidate analysis.
- Conducted NDWI–MNDWI comparison and threshold sensitivity analysis.

#### 📊 Research & Documentation Contributions

- Organised satellite acquisition metadata and scene inventories.
- Recorded raster validation and quality-assessment results.
- Analysed spectral-index statistics and candidate-area estimates.
- Documented the technical processing workflow and research limitations.
- Structured the project for future spatial validation and multi-temporal analysis.

---

## 📂 17. Repository Structure

```text
KRIPA-GeoSentinel/
│
├── README.md
├── COPYRIGHT
├── .gitignore
├── requirements.txt
│
├── notebooks/
│   ├── 01_Environment_and_Data_Checks.ipynb
│   ├── 02_...
│   └── 03_Satellite_and_Environmental_Data_Acquisition.ipynb
│
├── src/
│   ├── acquisition/
│   ├── preprocessing/
│   ├── indices/
│   ├── classification/
│   └── validation/
│
├── data/
│   └── README.md
│
├── outputs/
│   └── README.md
│
├── docs/
│   ├── methodology/
│   └── progress/
│
└── reports/
```

*The directory structure represents the intended repository organisation. Only folders and files actually committed to GitHub should be considered available in the repository.*

---

## 📚 18. Data Sources & References

- **USGS Landsat Collection 2:**  
  https://www.usgs.gov/landsat-missions/landsat-collection-2

- **Microsoft Planetary Computer:**  
  https://planetarycomputer.microsoft.com/

- **SpatioTemporal Asset Catalog (STAC):**  
  https://stacspec.org/

- **Rasterio Documentation:**  
  https://rasterio.readthedocs.io/

- **GeoPandas Documentation:**  
  https://geopandas.org/

- **QGIS Documentation:**  
  https://docs.qgis.org/

Satellite imagery, third-party datasets and external software remain subject to their respective terms and licences.

---

## 🔒 19. Copyright & Intellectual Property

**Copyright © 2026 Ampa Ranjan. All Rights Reserved.**

KRIPA GeoSentinel is an independently developed geospatial research and software project.

This repository is publicly accessible for academic review, research visibility and portfolio demonstration.

No general licence is granted to reproduce, modify, redistribute or commercially exploit the project's original source code, documentation, designs or other original materials without prior written authorisation, except where applicable law or GitHub's Terms of Service provide otherwise.

Access to this repository does not constitute a transfer of intellectual property rights.

Third-party software, datasets, satellite imagery and external materials remain subject to their respective licences and terms.

For permissions, collaboration or commercial licensing enquiries, written authorisation must be obtained from the copyright holder.

---

## ⭐ 20. Acknowledgement

KRIPA GeoSentinel represents an ongoing exploration of satellite remote sensing, geospatial intelligence and environmental research.

The project reflects an interest in applying computational methods and Earth-observation technologies to real-world environmental challenges.

**From Satellite Data to Geospatial Intelligence. 🛰️🌍**

<p align="center">
  <b>KRIPA GeoSentinel</b><br/>
  <i>Observing Earth. Understanding Water. Advancing Geospatial Intelligence.</i>
</p>
