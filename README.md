### MST-Based Medical Image Analysis
Overview:
This project implements a graph-theoretical approach to medical image processing, specifically focusing on MRI (Magnetic Resonance Imaging) scans. By treating an image as a graph and finding a Minimum Spanning Tree (MST), the algorithm partitions the image into meaningful anatomical regions while simultaneously reducing noise.

# Key Features:

1.Efficient Graph Representation: Models images as 4-neighbor graphs where edge weights represent intensity gradients.

2.Kruskal’s Based Segmentation: Uses an MST-based merging criterion to group pixels into meaningful anatomical regions.

3.Rainbow Label Visualization: Uses the nipy_spectral colormap to generate high-contrast segment maps, as required by the project specifications.

4.Segment-Dependent Denoising: Calculates the mean intensity of each MST component to smooth the image while preserving boundaries.

5.Statistical Analysis: Includes log-scale histograms to visualize the distribution of segment sizes.

# Structure:
The code is organized into the following mandatory sections:

i.UNION-FIND DATA STRUCTURE: Handles component merging with path compression.

ii.GRAPH CONSTRUCTION & SEGMENTATION: Builds the edge list and executes the MST merging logic.

iii.DENOISING & LABEL EXTRACTION: Computes segment means and prepares the colorful boundary map.

iv.METRICS CALCULATION: Computes MSE and PSNR for quality assessment.

v.VISUALIZATION: Generates the 4-panel results (Original, Boundaries, Denoised, Histogram).

vi.MAIN EXECUTION PIPELINE: Orchestrates the processing of the manual list ['mri.jpg', 'mri2.jpg', 'mri3.jpg'].

# Usage Instructions:

Setup: Upload your MRI images (mri.jpg, mri2.jpg, mri3.jpg) to the Google Colab file sidebar.

Parameter Tuning: Adjust the k_val variable (recommended: 500–1000) to achieve the large anatomical segments seen in the target screenshot.

Execution: Run the script. The output will display the grayscale denoised results and the corresponding colored segment maps.

# Configuration:


The MST-based medical image processing pipeline begins with Graph Construction, where the MRI is modeled as a grid graph with pixels as nodes and edges representing the intensity gradients between 4-neighboring pixels. During the Segmentation phase, the algorithm employs a Union-Find data structure with path compression to efficiently merge components based on a dynamic threshold $k$; this parameter is central to the Configuration, as a higher $k$ value forces the merger of larger anatomical regions to produce the colorful, rainbow-like boundary map seen in your reference. Following segmentation, Denoising & Label Extraction occurs by calculating the mean intensity for each identified component, ensuring that the Denoised Image preserves sharp anatomical borders while eliminating local noise. Finally, the Metrics Calculation provides quantitative validation through MSE and PSNR, while the Visualization and Segment Distribution Histogram offer a qualitative and statistical overview of the segmentation granularity, all orchestrated within a streamlined Main Execution Pipeline.
