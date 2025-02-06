# NMR Data Processing Script

## Overview
This Python script processes Nuclear Magnetic Resonance (NMR) data from a text file, performs Fourier Transform (FT), applies baseline correction, phase correction, apodization, and broadening, and visualizes the resulting spectrum. It also detects and highlights spectral peaks.

## Requirements
Ensure you have the following Python libraries installed:
- `numpy`
- `matplotlib`
- `scipy`
- `pandas`
- `nmrglue`

You can install them using:
```sh
pip install numpy matplotlib scipy pandas nmrglue
```

## Input Data
The script loads data from a text file named `13DW1.5NS2093.txt`, which contains NMR signal values.

## Processing Steps
### 1. Load and Preprocess Data
- Reads the NMR signal data from a text file.
- Extracts real and imaginary components.
- Constructs a complex array `G` for further processing.

### 2. Create a Time Array
- Defines a dwell time of `3e-6 s`.
- Generates a time axis `T`.
- Performs baseline correction by subtracting the average of the last 20% of the signal.

### 3. Fourier Transform
- Performs a complex discrete Fourier transform (CDFT) on the processed signal.
- Reorders the frequency data for better visualization.

### 4. Spectrum Processing
- Applies phase correction.
- Optionally applies apodization (Gaussian or Blackman window functions).
- Uses a broadening function to smooth the spectrum.

### 5. Peak Detection
- Detects peaks using `scipy.signal.find_peaks`.
- Filters peaks based on intensity threshold.

### 6. Visualization
- Plots the original and broadened spectra.
- Marks detected peaks.
- Saves figures if needed.

## Output Files
- **`parameters.txt`**: Contains metadata about the processed dataset.
- **`null.txt`**: Contains the processed frequency and intensity values.
- **Plots**: Displayed in the script but can be saved as needed.

## Example Usage
Simply run the script in a Python environment:
```sh
python script.py
```

## Parameters Used
- **Dwell Time**: `3e-6 s`
- **Size of FT**: `20480`
- **Start Time**: `0.0 s`
- **Phase Correction**: `0°`
- **Broadening Factor**: `100`
- **Apodization Window**: `None`

## Author
This script was developed to analyze NMR data and extract meaningful spectral features efficiently. Feel free to modify and optimize it for your specific dataset.

