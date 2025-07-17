# ImageJ Macro Collection - Plant Image Analysis

This repository contains ImageJ macros for plant image analysis.

**📖 日本語版: [README_JP.md](README_JP.md)**

## Overview

This repository contains the following two ImageJ macros:

1. **AreaCalculationExG.txt** - Macro for measuring green leaf area
2. **AreaCalculationUsingBOfLabForStem.txt** - Macro for measuring yellow stem area

## Required Software

- [ImageJ](https://imagej.nih.gov/ij/) or [Fiji](https://fiji.sc/)
- Image files (JPG, PNG, TIF, BMP, GIF formats supported)

## How to Use the Macros

### Preparation

#### 1. Install ImageJ
1. Download ImageJ from the [official website](https://imagej.nih.gov/ij/)
2. Run the downloaded file to install
3. Launch ImageJ

#### 2. Install the Macros
1. Launch ImageJ
2. Click **Plugins** → **Macros** → **Install**
3. Select the saved macro file (`AreaCalculationExG.txt` or `AreaCalculationUsingBOfLabForStem.txt`)
4. The macro will be installed

#### 3. Prepare Images
- Save images to be analyzed in `LeavesImages` (for leaves) or `StemsImages` (for stems) folders
- Ensure images contain a 10cm ruler or scale bar

### How to Use the Green Leaf Area Measurement Macro

#### 1. Launch the Macro
1. Click **Plugins** → **Macros**
2. Click the installed macro (`AreaCalculationExG`)
3. The macro will start

#### 2. Select Folder
1. When the macro starts, a folder selection dialog will appear
2. Select the `LeavesImages` folder saved on your PC and open it
3. Click **OK**

#### 3. Execute Image Processing
Repeat the following steps until all images in the folder are processed:

##### 3-1. Zoom In/Out Image
- Images in the folder will open
- Hold **Ctrl** and scroll the mouse wheel to zoom in/out the image
- Adjust until the 10cm ruler part is at a comfortable size

##### 3-2. Set Scale
1. Find the 10cm part of the ruler
2. Left-click and drag to draw a 10cm line, then release
3. Click **OK** to set the scale

##### 3-3. Select ROI (Region of Interest)
1. Draw a polygon that includes all leaves to be measured
2. Left-click to create multiple vertices
3. Left-click on the first vertex to close the polygon
4. Click **OK**

##### 3-4. Adjust Threshold
1. Threshold will be set automatically and the selected area will turn red
2. Move the **Threshold** slider left and right to set the threshold so that leaves are included as accurately as possible
3. Click **OK**

#### 4. Save Results
- Measurement results will be saved as `green_leaf_area_ExG.csv` file in the `LeavesImages` folder

### How to Use the Yellow Stem Area Measurement Macro

#### 1. Launch the Macro
1. Click **Plugins** → **Macros**
2. Click the installed macro (`AreaCalculationUsingBOfLabForStem`)
3. The macro will start

#### 2. Select Folder
1. When the macro starts, a folder selection dialog will appear
2. Select the `StemsImages` folder saved on your PC and open it
3. Click **OK**

#### 3. Execute Image Processing
Repeat the following steps until all images in the folder are processed:

##### 3-1. Zoom In/Out Image
- Images in the folder will open
- Hold **Ctrl** and scroll the mouse wheel to zoom in/out the image
- Adjust until the 10cm ruler part is at a comfortable size

##### 3-2. Set Scale
1. Find the 10cm part of the ruler
2. Left-click and drag to draw a 10cm line, then release
3. Click **OK** to set the scale

##### 3-3. Select ROI (Region of Interest)
1. Draw a polygon that includes all stems to be measured
2. Left-click to create multiple vertices
3. Left-click on the first vertex to close the polygon
4. Click **OK**

##### 3-4. Adjust Threshold
1. Threshold will be set automatically and the selected area will turn red
2. Move the **Threshold** slider left and right to set the threshold so that stems are included as accurately as possible
3. Click **OK**

#### 4. Save Results
- Measurement results will be saved as `yellow_area_lab_b.csv` file in the `StemsImages` folder

## Macro Features

### ExG Macro Features
- **ExG Index**: Uses the formula 2G - R - B
- **Green Detection**: Efficiently detects green parts of plants
- **Manual Adjustment**: Threshold can be adjusted manually

### Lab b-channel Macro Features
- **Lab Color Space**: Enables more accurate color separation
- **b-channel**: Color separation on yellow-blue axis
- **Stem Detection**: Specialized for detecting yellow stem parts

## Important Notes

1. **Scale Setting**: Always draw the 10cm reference line accurately
2. **ROI Selection**: Select only the area to be analyzed and exclude the background
3. **Threshold Adjustment**: Adjust manually if the automatic threshold is not appropriate
4. **File Format**: Only supported image formats can be processed

## Troubleshooting

### Common Problems and Solutions

1. **Macro doesn't run**
   - Check if the macro file is properly installed

2. **Results are incorrect**
   - Check if the scale setting is done correctly
   - Check if the ROI selection is appropriate
   - Recheck the threshold adjustment

3. **Files are not saved**
   - Check the write permission of the output folder
   - Check if the filename contains special characters

## License

This project is published under the MIT License.

## Contributing

Please use Issues or Pull Requests for bug reports and feature improvement suggestions.

## Update History

- v1.0.0: Initial version
  - Added ExG macro
  - Added Lab b-channel macro
