# Retinal Disease Classification using Deep Learning
This project implements a Deep Learning system (utilizing ResNet50 and EfficientNetB3) for the multi-label classification of 8 common retinal pathologies.

*Note: This source code is intended for research purposes and a graduation thesis. It reflects a self-study process, experimenting with and refining models from basic to advanced levels.*

**Quick Start Guide**

To ensure the code runs smoothly and performance is optimized, please follow the environment setup steps below strictly.

* **Step 1: Environment Setup (Google Colab)**

1. Download the .ipynb file from this repository to your local 



machine.

2. Open Google Colab and upload the downloaded file.

3. **Important: Enable Hardware Acceleration (GPU).**

    * Go to menu: Runtime > Change runtime type.

    * Select T4 GPU (or a higher tier GPU if available).

* **Step 2: Data Preparation (Google Drive)**
The system is designed to read data from Google Drive for persistent storage.

1. Go to your Google Drive.

2. Create a root folder named exactly: datasetFinal.

3. Upload your dataset into this folder following this structure:





```
My Drive/
└── datasetFinal/
    ├── images/           # Folder containing all image files
    └── label_images.csv  # CSV file with labels
```


* **Step 3: Running the Notebook**
Execute the code cells sequentially from top to bottom:

1. **Mount Drive & Setup Local Storage:**

Run the cell to connect to Google Drive.

Note: Execute the cell that copies data from Drive to the local virtual machine storage (/content/local_images). This step is crucial as it significantly accelerates training speed compared to reading directly from Drive.

2. **Exploratory Data Analysis (EDA):**

Run the data exploration cells to inspect label distribution, check for corrupted images, and visualize statistics.

3. **Model Training:**

Locate the section titled "Specify model ResNet50".

This block consolidates the optimized training pipeline: Oversampling -> Focal Loss -> Warm-up -> Aggressive Fine-tuning.

**Disclaimer & Troubleshooting**
This project is the result of independent research and exploration; therefore:

* Experimental Nature: Several code cells appearing before the main model section may be fragmented or experimental. These represent trial-and-error phases and hypothesis testing conducted before reaching the final optimized solution.

* Code Structure: The code is structured for research demonstration rather than production-ready deployment.

* Troubleshooting: If you encounter errors (e.g., FileNotFound, Path Error, or library conflicts), please verify:

  * Is the folder on Drive named exactly datasetFinal?

  * Are the library versions in the current Colab environment compatible?

  * System Differences: Errors may occur if you attempt to run this locally (Windows/Linux) without adjusting file paths, as the code is tailored for the Google Colab environment.

**Key Optimization Techniques**
1. Data Handling: Random Oversampling to address class imbalance.

2. Loss Function: Implementation of Focal Loss to focus learning on hard-to-classify samples.

3. Training Strategy: Transfer Learning utilizing a Warm-up phase followed by Aggressive Fine-tuning.

4. Inference: "Golden Threshold" strategy to maximize Recall (Sensitivity) for screening purposes.


Author: [Group 22 ]
