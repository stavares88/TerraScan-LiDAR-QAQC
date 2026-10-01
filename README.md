# South Platte LiDAR QA/QC – TerraScan

## Project Overview

This project demonstrates a LiDAR point-cloud classification and quality assurance/quality control (QA/QC) workflow using TerraScan and Spatix.

Approximately 1.8 million LiDAR points from the South Platte River area were evaluated using automated classification tools, class statistics, class-based visualization, and visual inspection.

The goal was not simply to run automated classification, but to evaluate the resulting classes and identify potential classification issues that would require additional review.

## Tools & Technologies

- TerraScan
- Spatix
- LiDAR / Point Cloud Data
- LAZ
- ASPRS-style point classifications
- Visual QA/QC
- Classification statistics

## Dataset

The project uses publicly available USGS LiDAR data associated with the South Platte River area.

Total points analyzed:

**1,802,573**

The original source data was preserved separately from the TerraScan working and final project files.

## Workflow

### 1. Initial Point Cloud Review

The LiDAR dataset was loaded into TerraScan/Spatix and inspected before additional classification.

Initial class statistics were recorded to establish a baseline for comparison.

### 2. Ground Classification

Ground points were evaluated and classified into:

**Class 2 – Ground**

The resulting ground surface was visually inspected for spatial continuity and obvious classification problems.

### 3. Height-From-Ground Classification

Height-from-ground processing was used to separate vegetation into height-based classes.

Classes evaluated included:

- Class 3 – Low Vegetation
- Class 4 – Medium Vegetation
- Class 5 – High Vegetation

This allowed vegetation points to be evaluated relative to the classified ground surface.

### 4. Class-Based Visualization

Individual point classes were isolated using TerraScan's display controls.

Viewing classes independently made it possible to examine their spatial distributions without interference from the rest of the point cloud.

Ground and vegetation classes were also displayed together to visually compare terrain and above-ground features.

### 5. Statistical QA/QC

TerraScan class statistics were used throughout the workflow to compare point populations and elevation ranges.

Final classification statistics included:

| Class | Description | Point Count |
|---|---|---:|
| 1 | Default | 287,725 |
| 2 | Ground | 505,864 |
| 3 | Low Vegetation | 22,668 |
| 4 | Medium Vegetation | 31,095 |
| 5 | High Vegetation | 294,444 |
| 7 | Low Point | 24,102 |
| 17 | Vegetation | 46,780 |
| 18 | Pole | 589,895 |

## QA/QC Finding

A significant classification anomaly was identified during the QA/QC process.

**Class 18 – Pole contained 589,895 points**, representing approximately 32.7% of the complete point cloud.

When Class 18 was isolated and visually inspected, its spatial distribution extended across broad portions of the scene and reproduced terrain, roadway, and neighborhood patterns inconsistent with an expected pole-only distribution.

Rather than accepting the automated classification result, the class was flagged as a **suspected misclassification requiring further investigation or reclassification**.

This demonstrates an important principle of LiDAR QA/QC:

> Automated classification results should be validated using both statistical analysis and visual inspection before being accepted as final.

## Project Results

The project demonstrated the ability to:

- Load and inspect a large LiDAR point cloud
- Preserve original data while working from separate processing copies
- Perform and evaluate ground classification
- Perform height-from-ground vegetation classification
- Isolate individual LiDAR classes
- Analyze point counts and elevation statistics
- Perform visual classification QA/QC
- Identify suspicious automated classification behavior
- Document QA findings without assuming automated results are correct
- Export a final LAZ project output

## Screenshots

The `Screenshots` directory contains documentation from multiple stages of the workflow, including:

- Initial classification statistics
- Ground classification results
- Low, medium, and high vegetation classification statistics
- Ground and vegetation visualization
- Ground-only QA
- High-vegetation QA
- Final classification statistics
- Class 18 anomaly investigation

## Repository Structure

TerraScan-LiDAR-QAQC/
- Data/ – source and working LiDAR data
- Documentation/ – supporting project documentation
- Outputs/ – processed project outputs
- Screenshots/ – workflow and QA/QC evidence
- South_Platte_LiDAR_Project.spx – Spatix project
- README.md – project documentation

## Skills Demonstrated

**LiDAR • TerraScan • Spatix • Point Cloud Processing • Ground Classification • Vegetation Classification • LAZ • QA/QC • Classification Validation • Geospatial Analysis • Remote Sensing**