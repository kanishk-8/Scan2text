# Scan2text

Scan2text is a repository that contains multiple models designed to handle the same type of request—extracting text from images and providing the output. The repository leverages various OCR and deep learning models to process images (and PDFs, if needed) and convert the content into editable text. This project was inspired by the Amazon ML Challenge, which provided a dataset for testing and benchmarking text extraction techniques.

## Table of Contents

- Features

- Dataset Structure

- Prerequisites

- Installation

- Usage

- Contributing

- License

- Acknowledgements

- Contact

## Features

- Multi-Model OCR: Supports multiple models that extract text from images.

- Flexible Input Handling: Processes various image formats (JPEG, PNG, etc.) and can also handle PDFs if required.

- Modular Architecture: Easily swap out or update OCR models without affecting the overall system.

- Batch Processing: Supports single-file processing as well as batch processing of directories.

- Dataset Compatibility: Designed to work seamlessly with the Amazon ML Challenge dataset for testing and evaluation.

## Dataset Structure

For the Amazon ML Challenge dataset (available on Kaggle), a clear and organized structure is essential. Below is a suggested dataset directory layout:

```
Amazon_ML_Challenge_Dataset/
├── data/
│   ├── raw/
│   │   ├── train/
│   │   │   ├── image_001.jpg
│   │   │   ├── image_002.jpg
│   │   │   └── ... 
│   │   └── test/
│   │       ├── image_101.jpg
│   │       ├── image_102.jpg
│   │       └── ... 
│   ├── annotations/
│   │   ├── train_labels.csv    # Contains image IDs and corresponding ground truth text
│   │   └── test_labels.csv     # (If available) Ground truth for the test set
│   └── processed/
│       ├── train/              # Preprocessed images (e.g., resized, grayscale)
│       │   ├── image_001.png
│       │   └── ... 
│       └── test/
│           ├── image_101.png
│           └── ... 
├── models/                     # Saved model weights and configurations for each model
│   ├── model_A/
│   ├── model_B/
│   └── ...
├── notebooks/                  # Jupyter notebooks for exploratory data analysis and experiments
│   ├── exploratory_analysis.ipynb
│   ├── model_training.ipynb
│   └── evaluation.ipynb
├── scripts/                    # Utility scripts for preprocessing, training, and prediction
│   ├── preprocess.py
│   ├── train_model.py
│   └── predict.py
├── requirements.txt            # Python dependencies
├── README.md                   # This file
└── LICENSE
```
<div><img src="https://machinelearningmastery.com/wp-content/uploads/2021/08/attention_research_1.png" alt="Scan2text Logo" height="400" >
<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSrBZYuRm6i3nDz07SqtHaVLZdNgVjJrnJDLVE1gn0sFL7lu2N2BtSNG4kjldSSBlwrwvA&usqp=CAU" alt="Scan2text Logo" height="400" >
<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcStdVyIlGWgJVjWtBMNOCfK7GA2CAWPuVqhDFUiTrw9y7I0Qzx63t4fDF-irj02uiGYVnM&usqp=CAU" alt="Scan2text Logo" height="400" >
  <img src="https://miro.medium.com/v2/resize:fit:1400/1*IHT7lqvEiuu1BzVIXXD0hA.png" alt="Scan2text Logo" height="400" >
<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQgmMpEY8CqGlMRT2OHIeyNW6wHWtlm1L02Cpe5esFGbuRFn6BXE5KWbA7J26pNXAT1sA&usqp=CAU" alt="Scan2text Logo" height="400" >
</div>

## Explanation of the Structure


- data/raw:Contains the original images from the challenge. Images are separated into training and testing folders.


- data/annotations:CSV files containing the ground truth text (and possibly bounding box coordinates, if available) for each image. This helps in both training and evaluation.


- data/processed:Contains the preprocessed versions of images (e.g., resized, normalized, or converted to grayscale) ready for model input.


- models:Each subdirectory holds a different model’s configuration, weights, and any associated metadata. This modular approach lets you compare multiple OCR solutions.


- notebooks:Jupyter notebooks that document exploratory data analysis, model training, and evaluation procedures. They serve as both documentation and a way to reproduce experiments.


- scripts:Contains standalone scripts for data preprocessing, model training, and prediction. These scripts can be invoked from the command line or integrated into a CI/CD pipeline for automated workflows.

## Prerequisites


- Python 3.6+


- Tesseract OCR (if using Tesseract-based models):


- Installation details: Tesseract GitHub


- Required Python Libraries:


- pytesseract, Pillow, pdf2image, etc. (see requirements.txt)

## Installation


- Clone the Repository:


```
git clone https://github.com/kanishk-8/Scan2text.git
cd Scan2text
```

- Install Python Dependencies:

```
pip install -r requirements.txt
Install Tesseract OCR (if needed):
```

- Ubuntu:

```
sudo apt-get update
sudo apt-get install tesseract-ocr
```

- macOS (via Homebrew):

```
brew install tesseract
```

- Windows: Download and install from Tesseract at UB Mannheim.


## Usage


- To extract text from an image:

```
python scan2text.py --input path/to/image.jpg --output output.txt
```

- For batch processing or using PDFs, refer to the help menu:

```
python scan2text.py --help
```

## Contributing


- Contributions are welcome! To contribute:


- Fork the repository.


- Create a new branch: git checkout -b feature/your-feature.


- Commit your changes: git commit -am "Describe your feature or fix".


- Push your branch: git push origin feature/your-feature.


- Open a pull request.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Acknowledgements


- Tesseract OCR


- pytesseract


- Pillow


- Thanks to the contributors of the Amazon ML Challenge dataset on Kaggle.

## Contact

For questions or suggestions, please open an issue on GitHub or contact the maintainer at your-email@example.com.

Feel free to adjust the sections to better fit the specifics of your implementation and the dataset details.
