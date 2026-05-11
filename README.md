# Sleep Stage Classification using EEG Signals

Deep Learning project for automatic sleep stage classification using EEG signals from the Sleep-EDF dataset.

## Project Overview

This project processes raw EEG recordings and hypnogram annotations from EDF files to classify sleep stages automatically. The pipeline extracts 30-second EEG epochs and maps sleep stages into standard sleep classes.

The project uses:

- Python
- MNE
- NumPy
- Deep Learning techniques for EEG analysis

## Dataset

Dataset used: Sleep-EDF Database

Files include:

- PSG (Polysomnography) EEG recordings
- Hypnogram annotation files

Example files:

```text
SC4002E0-PSG.edf
SC4002EC-Hypnogram.edf
SC4011E0-PSG.edf
SC4011EH-Hypnogram.edf
```

## Sleep Stage Mapping

| Sleep Stage | Label |
|---|---|
| Wake | 0 |
| N1 | 1 |
| N2 | 2 |
| N3 | 3 |
| REM | 4 |

Stages 3 and 4 are merged into N3 according to standard preprocessing practices.

## Features

- EDF file loading using MNE
- EEG channel extraction
- Hypnogram annotation parsing
- 30-second epoch segmentation
- Automatic label generation
- Dataset concatenation for multiple subjects
- Ready for Deep Learning model training

## EEG Channel Used

```python
EEG Fpz-Cz
```

## Preprocessing Pipeline

1. Load PSG EDF file
2. Load hypnogram annotations
3. Extract EEG signal
4. Split into 30-second epochs
5. Assign sleep stage labels
6. Remove unscored/movement epochs
7. Build training dataset

## Technologies Used

- Python
- MNE
- NumPy
- Google Colab / VS Code
- Deep Learning

## Project Structure

```text
sleep_edf_data/
│
├── SC4002E0-PSG.edf
├── SC4002EC-Hypnogram.edf
├── SC4011E0-PSG.edf
└── SC4011EH-Hypnogram.edf
```

## Installation

```bash
pip install mne numpy
```

## Run the Project

```bash
python main.py
```

or run the notebook in Google Colab / VS Code.

## Example Output

```text
SC4002E0-PSG.edf: 841 epochs
SC4011E0-PSG.edf: 915 epochs

Total epochs : 1756
Epoch length : 3000 samples (= 30s)

Class distribution:
Wake : 300
N1   : 150
N2   : 800
N3   : 250
REM  : 256
```

## Future Improvements

- CNN/LSTM sleep stage classification
- Spectrogram generation
- Multi-channel EEG support
- Attention-based architectures
- Better class balancing
- Real-time sleep monitoring

## Author

Abdelhady Mohamed
```
