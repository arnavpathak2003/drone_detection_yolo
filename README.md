---

# Drone Detection with YOLO  

This repository contains all the resources required to train and evaluate a YOLO-based model for drone detection. Follow the steps below to set up the environment, process the data, and train the model.

---

## **Prerequisites**  

Before proceeding, make sure you have the following tools installed on your system:  

- **Miniconda**: You can install Miniconda by following the instructions at [Miniconda Installation Guide](https://docs.anaconda.com/miniconda/install/).  
- **Git**: Ensure Git is installed to clone the repository. You can install Git by following the instructions [here](https://git-scm.com/downloads/).

---

## **Getting Started**  

1. **Clone the Repository**  
   Use the following command to clone this repository:  

   ```bash
   git clone https://github.com/arnavpathak2003/drone_detection_yolo.git
   ```

2. **Navigate to the Repository**  
   Move into the project directory:  

   ```bash
   cd drone_detection_yolo
   ```

3. **Create the Anaconda Environment**  
   Create a new environment using the provided `environment.yml` file:  

   ```bash
   conda env create -f environment.yml
   ```

4. **Activate the Environment**  
   Activate the newly created environment:  

   ```bash
   conda activate yolo
   ```

---

## **Data Processing**  

### Step 1: Run the Data Processing Script  

Open the `data_process_script.ipynb` notebook and follow the instructions:  

- If you want to download the dataset using `curl`, **uncomment** the relevant line in the notebook.  
- Alternatively, a link to the dataset on Kaggle is provided in the notebook.  

This script will:  
- Download the dataset.  
- Split it into training and validation datasets (`train` and `val`).  
- Generate the `dataset.yaml` file required by YOLO for training.
- Create the directory structure required by YOLO.
  
---

## **Folder Structure**

After running the `data_process_script.ipynb`, the folder structure will look like this:

```
drone_detection_yolo/
│
├── datasets/
│   ├── train/
│   │   ├── images/
│   │   ├── labels/
│   │   
│   │
│   ├── val/
│   │   ├── images/
│   │   ├── labels/
│   
│
├── dataset.yaml
├── data_process_script.ipynb
├── yolo_train.ipynb
├── environment.yml
├── README.md
```

---

## **Model Training**  

### Step 2: Train the Model  

Run the `yolo_train.ipynb` notebook to train the YOLO model.  

- The notebook contains all the steps required to train the model using the processed data.  

### Step 3: Test the Model  

Once training is complete, you can evaluate the model's performance by running the last cell of the `yolo_train.ipynb` notebook **repeatedly**.  

- The last cell randomly selects an image from the validation dataset.  
- It displays the predicted bounding boxes and ground truth side by side, helping you visually assess the model's performance.

---

