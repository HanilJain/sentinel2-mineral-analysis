# Copper-associated Mineral Mapping in

# Khetri Region using Sentinel-2A Data

## Introduction

Copper is one of the most economically significant metals, widely used in industrial applications
and infrastructure development. The identification of copper-bearing minerals and associated
alteration zones is crucial for exploration and sustainable resource management. The Khetri
region in Rajasthan, India, is a well-known copper belt that hosts a number of active and historic
copper mines, including the Kolihan mine. This study utilizes Sentinel-2A satellite imagery to
conduct mineral abundance mapping and spectral analysis for copper exploration in the region.
Sentinel-2A’s multispectral capabilities, combined with efficient image processing tools such as
QGIS, offer a cost-effective and accurate solution for remote mineral exploration.
The approach involves selective band utilization, spectral resampling of medium-resolution
bands to high resolution, and computation of band ratios and spectral indices to highlight
mineral signatures indicative of hydrothermal alteration. Specific indices were derived to identify
clays, carbonates, and iron oxides, all of which serve as pathfinders for copper mineralization.
The integration of these indices into a false color composite enhances the visualization and
interpretation of mineral distribution across the study area.



## Study Area


The study was conducted in the Khetri region, located in the Jhunjhunu district of Rajasthan,
India, renowned for its substantial copper deposits. This area forms a critical part of India's
copper belt, characterized by significant mineralization predominantly within the Proterozoic
Delhi Supergroup. The primary site chosen for mineral identification and mapping is the Kolihan
mine, an active underground copper mining operation notable for its substantial production and
geological complexity. Additionally, the area around the Copper Dam, situated adjacent to the
Kolihan mine, was included to investigate mineral distribution in water-influenced terrains.
The Kolihan mine is particularly known for its mineralization of chalcopyrite, pyrite, bornite, and
associated alteration minerals such as chlorite, epidote, sericite, kaolinite, illite, and carbonate

![image](https://github.com/user-attachments/assets/9390537a-03fd-4cbd-aba9-b3076b3e3373)
![Screenshot 2025-04-08 064908](https://github.com/user-attachments/assets/b2803a1d-a87e-4745-a995-bcccdbde93ff)

minerals including calcite and dolomite. Surrounding areas host other significant mining sites,
contributing to the region's reputation as a major copper-mining hub. These combined sites
present a diversified geological environment, ideal for remote sensing-based mineral
identification and abundance mapping utilizing Sentinel-2A satellite data.

## Research Methodology
![Screenshot 2025-04-08 050503](https://github.com/user-attachments/assets/563ca914-74dc-4c12-8149-9fd468656220)


## Data Used

The dataset utilized in this study was acquired from the open-source Bhuvan Bhoonidhi portal.
Specifically, we employed the Sentinel-2A Multispectral Instrument (MSI) dataset, which
comprises 13 spectral bands encompassing the visible spectrum, near-infrared (NIR), and
shortwave infrared (SWIR) regions. Sentinel-2A MSI data are available in varying spatial
resolutions of 10 meters, 20 meters, and 60 meters, facilitating detailed analyses across
different spectral characteristics.
We selected the Sentinel-2A MSI Level-2A data due to its comprehensive preprocessing
capabilities, including atmospheric corrections such as haze removal, water vapor
compensation, and effective cloud masking. This preprocessing ensures reduced data
preparation requirements, making the dataset immediately suitable for accurate and efficient
mineral identification and mapping analyses.

## Band Selection

For this study, we excluded bands B1 and B9 as they primarily serve for coastal aerosol and
water vapor detection, respectively. Additionally, band B10 is not available at any spatial
resolution in the dataset. Consequently, the analysis was conducted using bands B2, B3, B4,
and B8 at 10-meter resolution and bands B5, B6, B7, B8a, B11, and B12 at 20-meter resolution.
The 60-meter resolution bands were omitted since their primary function pertains to atmospheric
corrections, which were already accounted for in the Level-2A preprocessing.
![image](https://github.com/user-attachments/assets/cce26375-002c-4976-9f72-c537b5e6cb56)
![image](https://github.com/user-attachments/assets/de3c07e3-703e-46d0-9deb-0d901611f79d)


## Spectral Resampling

Bands B5, B6, B7, B8a, B11, and B12, originally available at 20-meter resolution, were
resampled to 10-meter resolution to ensure uniformity across all selected bands for multispectral
analysis. The Lanczos resampling algorithm was employed for this purpose due to its superior
interpolation capabilities. Lanczos is a sinc function–based method that performs convolution
over a windowed kernel, allowing for smoother transitions and improved edge preservation
compared to traditional methods like nearest-neighbor, bilinear, or bicubic interpolation.
Lanczos effectively minimizes aliasing and ringing artifacts, thereby maintaining spectral
integrity and spatial precision—essential for accurate mineral mapping and classification.
Post-resampling, a visibly smoother profile was observed across all enhanced bands,


significantly improving image quality and consistency for subsequent processing and analysis
steps.
**B05 at 20m resolution B05 after applying Lanczos converting to 10m**

## Band Ratio and Spectral Indices Analysis

Based on insights from previous research and established spectral characteristics of alteration
minerals, various band ratios and spectral indices were computed using the Raster Calculator in
QGIS to enhance mineral discrimination.

**1. Clay mineral (general)**
    a. 𝐵 11 (𝑆𝑊𝐼𝑅 1 ) / 𝐵 12 ( 𝑆𝑊𝐼𝑅 2 )
    b. ( 𝐵 11 − 𝐵 12 ) / ( 𝐵 11 + 𝐵 12 ) Clay Index
**2. Kaolnite and Al Rich Clays**
    a. 𝐵 12 (𝑆𝑊𝐼𝑅 2 ) / 𝐵 8 (𝑁𝐼𝑅)
**3. Carbonates( Calcite, Dolomite , Siderite)**
    a. 𝐵 11 (𝑆𝑊𝐼𝑅 1 ) / 𝐵 4 (𝑟𝑒𝑑)
    b. ( 𝐵 11 −𝐵 4 ) / ( 𝐵 11 + 𝐵 4 ) Normalized Difference Clay Index
**4. Iron Oxide ( Hematite)**
    a. 𝐵 4 / 𝐵 2
    b. ( 𝐵 4 − 𝐵 2 ) / ( 𝐵 4 + 𝐵 2 ) Normalized Difference Iron Index

These indices helped differentiate zones enriched in clay, carbonate, and iron oxide minerals,
which are crucial in identifying hydrothermal alteration and copper mineralization.

![Screenshot 2025-04-08 052944](https://github.com/user-attachments/assets/3fbc0208-5605-4d58-80fd-ae38cfb303c8)![Screenshot 2025-04-08 052825](https://github.com/user-attachments/assets/b41242b5-2763-4ffd-918b-bd0ba27dcc38)

![Screenshot 2025-04-08 053126](https://github.com/user-attachments/assets/2fd6d8a8-c941-4b71-8b79-493f925dc35b)![Screenshot 2025-04-08 064908](https://github.com/user-attachments/assets/eb87730d-23d2-4186-9795-b6f4b697aa76)


![Screenshot 2025-04-08 070435](https://github.com/user-attachments/assets/33419557-1cb1-4cbc-96ad-5988d2dab648)
![Screenshot 2025-04-08 070514](https://github.com/user-attachments/assets/81857d51-e03b-4acb-a9a6-2904706950b4)
![Screenshot 2025-04-08 070909](https://github.com/user-attachments/assets/6ded4fd5-7861-4da5-b14c-ca8070410a19)

![Screenshot 2025-04-08 071241](https://github.com/user-attachments/assets/1b083599-3bf1-42db-9f26-29ad0808ed7d)
![Screenshot 2025-04-08 071330](https://github.com/user-attachments/assets/c0726d2b-65bd-4589-9ad7-4a67deac740f)
![Screenshot 2025-04-08 071717](https://github.com/user-attachments/assets/bc935ac6-2471-45af-8bc3-0dac95ad0cf0)


Visual inspection of the generated ratio layers revealed significant spatial variations
corresponding to the above indices. To facilitate integrated interpretation, the key indices were
merged into a single false color composite image using RGB band assignment: **Red for the
Normalized Difference Iron Index (NDII), Green for the Carbonate Index (CI), and Blue for
the Normalized Difference Clay Index (NDCI)**. This composite visualization enhances the
identification of lithological variations and alteration zones, providing a comprehensive
mineralogical perspective for copper exploration in the study area.




## Conclusion

This study demonstrates the effectiveness of Sentinel-2A multispectral data for mineral mapping
and copper exploration in the Khetri region of Rajasthan. By leveraging band ratio techniques
and spectral indices within the QGIS platform, we successfully identified key mineral
groups—clays, carbonates, and iron oxides—associated with hydrothermal alteration. The
application of Lanczos resampling further ensured spatial consistency and spectral fidelity
across all utilized bands.
The integration of various mineral indices into a composite visualization enabled clear
differentiation of alteration zones, offering valuable insights into potential copper-bearing areas.
This approach provides a replicable and cost-efficient methodology for remote mineral
exploration, particularly in metallogenic provinces like Khetri where traditional field-based
mapping is limited by scale and accessibility.

