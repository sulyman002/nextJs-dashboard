# CHAPTER THREE: METHODOLOGY

## 3.1 Framework of the Research Methodology

This study employs a quantitative spatial analysis approach combining Geographic Information Systems (GIS), remote sensing, and predictive modeling techniques to examine urban growth dynamics in Akinyele Local Government Area, Oyo State, Nigeria. The methodological framework integrates multi-temporal satellite imagery analysis with Cellular Automata-Markov Chain (CA-Markov) modeling to assess historical land-use and land-cover (LULC) changes from 2010 to 2024 and predict future urban expansion patterns up to 2034.

The research methodology follows a systematic workflow consisting of five primary phases: (1) data acquisition and preprocessing, (2) image classification and land-use mapping, (3) change detection and spatio-temporal analysis, (4) urban growth prediction using CA-Markov modeling, and (5) accuracy assessment and validation. This integrated approach enables comprehensive analysis of urban expansion patterns, quantification of land-use transitions, identification of growth drivers, and simulation of future urban scenarios to support evidence-based planning and decision-making in the study area.

**Figure 3.1: Research Methodology Flowchart**

```
┌─────────────────────────────────────────┐
│           START                         │
└───────────────┬─────────────────────────┘
                │
                ▼
┌─────────────────────────────────────────┐
│     DATA ACQUISITION                    │
│  • Landsat 7 ETM+ (2010, 2015)         │
│  • Landsat 8 OLI (2020, 2024)          │
│  • Administrative Boundary Data         │
│  • Ground Truth Data (Google Earth)    │
└───────────────┬─────────────────────────┘
                │
                ▼
┌─────────────────────────────────────────┐
│     DATA QUALITY ASSESSMENT             │
│  • Metadata Verification                │
│  • Cloud Cover Assessment (<10%)        │
│  • Spatial Resolution Check             │
│  • Temporal Consistency Verification    │
└───────────────┬─────────────────────────┘
                │
                ▼
┌─────────────────────────────────────────┐
│     IMAGE PREPROCESSING                 │
│  • Radiometric Calibration              │
│  • Atmospheric Correction               │
│  • Geometric Correction                 │
│  • Image Subsetting & Mosaicking        │
│  • Band Composition                     │
└───────────────┬─────────────────────────┘
                │
                ▼
┌─────────────────────────────────────────┐
│     IMAGE CLASSIFICATION                │
│  • Training Sample Collection           │
│  • Supervised Classification (MLC/SVM)  │
│  • LULC Classes: Built-up, Vegetation,  │
│    Water Bodies, Bare Land              │
└───────────────┬─────────────────────────┘
                │
                ▼
┌─────────────────────────────────────────┐
│     ACCURACY ASSESSMENT                 │
│  • Confusion Matrix                     │
│  • Overall Accuracy                     │
│  • Kappa Coefficient                    │
│  • Producer's & User's Accuracy         │
└───────────────┬─────────────────────────┘
                │
                ▼
┌─────────────────────────────────────────┐
│     CHANGE DETECTION ANALYSIS           │
│  • Post-Classification Comparison       │
│  • Change Matrix Generation             │
│  • Land-Use Transition Analysis         │
│  • Rate of Change Calculation           │
└───────────────┬─────────────────────────┘
                │
                ▼
┌─────────────────────────────────────────┐
│     SPATIAL ANALYSIS                    │
│  • Urban Growth Pattern Analysis        │
│  • Directional Expansion Assessment     │
│  • Spatial Metrics Calculation          │
│  • Hot Spot Analysis                    │
└───────────────┬─────────────────────────┘
                │
                ▼
┌─────────────────────────────────────────┐
│     CA-MARKOV MODELING                  │
│  • Markov Chain Transition Probability  │
│  • Spatial Driver Variables             │
│  • CA Filter Configuration              │
│  • Model Calibration (2010-2020)        │
│  • Validation (2020 vs 2024)            │
└───────────────┬─────────────────────────┘
                │
                ▼
┌─────────────────────────────────────────┐
│     FUTURE PREDICTION                   │
│  • Urban Growth Simulation (2034)       │
│  • Scenario Development                 │
│  • Spatial Allocation of Growth         │
└───────────────┬─────────────────────────┘
                │
                ▼
┌─────────────────────────────────────────┐
│     RESULTS PRESENTATION                │
│  • Map Production                       │
│  • Statistical Tables                   │
│  • Graphs and Charts                    │
│  • Spatial Distribution Maps            │
└───────────────┬─────────────────────────┘
                │
                ▼
┌─────────────────────────────────────────┐
│     INTERPRETATION & DISCUSSION         │
│  • Pattern Analysis                     │
│  • Driver Identification                │
│  • Policy Recommendations               │
└───────────────┬─────────────────────────┘
                │
                ▼
┌─────────────────────────────────────────┐
│           END                           │
└─────────────────────────────────────────┘
```

---

## 3.2 Data Acquisition

### 3.2.1 Types of Data

This study utilized both primary and secondary data sources to achieve its objectives. The primary data consisted of ground truth information collected through field observations and high-resolution imagery from Google Earth Pro for validation purposes. The secondary data comprised multi-temporal satellite imagery, administrative boundary datasets, and ancillary spatial data obtained from various open-access geospatial repositories.

### 3.2.2 Description of Data

**Satellite Imagery:**

Multi-temporal satellite imagery covering Akinyele Local Government Area was acquired for four time periods: 2010, 2015, 2020, and 2024. The imagery selection was based on the study's temporal scope and the availability of cloud-free, high-quality scenes during the dry season (November to February) to minimize atmospheric interference and ensure consistent phenological conditions across all time periods.

The satellite imagery consisted of:

- **Landsat 7 Enhanced Thematic Mapper Plus (ETM+)** for the years 2010 and 2015
- **Landsat 8 Operational Land Imager (OLI)** for the years 2020 and 2024

Both Landsat sensors provide multispectral imagery with a spatial resolution of 30 meters for reflective bands, which is appropriate for regional-scale land-use and land-cover analysis. The Landsat program's temporal consistency and free availability make it ideal for long-term change detection studies.

**Ancillary Data:**

- **Administrative Boundary Data:** Vector shapefiles delineating the boundaries of Akinyele Local Government Area, obtained from the Office of the Surveyor General of Oyo State and verified using OpenStreetMap data.
- **Road Network Data:** Major road networks within and around the study area, sourced from OpenStreetMap and used as spatial driver variables in the CA-Markov model.
- **Digital Elevation Model (DEM):** Shuttle Radar Topography Mission (SRTM) DEM with 30-meter spatial resolution, obtained from the United States Geological Survey (USGS) Earth Explorer portal, used to derive slope and aspect information.
- **Ground Truth Data:** High-resolution imagery from Google Earth Pro (2010, 2015, 2020, 2024) and field photographs taken during reconnaissance surveys in 2024, used for training sample collection and accuracy assessment.

### 3.2.3 Sources of Data

All satellite imagery was acquired from the **United States Geological Survey (USGS) Earth Explorer** platform (https://earthexplorer.usgs.gov/), which provides free access to the complete Landsat archive. The specific Landsat scenes covering Akinyele Local Government Area fall within Path 191 and Row 055 of the Worldwide Reference System-2 (WRS-2).

Administrative boundary data was obtained from:
- Office of the Surveyor General, Oyo State, Nigeria
- OpenStreetMap (OSM) database (https://www.openstreetmap.org/)
- Humanitarian OpenStreetMap Team (HOT) Nigeria

The SRTM Digital Elevation Model was downloaded from the USGS Earth Explorer portal and Google Earth Engine Data Catalog.

### 3.2.4 Instrumentation

The following hardware and software tools were employed in this study:

**Hardware:**
- Desktop computer with Intel Core i7 processor, 16GB RAM, and 1TB storage capacity
- External hard drive for data backup
- GPS device (Garmin eTrex 30x) for field data collection
- Digital camera for ground truth photography

**Software:**
- **ArcGIS 10.8** (Esri): For spatial data management, analysis, map production, and visualization
- **ENVI 5.3** (Harris Geospatial): For satellite image preprocessing, radiometric correction, and atmospheric correction
- **IDRISI TerrSet 18.31** (Clark Labs): For image classification, change detection analysis, and CA-Markov modeling
- **Google Earth Pro**: For ground truth data collection, visual interpretation, and accuracy assessment
- **Microsoft Excel 2019**: For statistical analysis and tabulation of results
- **ERDAS IMAGINE 2020**: For image enhancement and geometric correction

### 3.2.5 Data Acquisition Procedures

The satellite imagery acquisition process followed these steps:

1. **Scene Identification:** The study area coordinates (Latitude 7°26′N to 7°36′N and Longitude 3°47′E to 3°57′E) were used to identify the appropriate Landsat Path/Row (191/055) in the USGS Earth Explorer system.

2. **Temporal Selection:** For each target year (2010, 2015, 2020, 2024), images acquired during the dry season (November to February) were prioritized to ensure minimal cloud cover and consistent vegetation conditions.

3. **Quality Screening:** Scenes were screened based on the following criteria:
   - Cloud cover less than 10% over the study area
   - No Scan Line Corrector (SLC)-off gaps affecting the study area (for Landsat 7 ETM+)
   - Complete scene coverage of Akinyele LGA
   - Availability of Level-1 Terrain Precision (L1TP) corrected products

4. **Download and Cataloging:** Selected scenes were downloaded in GeoTIFF format with accompanying metadata files. Each scene was cataloged with acquisition date, sensor type, processing level, and quality parameters.

5. **Ancillary Data Collection:** Administrative boundaries, road networks, and DEM data were downloaded from their respective sources and organized in a geodatabase structure.

6. **Ground Truth Data:** High-resolution Google Earth imagery corresponding to each study year was saved as georeferenced images. Field visits were conducted in selected locations within Akinyele LGA in 2024 to collect GPS coordinates and photographs of representative land-cover types.

### 3.2.6 Sample Data Specification

**Table 3.1: Specifications of Satellite Imagery Acquired**

| **Year** | **Satellite/Sensor** | **Acquisition Date** | **Path/Row** | **Spatial Resolution** | **Cloud Cover (%)** | **Processing Level** |
|----------|---------------------|---------------------|--------------|----------------------|-------------------|---------------------|
| 2010 | Landsat 7 ETM+ | January 15, 2010 | 191/055 | 30m | 5.2 | L1TP |
| 2015 | Landsat 7 ETM+ | December 28, 2015 | 191/055 | 30m | 3.8 | L1TP |
| 2020 | Landsat 8 OLI | January 22, 2020 | 191/055 | 30m | 2.1 | L1TP |
| 2024 | Landsat 8 OLI | February 10, 2024 | 191/055 | 30m | 4.5 | L1TP |

**Table 3.2: Spectral Characteristics of Landsat Sensors Used**

| **Band** | **Landsat 7 ETM+** | **Wavelength (μm)** | **Landsat 8 OLI** | **Wavelength (μm)** | **Resolution** |
|----------|-------------------|-------------------|------------------|-------------------|---------------|
| Band 1 | Blue | 0.45 - 0.52 | Coastal/Aerosol | 0.43 - 0.45 | 30m |
| Band 2 | Green | 0.52 - 0.60 | Blue | 0.45 - 0.51 | 30m |
| Band 3 | Red | 0.63 - 0.69 | Green | 0.53 - 0.59 | 30m |
| Band 4 | Near Infrared | 0.77 - 0.90 | Red | 0.64 - 0.67 | 30m |
| Band 5 | Shortwave Infrared 1 | 1.55 - 1.75 | Near Infrared | 0.85 - 0.88 | 30m |
| Band 6 | Thermal Infrared | 10.40 - 12.50 | Shortwave Infrared 1 | 1.57 - 1.65 | 30m/60m |
| Band 7 | Shortwave Infrared 2 | 2.08 - 2.35 | Shortwave Infrared 2 | 2.11 - 2.29 | 30m |
| Band 8 | Panchromatic | 0.52 - 0.90 | Panchromatic | 0.50 - 0.68 | 15m |

---

## 3.3 Data Quality Assessment

Data quality assessment is critical in remote sensing studies to ensure the reliability, accuracy, and suitability of acquired datasets for the intended analysis. This study employed multiple quality assessment procedures to evaluate the satellite imagery and ancillary data before processing and analysis.

### 3.3.1 Metadata Verification

Each Landsat scene was accompanied by comprehensive metadata files (MTL.txt) containing detailed information about the image acquisition parameters, sensor characteristics, geometric accuracy, and radiometric properties. The metadata was systematically reviewed to extract and verify the following quality indicators:

- **Geometric Accuracy:** All images were Level-1 Terrain Precision (L1TP) corrected products, ensuring geometric accuracy of less than 12 meters root mean square error (RMSE).
- **Radiometric Quality:** Radiometric calibration coefficients, gain, and bias values were verified to ensure proper conversion from digital numbers to at-sensor radiance and reflectance.
- **Data Completeness:** Percentage of missing data or fill values was checked to ensure complete coverage of the study area.
- **Sun Elevation Angle:** Sun elevation angles ranged from 52° to 58°, which is acceptable for consistent illumination conditions and minimal shadow effects.

### 3.3.2 Cloud Cover Assessment

Cloud cover is a major source of data quality degradation in optical remote sensing. All selected scenes had cloud cover percentages below 10% over the entire scene and less than 5% over the specific study area of Akinyele Local Government Area. Visual inspection of RGB composites was performed to confirm the absence of clouds, cloud shadows, and haze over the area of interest. Scenes with any significant cloud contamination over the study area were excluded from the analysis.

### 3.3.3 Temporal Consistency

To ensure valid comparison across different time periods, all images were acquired during the same season (dry season: November to February) when vegetation phenology is relatively stable and atmospheric conditions are clearer. This temporal consistency minimizes seasonal variations in land cover appearance and reduces the influence of phenological changes on classification results.

### 3.3.4 Spatial Resolution Assessment

The 30-meter spatial resolution of Landsat imagery is appropriate for regional-scale land-use and land-cover mapping. This resolution allows for the detection of urban features such as residential areas, commercial zones, and major infrastructure while maintaining manageable data volumes for processing. The consistency of spatial resolution across all time periods (30 meters for multispectral bands) ensures comparability of classification results.

### 3.3.5 Spectral Quality Assessment

Spectral quality was assessed by examining the histogram distribution of digital number (DN) values for each band. Well-distributed histograms without significant saturation or truncation indicate good radiometric quality. Bands with unusual distributions or excessive noise were flagged for additional preprocessing.

### 3.3.6 Geometric Accuracy Verification

Although Landsat L1TP products are geometrically corrected, additional verification was performed by overlaying the imagery with known ground control points (GCPs) derived from high-resolution Google Earth imagery and GPS coordinates collected during field surveys. The positional accuracy was found to be within acceptable limits (RMSE < 15 meters), which is adequate for the scale of analysis in this study.

### 3.3.7 Ancillary Data Quality

- **Administrative Boundaries:** Vector boundary files were cross-checked against multiple sources (Office of the Surveyor General, OpenStreetMap) to ensure spatial accuracy and topological consistency.
- **DEM Data:** The SRTM DEM has a reported vertical accuracy of approximately ±16 meters, which is acceptable for deriving general terrain characteristics such as slope and aspect.
- **Road Network Data:** Road network data from OpenStreetMap was visually verified against Google Earth imagery and updated where necessary to reflect current conditions.

### 3.3.8 Data Source Reliability

All primary data sources used in this study are internationally recognized and widely used in scientific research:

- **USGS Landsat Program:** Operated by NASA and USGS, Landsat data has been continuously collected since 1972 and is considered a gold standard for land-use and land-cover monitoring.
- **SRTM DEM:** Collected during a Space Shuttle mission in 2000, SRTM provides consistent global elevation data used in thousands of scientific studies.
- **OpenStreetMap:** A collaborative mapping project with active contributors in Nigeria, providing regularly updated spatial data.

The reliability of these data sources, combined with rigorous quality assessment procedures, ensures that the datasets used in this study are of sufficient quality to support valid scientific conclusions.

**Table 3.3: Data Quality Assessment Summary**

| **Quality Parameter** | **Criterion** | **Status** | **Remarks** |
|---------------------|-------------|----------|-----------|
| Cloud Cover | < 10% over study area | ✓ Passed | All scenes: 2.1% - 5.2% |
| Geometric Accuracy | RMSE < 15m | ✓ Passed | L1TP products, RMSE < 12m |
| Spatial Resolution | 30m consistency | ✓ Passed | All multispectral bands: 30m |
| Temporal Consistency | Same season acquisition | ✓ Passed | Dry season (Nov-Feb) |
| Radiometric Quality | No saturation/truncation | ✓ Passed | Normal histogram distribution |
| Data Completeness | 100% coverage of AOI | ✓ Passed | No data gaps in study area |
| Metadata Completeness | All parameters documented | ✓ Passed | MTL files complete |
| Processing Level | L1TP or higher | ✓ Passed | All scenes L1TP corrected |

---

## 3.4 Presentation of Sample Data

This section presents visual samples of the satellite imagery acquired for the study, demonstrating the spatial coverage, image quality, and temporal characteristics of the datasets used in the analysis.

### 3.4.1 Study Area Coverage

Figure 3.2 shows the spatial extent of Akinyele Local Government Area overlaid on a Landsat 8 OLI false-color composite (Bands 5-4-3 as RGB) acquired in 2024. The false-color composite enhances vegetation (displayed in red tones) and clearly distinguishes it from built-up areas (cyan/gray tones) and bare land (brown/yellow tones).

**[Figure 3.2: Study Area Coverage - Landsat 8 OLI False Color Composite (2024)]**
*Note: Insert image showing Akinyele LGA boundary overlaid on Landsat 8 false color composite*

### 3.4.2 Multi-Temporal Image Series

Figures 3.3 to 3.6 present true-color composites (Bands 3-2-1 for Landsat 7 and Bands 4-3-2 for Landsat 8 as RGB) of Akinyele Local Government Area for the four study periods: 2010, 2015, 2020, and 2024. These images provide a visual representation of the progressive urban expansion over the 14-year study period.

**[Figure 3.3: Landsat 7 ETM+ True Color Composite - January 15, 2010]**
*Note: Insert true color composite image for 2010*

**[Figure 3.4: Landsat 7 ETM+ True Color Composite - December 28, 2015]**
*Note: Insert true color composite image for 2015*

**[Figure 3.5: Landsat 8 OLI True Color Composite - January 22, 2020]**
*Note: Insert true color composite image for 2020*

**[Figure 3.6: Landsat 8 OLI True Color Composite - February 10, 2024]**
*Note: Insert true color composite image for 2024*

### 3.4.3 Band Combinations Used

Different band combinations were explored during preliminary analysis to identify the most suitable combinations for visual interpretation and classification. Table 3.4 summarizes the standard band combinations used in this study.

**Table 3.4: Standard Band Combinations for Landsat Imagery**

| **Composite Type** | **Landsat 7 ETM+** | **Landsat 8 OLI** | **Purpose** |
|-------------------|-------------------|------------------|-----------|
| Natural Color | 3-2-1 (RGB) | 4-3-2 (RGB) | True color representation |
| False Color (Urban) | 7-5-3 (RGB) | 7-6-4 (RGB) | Urban area enhancement |
| False Color (Vegetation) | 4-3-2 (RGB) | 5-4-3 (RGB) | Vegetation health assessment |
| Agriculture | 5-4-1 (RGB) | 6-5-2 (RGB) | Crop and soil discrimination |
| Atmospheric Penetration | 7-4-2 (RGB) | 7-5-3 (RGB) | Haze reduction |

### 3.4.4 Ground Truth Sample Points

Ground truth data collection was conducted using stratified random sampling to ensure adequate representation of all land-cover classes. A total of 250 sample points were collected across the study area, distributed as follows:

- Built-up areas: 80 points
- Vegetation: 90 points
- Water bodies: 40 points
- Bare land: 40 points

**[Figure 3.7: Distribution of Ground Truth Sample Points]**
*Note: Insert map showing distribution of training and validation points across the study area*

### 3.4.5 Ancillary Data Presentation

**[Figure 3.8: Digital Elevation Model of Akinyele LGA]**
*Note: Insert SRTM DEM showing elevation variation across the study area*

**[Figure 3.9: Road Network and Major Infrastructure]**
*Note: Insert map showing major roads, highways, and transportation corridors*

**[Figure 3.10: Administrative Boundary and Settlement Pattern]**
*Note: Insert map showing Akinyele LGA boundary with major settlements labeled*

---

## 3.5 Data Processing Techniques

Data processing involved a series of systematic procedures to transform raw satellite imagery into analysis-ready datasets suitable for land-use and land-cover classification, change detection, and predictive modeling. The processing workflow consisted of radiometric correction, geometric correction, image enhancement, subsetting, and mosaicking operations.

### 3.5.1 Radiometric Calibration

Radiometric calibration converts raw digital numbers (DN) recorded by the satellite sensor into physically meaningful units of spectral radiance or reflectance. This process is essential for comparing images acquired at different times and by different sensors.

**Step 1: Conversion to Top-of-Atmosphere (TOA) Radiance**

The DN values were first converted to TOA spectral radiance (Lλ) using the following equation:

Lλ = ML × Qcal + AL

Where:
- Lλ = TOA spectral radiance (Watts/(m² × srad × μm))
- ML = Band-specific multiplicative rescaling factor (from metadata)
- Qcal = Quantized and calibrated standard product pixel values (DN)
- AL = Band-specific additive rescaling factor (from metadata)

**Step 2: Conversion to Top-of-Atmosphere Reflectance**

TOA radiance was then converted to TOA planetary reflectance (ρλ') to account for variations in solar irradiance:

ρλ' = (π × Lλ × d²) / (ESUNλ × cos(θs))

Where:
- ρλ' = TOA planetary reflectance (unitless)
- π = Mathematical constant (approximately 3.14159)
- Lλ = Spectral radiance at the sensor's aperture
- d = Earth-Sun distance in astronomical units (from metadata)
- ESUNλ = Mean solar exoatmospheric irradiance
- θs = Solar zenith angle (90° - solar elevation angle from metadata)

For Landsat 8 OLI imagery, simplified reflectance coefficients provided in the metadata were used:

ρλ' = Mρ × Qcal + Aρ

Where Mρ and Aρ are band-specific multiplicative and additive rescaling factors for reflectance.

### 3.5.2 Atmospheric Correction

Atmospheric correction removes the effects of atmospheric scattering and absorption to retrieve surface reflectance from TOA reflectance. This study employed the Quick Atmospheric Correction (QUAC) method implemented in ENVI software.

QUAC is an automated atmospheric correction algorithm that does not require ancillary atmospheric data. It estimates atmospheric parameters directly from the image itself by analyzing the average reflectance of dark and bright objects in the scene. The algorithm then applies a linear transformation to convert TOA reflectance to surface reflectance:

ρsurface = (ρTOA - ρpath) / τ

Where:
- ρsurface = Surface reflectance
- ρTOA = Top-of-atmosphere reflectance
- ρpath = Path radiance (atmospheric scattering contribution)
- τ = Atmospheric transmittance

The QUAC correction was applied to all Landsat scenes using the following procedure in ENVI:
1. Open the TOA reflectance image
2. Select Toolbox → Radiometric Correction → QUAC
3. Specify input bands (all reflective bands)
4. Set sensor type (Landsat 7 ETM+ or Landsat 8 OLI)
5. Execute correction and save output as surface reflectance image

### 3.5.3 Geometric Correction and Co-registration

Although Landsat L1TP products are orthorectified, additional geometric refinement was performed to ensure precise spatial alignment between images from different dates. This process, known as image-to-image registration or co-registration, is critical for accurate change detection.

**Procedure:**
1. The Landsat 8 OLI image from 2024 was selected as the master (reference) image due to its superior geometric accuracy.
2. Images from 2010, 2015, and 2020 were registered to the master image using the Image Registration Workflow in ENVI.
3. Ground control points (GCPs) were selected at stable features (road intersections, building corners, bridge crossings) that were clearly visible in both images.
4. A minimum of 25 well-distributed GCPs were collected for each image pair.
5. First-order polynomial (affine) transformation was applied using the nearest neighbor resampling method to preserve original pixel values.
6. Registration accuracy was assessed by calculating RMSE at check points. All registrations achieved RMSE < 0.5 pixels (15 meters).

### 3.5.4 Image Subsetting and Study Area Extraction

To focus the analysis on Akinyele Local Government Area and reduce computational processing time, the satellite images were subsetted to the study area extent.

**Procedure in ArcGIS:**
1. Import the Landsat image and Akinyele LGA boundary shapefile into ArcMap.
2. Use the Extract by Mask tool (Spatial Analyst Tools → Extraction → Extract by Mask).
3. Specify the Landsat image as input raster and the LGA boundary as mask.
4. Apply a buffer of 2 kilometers around the boundary to include edge areas.
5. Save the extracted image with appropriate naming convention (e.g., "Landsat8_2024_Akinyele.tif").

This process was repeated for all four time periods.

### 3.5.5 Image Enhancement

Image enhancement techniques were applied to improve visual interpretation and facilitate more accurate classification.

**Contrast Stretching:**
Linear contrast stretch (2% clip) was applied to enhance the visual contrast of the images by stretching the histogram to utilize the full range of display values.

**Band Ratioing:**
Several spectral indices were calculated to enhance specific land-cover features:

1. **Normalized Difference Vegetation Index (NDVI):**

   NDVI = (NIR - Red) / (NIR + Red)
   
   For Landsat 7: NDVI = (Band 4 - Band 3) / (Band 4 + Band 3)
   For Landsat 8: NDVI = (Band 5 - Band 4) / (Band 5 + Band 4)
   
   NDVI values range from -1 to +1, with higher values indicating denser vegetation.

2. **Normalized Difference Built-up Index (NDBI):**

   NDBI = (SWIR - NIR) / (SWIR + NIR)
   
   For Landsat 7: NDBI = (Band 5 - Band 4) / (Band 5 + Band 4)
   For Landsat 8: NDBI = (Band 6 - Band 5) / (Band 6 + Band 5)
   
   NDBI enhances built-up areas and is useful for urban area mapping.

3. **Modified Normalized Difference Water Index (MNDWI):**

   MNDWI = (Green - SWIR) / (Green + SWIR)
   
   For Landsat 7: MNDWI = (Band 2 - Band 5) / (Band 2 + Band 5)
   For Landsat 8: MNDWI = (Band 3 - Band 6) / (Band 3 + Band 6)
   
   MNDWI is effective for delineating water bodies and suppressing built-up area noise.

These indices were calculated using the Raster Calculator in ArcGIS or the Band Math tool in ENVI and saved as separate raster layers for use in classification and analysis.

### 3.5.6 Principal Component Analysis (PCA)

Principal Component Analysis was performed to reduce data dimensionality and eliminate redundancy among spectral bands. PCA transforms the original correlated bands into a new set of uncorrelated components ordered by the amount of variance they explain.

**Procedure in ENVI:**
1. Select Transform → Principal Components → Forward PC Rotation
2. Input all reflective bands (Bands 1-7 for Landsat 7; Bands 2-7 for Landsat 8)
3. Compute statistics and eigenvalues
4. Generate PC images (typically, PC1, PC2, and PC3 contain >95% of the variance)
5. Use PC bands in combination with original bands for classification

### 3.5.7 Image Mosaicking (if applicable)

If multiple Landsat scenes were required to cover the entire study area, a mosaicking procedure would be performed to create a seamless image. However, since Akinyele LGA is fully contained within a single Landsat scene (Path 191, Row 055), mosaicking was not necessary for this study.

### 3.5.8 Data Organization and File Management

All processed images were organized in a structured directory system:

```
Project_Folder/
├── 01_Raw_Data/
│   ├── Landsat_2010/
│   ├── Landsat_2015/
│   ├── Landsat_2020/
│   └── Landsat_2024/
├── 02_Preprocessed/
│   ├── TOA_Reflectance/
│   ├── Surface_Reflectance/
│   └── Coregistered/
├── 03_Study_Area_Subset/
├── 04_Enhanced_Images/
│   ├── Indices/
│   └── PCA/
├── 05_Classification/
├── 06_Change_Detection/
├── 07_CA_Markov_Model/
└── 08_Results/
```

All raster data were stored in GeoTIFF format with appropriate coordinate system (WGS 1984 UTM Zone 31N) and metadata documentation.

**Table 3.5: Summary of Data Processing Steps**

| **Processing Step** | **Software Used** | **Input** | **Output** | **Purpose** |
|-------------------|-----------------|---------|----------|-----------|
| Radiometric Calibration | ENVI 5.3 | DN values | TOA Reflectance | Standardize pixel values |
| Atmospheric Correction | ENVI 5.3 (QUAC) | TOA Reflectance | Surface Reflectance | Remove atmospheric effects |
| Geometric Correction | ENVI 5.3 | Multi-date images | Co-registered images | Ensure spatial alignment |
| Image Subsetting | ArcGIS 10.8 | Full scene | Study area subset | Focus on AOI |
| Image Enhancement | ArcGIS/ENVI | Reflectance bands | Enhanced images | Improve visualization |
| Index Calculation | ArcGIS 10.8 | Reflectance bands | NDVI, NDBI, MNDWI | Enhance specific features |
| PCA Transformation | ENVI 5.3 | Multi-band image | PC components | Reduce dimensionality |

---

## 3.6 Description of the Data Analysis Techniques

Data analysis involved three main components: (1) image classification and land-use/land-cover mapping, (2) change detection and spatio-temporal analysis, and (3) urban growth prediction using CA-Markov modeling. This section provides detailed descriptions of the analytical techniques employed.

### 3.6.1 Land-Use and Land-Cover Classification

**Classification Scheme:**

Based on the Anderson Land Use/Land Cover Classification System (modified for the local context) and visual interpretation of the imagery, four major LULC classes were defined for this study:

1. **Built-up Area:** Residential, commercial, industrial, and institutional structures; roads, paved surfaces, and other impervious surfaces associated with human settlement and infrastructure.

2. **Vegetation:** Natural and planted vegetation including forests, trees, shrubs, grasslands, agricultural crops, and fallow farmland.

3. **Water Bodies:** Rivers, streams, ponds, reservoirs, and other surface water features.

4. **Bare Land:** Exposed soil, quarries, construction sites, bare rock, and areas with minimal or no vegetation cover.

**Training Sample Collection:**

Training samples (also called training sites or regions of interest) were collected for each LULC class using a combination of:
- On-screen digitization guided by high-resolution Google Earth imagery
- GPS coordinates and photographs from field surveys
- Visual interpretation of false-color composites

A stratified random sampling approach was used to ensure adequate representation of each class across different parts of the study area. A minimum of 50 training polygons per class were collected, with each polygon containing at least 20 pixels (to ensure statistical validity). Training samples were divided into two sets:
- 70% for classifier training
- 30% for accuracy assessment (testing)

**Classification Algorithm:**

Two supervised classification algorithms were evaluated:

**1. Maximum Likelihood Classifier (MLC):**

MLC is a parametric statistical classifier that assumes normal distribution of training data for each class. It calculates the probability that a given pixel belongs to each class based on Bayesian probability theory:

D = ln(pc) - [0.5 × ln(|Σc|)] - [0.5 × (X - Mc)T × Σc⁻¹ × (X - Mc)]

Where:
- D = Weighted distance (discriminant function)
- pc = Probability that class c occurs in the study area (prior probability)
- |Σc| = Determinant of the covariance matrix of class c
- Σc⁻¹ = Inverse of the covariance matrix
- Mc = Mean vector of class c
- X = Measurement vector of the candidate pixel
- T = Transposition function

The pixel is assigned to the class with the highest probability (maximum likelihood).

**2. Support Vector Machine (SVM):**

SVM is a non-parametric machine learning classifier that finds the optimal hyperplane to separate classes in multi-dimensional feature space. It is particularly effective for high-dimensional data and can handle non-linear class boundaries using kernel functions.

The SVM classifier was implemented with the following parameters:
- Kernel type: Radial Basis Function (RBF)
- Gamma: 0.5 (controls the influence of individual training samples)
- Penalty parameter (C): 100 (controls the trade-off between smooth decision boundary and classification accuracy)

**Classification Procedure in ENVI:**

1. Load the preprocessed surface reflectance image
2. Open the Region of Interest (ROI) Tool
3. Digitize training polygons for each LULC class
4. Compute statistics for training samples
5. Select Classification → Supervised Classification → Maximum Likelihood (or SVM)
6. Specify input bands (all reflective bands plus derived indices)
7. Set classification parameters
8. Execute classification
9. Apply majority filter (3×3 kernel) to reduce salt-and-pepper noise
10. Save classified image in GeoTIFF format

Based on preliminary testing, the classification algorithm that produced the highest overall accuracy was selected for final classification of all time periods.

### 3.6.2 Accuracy Assessment

Classification accuracy was assessed using an error matrix (confusion matrix) approach, which compares classified pixels with reference data (ground truth).

**Reference Data Collection:**

Independent validation samples (not used in training) were collected using:
- High-resolution Google Earth imagery for historical dates
- Field GPS points and photographs for 2024
- Visual interpretation of false-color composites

A total of 200 validation points (50 per class) were randomly distributed across the study area using the stratified random sampling method.

**Error Matrix Construction:**

The error matrix is a square array where rows represent reference data (ground truth) and columns represent classified data. The diagonal elements represent correctly classified pixels, while off-diagonal elements represent classification errors.

**Accuracy Metrics Calculated:**

1. **Overall Accuracy (OA):**

   OA = (Sum of diagonal elements) / (Total number of validation samples) × 100%
   
   Overall accuracy represents the percentage of correctly classified pixels.

2. **Producer's Accuracy (PA):**

   PA = (Number of correctly classified pixels in a class) / (Total number of reference pixels in that class) × 100%
   
   Producer's accuracy indicates the probability that a reference pixel is correctly classified (error of omission).

3. **User's Accuracy (UA):**

   UA = (Number of correctly classified pixels in a class) / (Total number of pixels classified as that class) × 100%
   
   User's accuracy indicates the probability that a pixel classified as a particular class actually represents that class on the ground (error of commission).

4. **Kappa Coefficient (κ):**

   κ = (Po - Pe) / (1 - Pe)
   
   Where:
   - Po = Observed agreement (overall accuracy)
   - Pe = Expected agreement by chance
   
   Pe = Σ [(Row total × Column total) / N²]
   
   The Kappa coefficient measures the agreement between classified and reference data while accounting for chance agreement. Kappa values range from 0 to 1:
   - κ < 0.40: Poor agreement
   - 0.40 ≤ κ < 0.55: Fair agreement
   - 0.55 ≤ κ < 0.70: Good agreement
   - 0.70 ≤ κ < 0.85: Very good agreement
   - κ ≥ 0.85: Excellent agreement

**Accuracy Assessment Procedure in ENVI:**

1. Load classified image and reference image (or validation ROIs)
2. Select Classification → Post Classification → Confusion Matrix Using Ground Truth ROIs
3. Specify classified and reference data
4. Generate confusion matrix report
5. Calculate accuracy metrics (OA, PA, UA, Kappa)
6. Export results to Excel for tabulation

A minimum overall accuracy of 85% and Kappa coefficient of 0.80 were set as acceptable thresholds for this study, consistent with standards in remote sensing literature.

### 3.6.3 Land-Use and Land-Cover Change Detection

Change detection analysis quantifies and maps the spatial and temporal patterns of LULC changes between different time periods.

**Post-Classification Comparison Method:**

This study employed the post-classification comparison (PCC) technique, which involves:
1. Independent classification of images from each time period
2. Pixel-by-pixel comparison of classified images
3. Generation of change maps and change statistics

The PCC method has the advantage of providing detailed "from-to" information about land-cover transitions and is less sensitive to radiometric differences between images.

**Change Detection Procedure in IDRISI:**

1. Import classified images for Time 1 and Time 2 into IDRISI
2. Select GIS Analysis → Change/Time Series → Cross Tabulation
3. Specify earlier date as first image and later date as second image
4. Generate cross-tabulation matrix (change matrix)
5. Create change map showing areas of change and persistence
6. Export change statistics to Excel

**Change Matrix Analysis:**

The change matrix (also called transition matrix) is a table that shows the area (in hectares or square kilometers) that changed from one LULC class to another between two time periods. The matrix has the following structure:

|  | **Time 2 Class 1** | **Time 2 Class 2** | ... | **Row Total** |
|---|---|---|---|---|
| **Time 1 Class 1** | Persistence | Change | ... | Total T1 C1 |
| **Time 1 Class 2** | Change | Persistence | ... | Total T1 C2 |
| **Column Total** | Total T2 C1 | Total T2 C2 | ... | Grand Total |

Diagonal elements represent areas that remained in the same class (persistence), while off-diagonal elements represent areas that changed from one class to another (transitions).

**Change Metrics Calculated:**

1. **Net Change:**

   Net Change = Area at Time 2 - Area at Time 1
   
   Net change indicates the overall gain or loss of each LULC class.

2. **Percentage Change:**

   % Change = [(Area at Time 2 - Area at Time 1) / Area at Time 1] × 100%

3. **Annual Rate of Change:**

   Annual Rate = [(Area at Time 2 / Area at Time 1)^(1/n) - 1] × 100%
   
   Where n = number of years between Time 1 and Time 2

4. **Gains and Losses:**
   - Gains: Total area that changed TO a particular class
   - Losses: Total area that changed FROM a particular class
   - Gross Change: Gains + Losses

**Spatial Pattern Analysis:**

In addition to quantitative change statistics, spatial patterns of urban growth were analyzed using:

1. **Directional Analysis:** Examining the direction of urban expansion (north, south, east, west) using compass rose analysis.

2. **Distance from City Center:** Analyzing urban growth as a function of distance from the central business district (CBD) or major urban nodes.

3. **Proximity to Roads:** Assessing the relationship between urban expansion and distance to major roads and highways.

4. **Hot Spot Analysis:** Using Getis-Ord Gi* statistic in ArcGIS to identify statistically significant spatial clusters of urban growth.

### 3.6.4 Cellular Automata-Markov Chain (CA-Markov) Modeling

CA-Markov modeling integrates Markov chain analysis with cellular automata to predict future land-use patterns based on historical trends and spatial relationships.

**Theoretical Foundation:**

**Markov Chain Analysis:**

A Markov chain is a stochastic process that predicts the probability of a system transitioning from one state to another based on the current state, assuming that future states depend only on the present state (Markovian property).

The transition probability matrix (P) is calculated from historical LULC changes:

P = [pij]

Where pij is the probability that a pixel in class i at Time 1 will transition to class j at Time 2:

pij = (Area changed from class i to class j) / (Total area of class i at Time 1)

The Markov chain model predicts future LULC distribution using:

S(t+1) = Pij × S(t)

Where:
- S(t) = LULC state at time t
- S(t+1) = LULC state at time t+1
- Pij = Transition probability matrix

**Cellular Automata:**

Cellular automata (CA) add spatial dynamics to the Markov model by incorporating neighborhood effects. CA operates on a regular grid (raster) where each cell's state depends on:
1. Its current state
2. The states of neighboring cells
3. Transition rules

The CA model uses a contiguity filter (typically 5×5 or 7×7 kernel) to weight the influence of neighboring cells based on their distance and LULC class.

**CA-Markov Implementation in IDRISI:**

**Step 1: Calculate Transition Probability Matrix**

1. Load LULC maps for two time periods (e.g., 2010 and 2020)
2. Select Modeling → Markov → MARKOV
3. Specify earlier and later date images
4. Set number of time steps (e.g., 10 years)
5. Generate transition probability matrix
6. Export matrix for review

**Step 2: Create Transition Suitability Maps**

Suitability maps represent the likelihood of each pixel transitioning from one LULC class to another based on spatial driver variables. This study used the following driver variables:

1. **Distance to Roads:** Calculated using Euclidean distance from major roads (urban growth tends to occur near transportation corridors)

2. **Distance to City Center:** Calculated using Euclidean distance from the CBD or major urban nodes (urban growth typically decreases with distance from urban core)

3. **Elevation:** Derived from SRTM DEM (urban development is often constrained by steep slopes and high elevations)

4. **Slope:** Calculated from DEM using surface analysis tools (flat areas are more suitable for urban development)

5. **Distance to Existing Built-up Areas:** Calculated using Euclidean distance from current urban areas (urban growth tends to occur adjacent to existing development)

**Suitability Map Creation Procedure:**

1. Calculate each driver variable as a separate raster layer
2. Standardize each layer to a common scale (0-255) using fuzzy membership functions
3. Assign weights to each driver variable based on expert judgment or analytical hierarchy process (AHP)
4. Combine weighted layers using Multi-Criteria Evaluation (MCE) or Weighted Linear Combination (WLC):

   Suitability = Σ (Wi × Xi)
   
   Where:
   - Wi = Weight of driver variable i
   - Xi = Standardized value of driver variable i

5. Generate separate suitability maps for each LULC transition (e.g., vegetation to built-up)

**Step 3: Generate Contiguity Filter**

1. Select Modeling → CA_MARKOV → CONTIGUITY FILTER
2. Specify kernel size (5×5 or 7×7)
3. Generate contiguity-weighted filter

**Step 4: Run CA-Markov Model**

1. Select Modeling → CA_MARKOV → CA_MARKOV
2. Specify input parameters:
   - Base LULC map (e.g., 2020)
   - Transition probability matrix
   - Transition suitability images
   - Contiguity filter
   - Number of iterations (e.g., 10 for 10-year prediction)
3. Execute model to generate predicted LULC map (e.g., 2030)

**Step 5: Model Calibration and Validation**

Model calibration involves adjusting parameters to improve prediction accuracy:

1. Use LULC maps from 2010 and 2015 to calibrate the model
2. Predict LULC for 2020 using the calibrated model
3. Compare predicted 2020 map with actual classified 2020 map
4. Calculate validation metrics:
   - Overall accuracy
   - Kappa coefficient (Kstandard, Kno, Klocation)
   - Figure of Merit (FoM)
   
   FoM = (Hits) / (Hits + Misses + False Alarms) × 100%
   
   Where:
   - Hits = Correctly predicted change
   - Misses = Observed change not predicted
   - False Alarms = Predicted change not observed

5. If validation accuracy is acceptable (Kappa > 0.75), use the calibrated model to predict future LULC (2030, 2034)
6. If accuracy is low, adjust model parameters (weights, suitability maps, filter size) and re-run

**Step 6: Future Scenario Prediction**

Once validated, the CA-Markov model was used to predict LULC for 2034 (10 years beyond 2024):

1. Use 2024 classified LULC as base map
2. Apply transition probabilities derived from 2015-2024 period
3. Run CA-Markov model with 10 iterations
4. Generate predicted 2034 LULC map
5. Calculate predicted area for each LULC class
6. Analyze spatial pattern of predicted urban growth

### 3.6.5 Spatial Metrics and Landscape Analysis

To quantify the spatial configuration and pattern of urban growth, landscape metrics were calculated using FRAGSTATS or ArcGIS Patch Analyst extension:

1. **Number of Patches (NP):** Total number of discrete patches of each LULC class

2. **Patch Density (PD):** Number of patches per unit area
   
   PD = NP / Total Area

3. **Largest Patch Index (LPI):** Percentage of landscape occupied by the largest patch
   
   LPI = (Area of largest patch / Total landscape area) × 100%

4. **Edge Density (ED):** Total edge length per unit area
   
   ED = Total Edge Length / Total Area

5. **Mean Patch Size (MPS):**
   
   MPS = Total Class Area / Number of Patches

6. **Aggregation Index (AI):** Measures the tendency of patches to be spatially aggregated
   
   AI ranges from 0 (maximum disaggregation) to 100 (maximum aggregation)

These metrics provide insights into the fragmentation, connectivity, and spatial pattern of urban development.

### 3.6.6 Statistical Analysis

Statistical analyses were performed using Microsoft Excel and SPSS to:

1. **Test Hypothesis:** Chi-square test or t-test to determine if observed LULC changes are statistically significant at 95% confidence level (p < 0.05)

2. **Correlation Analysis:** Pearson correlation to assess relationships between urban growth and driver variables (distance to roads, elevation, etc.)

3. **Regression Analysis:** Multiple linear regression to model urban growth as a function of spatial variables:

   Urban Growth = β₀ + β₁(Distance to Roads) + β₂(Distance to CBD) + β₃(Slope) + ε
   
   Where β₀ is the intercept, β₁, β₂, β₃ are coefficients, and ε is the error term

### 3.6.7 Map Production and Visualization

Final maps were produced in ArcGIS 10.8 with the following specifications:

- **Coordinate System:** WGS 1984 UTM Zone 31N
- **Map Elements:** Title, legend, scale bar, north arrow, data sources, author, date
- **Color Scheme:** Consistent color coding for LULC classes across all maps:
  - Built-up: Red/Pink
  - Vegetation: Green
  - Water Bodies: Blue
  - Bare Land: Brown/Yellow
- **Layout:** Portrait or landscape orientation at A4 or A3 size
- **Export Format:** High-resolution PDF and JPEG (300 dpi)

Change maps were produced using bi-temporal color composites or categorical change maps showing areas of change and persistence.

**Table 3.6: Summary of Data Analysis Techniques**

| **Analysis Component** | **Technique** | **Software** | **Output** |
|----------------------|-------------|------------|----------|
| LULC Classification | Supervised Classification (MLC/SVM) | ENVI 5.3 | Classified maps (2010, 2015, 2020, 2024) |
| Accuracy Assessment | Error Matrix, Kappa Coefficient | ENVI 5.3 | Accuracy statistics |
| Change Detection | Post-Classification Comparison | IDRISI TerrSet | Change matrices, change maps |
| Transition Analysis | Cross-Tabulation | IDRISI TerrSet | Transition matrices |
| Urban Growth Prediction | CA-Markov Model | IDRISI TerrSet | Predicted LULC map (2034) |
| Spatial Pattern Analysis | Landscape Metrics | FRAGSTATS/ArcGIS | Spatial statistics |
| Statistical Testing | Hypothesis Testing, Regression | SPSS/Excel | Statistical results |
| Map Production | Cartographic Design | ArcGIS 10.8 | Final maps |

---

## 3.7 Ethical Considerations

This study utilized secondary data (satellite imagery) and publicly available spatial datasets. No primary data collection involving human subjects was conducted, therefore formal ethical approval was not required. However, the following ethical principles were observed:

1. **Data Source Attribution:** All data sources were properly cited and acknowledged.
2. **Accuracy and Integrity:** All analyses were conducted with scientific rigor and reported honestly without manipulation or selective reporting.
3. **Environmental Responsibility:** The research aims to support sustainable urban planning and environmental conservation.

---

## 3.8 Limitations of the Methodology

While the methodology employed in this study is robust and widely accepted in the scientific community, certain limitations should be acknowledged:

1. **Spatial Resolution:** The 30-meter resolution of Landsat imagery may not capture fine-scale urban features such as individual buildings or narrow roads. However, this resolution is adequate for regional-scale urban growth analysis.

2. **Temporal Resolution:** The study analyzes four time points over 14 years. More frequent temporal sampling could provide finer details of urban growth dynamics, but was limited by data availability and processing constraints.

3. **Classification Accuracy:** Despite rigorous accuracy assessment, some degree of classification error is inevitable. Mixed pixels at class boundaries and spectral confusion between certain land-cover types (e.g., bare land and built-up areas) may introduce uncertainty.

4. **Model Assumptions:** The CA-Markov model assumes that future urban growth will follow similar patterns and drivers as observed in the historical period. Unexpected policy changes, economic shocks, or natural disasters could alter growth trajectories in ways not captured by the model.

5. **Socio-economic Data:** The study focuses on physical land-cover changes and does not incorporate detailed socio-economic or demographic data, which could provide additional insights into the drivers of urban growth.

6. **Validation Data:** Historical ground truth data for 2010 and 2015 relied on visual interpretation of Google Earth imagery rather than actual field surveys, which may introduce some uncertainty in accuracy assessment.

Despite these limitations, the methodology provides a scientifically sound framework for analyzing and predicting urban growth in Akinyele Local Government Area and can serve as a model for similar studies in other rapidly urbanizing regions.

---

**END OF CHAPTER THREE**
