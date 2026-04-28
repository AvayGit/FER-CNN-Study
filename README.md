Deep and Lightweight CNN for Facial Expression Recognition

This repository contains the official, reproducible codebase for the study: "Deep and Lightweight CNN for Facial Expression Recognition based on Multi Block Regularization and Feature Learning." This codebase implements both the Deep Regularized CNN ($\approx$ 3.2M parameters) and the Lightweight CNN ($\approx$ 0.8M parameters) and evaluates them across three distinct data regimes: FER2013, CK+, and JAFFE.

To ensure strict reproducibility, all random seeds (Python, NumPy, TensorFlow) are explicitly anchored, and relative paths are used for all dataset loading and model checkpointing.

🛠 Dependencies

The models are built and trained using Python 3 and TensorFlow/Keras. To replicate the environment, ensure the following core libraries are installed:

 TensorFlow: `tensorflow` (>= 2.x) - Core deep learning framework
 OpenCV: `opencv-python` - Image processing and loading
 Scikit-learn: `scikit-learn` - Dataset splitting, shuffling, and evaluation metrics (Confusion Matrix, classification report)
 Pandas: `pandas` - CSV data manipulation (specifically for FER2013)
 Matplotlib: `matplotlib` - Plotting training curves and confusion matrices
 NumPy: `numpy` - Array operations and mathematical computations

You can install the required dependencies using pip:
`pip install tensorflow opencv-python scikit-learn pandas matplotlib numpy.`

📂 Dataset Acquisition and Setup

To evaluate the models, you must download the three standard benchmark datasets. Due to licensing, the datasets are not hosted in this repository. 

Download Links:
1.  FER2013: [Download via Kaggle](https://www.kaggle.com/c/challenges-in-representation-learning-facial-expression-recognition-challenge/data)
2.  CK+ (Extended Cohn-Kanade): [Download via Kaggle](https://www.kaggle.com/datasets/shawon10/ckplus) (Or request official access from the University of Pittsburgh)
3.  JAFFE (Japanese Female Facial Expression): [Download via Zenodo](https://zenodo.org/record/3451524) (Or via the official ATR dataset portal)

Directory Structure:
For the relative paths in the Jupyter Notebooks to function correctly, you must extract the downloaded datasets into a root folder named `dataset` located in the exact same directory as your `.ipynb` files. 

Ensure the structure strictly follows this format:

```text
FER-CNN-Study/
│
├── Model_1.ipynb                  Deep Regularized CNN training & evaluation
├── model_2.ipynb                  Lightweight CNN training & evaluation
├── README.md                      This documentation
│
└── dataset/                       Extracted datasets go here
    ├── FER2013/
    │   └── fer2013.csv            Raw CSV file containing pixels and labels
    ├── CK+/
    │   ├── anger/
    │   ├── disgust/
    │   ├── fear/
    │   ├── happy/
    │   ├── sadness/
    │   └── surprise/
    └── JAFFE/
        ├── KA.AN1.39.tiff         Raw image files 
        ├── KL.HA1.158.tiff
        └── ...
