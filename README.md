# Soil Erosion Assessment using USLE in GIS Environment for Paleru Reservoir Watershed

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![ArcGIS](https://img.shields.io/badge/GIS-ArcMap-green.svg)](https://www.esri.com/en-us/arcgis/products/arcgis-desktop)

## 📋 Table of Contents
- [Overview](#overview)
- [Study Area](#study-area)
- [Methodology](#methodology)
- [Data Sources](#data-sources)
- [Key Findings](#key-findings)
- [Installation & Usage](#installation--usage)
- [Results](#results)
- [Acknowledgments](#acknowledgments)
- [Citation](#citation)

## 🌍 Overview

This project presents a comprehensive soil erosion assessment for the Paleru reservoir watershed in Telangana, India, using the Universal Soil Loss Equation (USLE) integrated with Geographic Information Systems (GIS). The study addresses critical environmental challenges facing agricultural sustainability and water resource management in semi-arid regions.

### Key Objectives
- Quantify soil erosion rates across the Paleru watershed
- Identify erosion hotspots for targeted conservation interventions
- Assess the impact of sedimentation on reservoir storage capacity
- Provide actionable insights for sustainable land management

### Problem Statement
The Paleru reservoir has lost approximately **24.3%** of its original storage capacity over four decades due to sedimentation, with soil erosion rates ranging from **0 to 10,009.68 tons/ha/year**, significantly exceeding sustainable thresholds.

## 🗺️ Study Area

**Location**: Paleru Reservoir Watershed, Telangana, India
- **Coordinates**: 77°59'59.01"W to 79°43'46.2"W, 16°56'23.92"N to 17°38'12.24"N
- **Area**: 10,380.14 km² (1,038,013.769 hectares)
- **Districts**: Khammam (primary), Suryapet, Nalgonda
- **Climate**: Semi-arid with annual rainfall of 875-950 mm
- **Elevation Range**: 148m to 715m above MSL

### Watershed Characteristics
- **Primary Land Use**: Agriculture (68.22%), Built-up (13.7%), Barren land (13.39%)
- **Forest Cover**: 3.59%
- **Water Bodies**: 1.1%
- **Major Crops**: Rice, cotton, pulses
- **Reservoir**: Original capacity 184.6 million m³ (constructed 1974)

## 🔬 Methodology

The study employs the **Universal Soil Loss Equation (USLE)**:

```
A = R × K × LS × C × P
```

Where:
- **A** = Average annual soil loss (t/ha/year)
- **R** = Rainfall erosivity factor (MJ·mm/ha·h·year)
- **K** = Soil erodibility factor (t·ha·h/ha·MJ·mm)
- **LS** = Slope length-steepness factor (dimensionless)
- **C** = Cover-management factor (dimensionless)
- **P** = Support practice factor (dimensionless)

### Technical Workflow
1. **Watershed Delineation**: Using SRTM DEM and hydrology tools
2. **Factor Computation**: Spatial analysis of each USLE parameter
3. **Erosion Modeling**: Integration of all factors using raster calculator
4. **Validation**: Field observations and literature comparison
5. **Risk Assessment**: Classification of erosion severity zones

## 📊 Data Sources

| Parameter | Data Source | Resolution/Scale | Period |
|-----------|-------------|------------------|--------|
| **Elevation** | USGS SRTM DEM | 30m | 2000 |
| **Rainfall** | NASA POWER | Point data | 1994-2024 |
| **Soil Properties** | FAO HWSD | 1:1,000,000 | 2012 |
| **Land Cover** | LANDSAT 8 OLI/TIRS | 30m | 2021 |
| **Administrative** | Survey of India | 1:250,000 | 2020 |

### Software & Tools
- **GIS Platform**: ArcMap 10.x with Spatial Analyst
- **Remote Sensing**: ERDAS Imagine, ENVI
- **Statistical Analysis**: R, Python
- **Data Processing**: Microsoft Excel, Google Earth Engine

## 🎯 Key Findings

### Erosion Risk Distribution
| Erosion Category | Rate (t/ha/year) | Area Coverage | Risk Level |
|------------------|------------------|---------------|------------|
| **Slight** | 0-5 | 80-90% | Low |
| **Moderate** | 5-10 | 5-7% | Moderate |
| **High** | 10-20 | 5-7% | High |
| **Very High** | 20-40 | 5-7% | Very High |
| **Severe** | 40-80 | 2-4% | Severe |
| **Very Severe** | 80-10,009.68 | <1% | Critical |

### USLE Factor Analysis

#### Rainfall Erosivity (R Factor)
- **Range**: 88.34 - 89.65 MJ·mm/ha·h·year
- **Distribution**: 30-35% average erosivity, 5-10% very high erosivity

#### Soil Erodibility (K Factor)
- **Range**: 0.015 - 0.18 t·ha·h/ha·MJ·mm
- **Critical Finding**: 75-80% of watershed has highly erodible soils

#### Topographic Factor (LS)
- **Range**: 0 - 73.62 (dimensionless)
- **Terrain**: 10-15% gentle slopes, 5-10% very steep slopes

#### Cover Management (C Factor)
- **Agricultural Land**: 68.22% (C = 0.28)
- **Forest Cover**: 3.59% (C = 0.004)
- **Built-up Areas**: 13.7% (C = 1.0)

#### Conservation Practices (P Factor)
- **Effective Practices**: 48.52% (P = 0.55)
- **No Conservation**: 2.17% (P = 1.0)

## 💻 Installation & Usage

### Prerequisites
```bash
# Required Software
- ArcGIS Desktop 10.x or ArcGIS Pro
- Python 3.8+
- R 4.0+

# Required Python Packages
pip install rasterio
pip install geopandas
pip install numpy
pip install matplotlib
pip install scipy
```

### Repository Structure
```
paleru-erosion-assessment/
│
├── data/
│   ├── raw/                    # Original datasets
│   ├── processed/              # Processed spatial data
│   └── outputs/                # Final results and maps
│
├── scripts/
│   ├── preprocessing/          # Data preparation scripts
│   ├── usle_factors/          # USLE factor computation
│   ├── analysis/              # Erosion analysis and mapping
│   └── validation/            # Model validation scripts
│
├── docs/
│   ├── methodology.md         # Detailed methodology
│   ├── data_dictionary.md     # Data specifications
│   └── results_interpretation.md
│
├── maps/                      # Generated maps and visualizations
├── reports/                   # Technical reports and publications
└── README.md
```

### Quick Start
```bash
# Clone the repository
git clone https://github.com/username/paleru-erosion-assessment.git
cd paleru-erosion-assessment

# Run the complete workflow
python scripts/main_analysis.py

# Generate specific USLE factors
python scripts/usle_factors/calculate_r_factor.py
python scripts/usle_factors/calculate_k_factor.py
python scripts/usle_factors/calculate_ls_factor.py
```

## 📈 Results

### Critical Erosion Zones
- **Hotspot Locations**: Eastern highlands and steep terrain areas
- **Maximum Erosion**: 10,009.68 t/ha/year in unprotected gullies
- **Reservoir Impact**: 24.3% storage capacity loss over 40 years
- **Economic Loss**: INR 18-22 crores annually in irrigation sector

### Conservation Recommendations
1. **Immediate Actions**:
   - Implement terracing on slopes >17°
   - Establish vegetative barriers in high-risk zones
   - Deploy rainwater harvesting systems

2. **Medium-term Strategies**:
   - Reforestation programs in critical areas
   - Cover crop promotion in agricultural zones
   - Community-based conservation initiatives

3. **Long-term Planning**:
   - Integrated watershed management
   - Policy framework development
   - Continuous monitoring systems


### Institution
**Department of Civil Engineering**  
Indian Institute of Technology, Roorkee - 247667, India

## 🙏 Acknowledgments

We extend our heartfelt gratitude to:
- Telangana State Remote Sensing Applications Centre
- Central Water Commission, Government of India
- NASA POWER Data Access Team
- USGS Earth Explorer Platform
- FAO for Harmonized World Soil Database


## 📚 Citation

If you use this work in your research, please cite:

```bibtex
@techreport{SLE2025paleru,
  title={Soil Erosion Assessment using USLE in GIS environment for Paleru reservoir watershed, Telangana, India},
  author={Udhay Kiraan K H},
  institution={Indian Institute of Technology Roorkee},
  year={2025},
  month={April},
  type={Technical Report},
}
```

## 📞 Contact

For questions, collaborations, or technical support:

- **Primary Contact**: Udhay Kiraan K H - [Udhay_k@ce.iitr.ac.in]
- **Institution**: Department of Civil Engineering, IIT Roorkee

## 🔗 Related Links

- [Telangana Irrigation Department](http://irrigation.telangana.gov.in/)
- [USLE Documentation](https://www.ars.usda.gov/research/publications/publication/?seqNo115=68879)
- [NASA POWER Data](https://power.larc.nasa.gov/)

---

**Last Updated**: April 2025  
**Version**: 1.0.0  
**Status**: ✅ Complete

> *This study provides critical insights for soil conservation and sustainable watershed management in semi-arid regions, contributing to the broader goals of environmental sustainability and agricultural resilience.*
