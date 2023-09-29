# GPS-Data-Extraction-from-Images

This repository contains a Python script to process images taken from the GPS Status application. The script processes these images, extracts relevant GPS and device data, and then presents this data in a structured tabular format.

Google Colab: https://colab.research.google.com/drive/1qFNz2VfujTHiH01h0GlIjNSker2gybeo?usp=sharing

## Steps of Execution:
### 1. Setup:
Before running the script, you need to ensure you have the necessary libraries and tools installed. The script relies on the pytesseract library for optical character recognition and the PIL library for image processing.

```
pip install pytesseract
sudo apt update
sudo apt install -y tesseract-ocr libtesseract-dev
```

### 2. Image Processing:
For each image provided:

- The image is loaded and cropped to focus on the area containing the relevant data.
- The cropped image is saved in an output directory with the prefix cropped_ added to the original file name.

### 3. Data Extraction:
Using Optical Character Recognition (OCR) provided by pytesseract:

Extracted texts from each image are saved as .txt files in the output directory.
The script searches for the following parameters:
- Date and Time (extracted from the image filename)
- Breitengrad (gps)
- Langengrad (gps)
- Battery Temperature and Voltage
- Battery Percentage

### 4. Tabular Presentation:
- All extracted information is aggregated and presented in a structured tabular format using pandas.
- This table is also exported as a .csv file named results.csv in the output directory for future reference.

## Usage:
- Place your images in the specified directory (default is /content/ for Google Colab).
- Run the script.
- Check the output directory for cropped images, extracted texts, and the final results.csv.

## Note:
This script is optimized for a specific format and layout of the images. If there are any changes in the layout or new updates in the GPS Status application that affect the image format, adjustments to the script may be required.

