# Mitochondrianalyzermacro

This ImageJ macro script is designed for analyzing mitochondrial images using the MitoAnalyzer plugin. It automates the process of opening multi-channel images, processing individual channels, and performing z-stack analysis. 

## Prerequisites

- **ImageJ**: Ensure you have the ImageJ software installed (Fiji Downloads (imagej.net)).
- **Bio-Formats Plugin**: The script uses Bio-Formats to open the image files. Install the Bio-Formats plugin if you haven’t already.
- **MitoAnalyzer Plugin**: Ensure that the MitoAnalyzer plugin is installed and properly configured. The process is as mentioned: AhsenChaudhry/Mitochondria-Analyzer: Mitochondria Analyzer (github.com).

 Script Details

### File Path and Naming Conventions

- **`path_name`**: Directory where the image files are located.
- **`excelFile`**: The name of the image file (including extension).
- **`DV`**: The file extension of the image file; it will differ based on the extension a particular microscope software uses.
- **`ImgFile`**: Derived filename without the extension.
- **Channel Naming**: The script creates combined names for different channels based on the original filename and predefined prefixes.

### Parameters
In order to get information from the best stacks, an additional parameter is added in this script which ensures that measurements from the most focusses stacks are only recorded. This command ensures that start and end stacks can be manually added by the user.
- **`z_stack_start`**: Starting slice number for z-stack analysis.
- **`z_stack_end`**: Ending slice number for z-stack analysis.

### Script Workflow

1. **Open the Image**: Uses Bio-Formats to open the specified image file.
2. **Z-Stack Subset**: Selects a range of slices for analysis based on the z-stack parameters.
3. **Split Channels**: Separates the channels into individual images.
4. **Image Processing**: Each channel is processed individually:
   - Convert to 8-bit grayscale
   - Subtract background
5. **Adjust Brightness/Contrast**: Prompts the user to adjust the brightness and contrast of the images.
6. **Manual ROI Selection**: Prompts the user to manually select a region of interest (ROI) for analysis.
7. **Image Thresholding**: Applies thresholding to the green channel to enhance the features of interest.
8. **Close All Windows**: Closes all windows and managers after processing.

### Usage Instructions

1. **Setup**: Modify the `path_name` and `excelFile` variables to match your file locations and names.
2. **Run the Script**:
   - Open ImageJ.
   - Go to `Plugins > Macros > Run...` and select this script.
   - Follow the prompts for brightness/contrast adjustment and ROI selection.

### Troubleshooting

- **No Image Displayed**: Ensure that the Bio-Formats plugin is installed and correctly configured.
- **ROI Selection Issues**: Verify that the correct tool is selected when prompted to draw the ROI.

### Example

For an image file named `1_03_R3D_D3D.dv` located in `E:/xyz_mitoGFP_gfh/123/`, the script will process the channels named `C1-1_03_R3D_D3D.dv`, `C2-1_03_R3D_D3D.dv`, and `C3-1_03_R3D_D3D.dv`.



## Contact

For issues or questions, please contact Autophagy lab JNCASR  at autophagygithubjnc@gmail.com


---

Feel free to customize any section to better fit your needs!
