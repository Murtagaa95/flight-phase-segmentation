# A Hybrid Expert System and Deep Learning Approach for Flight Phase Segmentation

This repository contains the official source code and implementation for the research paper titled "A Hybrid Expert System and Deep Learning Approach for Flight Phase Segmentation from FDR Data".

## Project Overview

The primary goal of this project is to develop and validate a robust system for automatically segmenting raw Flight Data Recorder (FDR) time-series data into distinct operational flight phases (e.g., On Stand, Taxi, Climb, Cruise, Descent).

The project follows a two-stage hybrid methodology:
1.  **Expert Rule-Based System:** A sophisticated rule-based model (v9) was developed through an iterative process to label the raw flight data, creating a high-quality "Ground Truth" dataset.
2.  **Deep Learning Model:** A Long Short-Term Memory (LSTM) neural network was then trained on this labeled data. The results show that the LSTM model not only learned to accurately replicate the expert's classification but also demonstrated superior performance in handling noisy sensor data, producing a smoother and more stable segmentation.

## Data Source

The dataset used in this study is publicly available from the NASA Prognostics Center of Excellence. It can be downloaded directly from the following link:
* **Source:** [NASA Dashlink - Flight Data](https://c3.ndc.nasa.gov/dashlink/resources/664/)

**Setup Instructions:** To run the code, please download the required `.mat` flight data files and place them in a folder named `Input_MAT` within the project's root directory.

## Code Files

This repository includes the following key Python scripts:

* `requirements.txt`: A list of all the necessary Python libraries to run the project.
* `1_rule_based_ground_truth.py`: This script applies the final expert rule-based model (v9) to the raw `.mat` files to generate the labeled "Ground Truth" dataset.
* `2_lstm_model_training.py`: This script uses the labeled data to train, evaluate, and save the final LSTM model. It also generates the visual comparison plots.

## How to Run the Project

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/Murtagaa95/flight-phase-segmentation.git
    cd flight-phase-segmentation
    ```
2.  **Set up the environment:**
    ```bash
    pip install -r requirements.txt
    ```
3.  **Download the data:** Create a folder named `Input_MAT` and place the downloaded `.mat` files inside it.
4.  **Generate Ground Truth (Optional):** Run the `1_rule_based_ground_truth.py` script if you wish to regenerate the expert labels.
5.  **Train the LSTM Model:** Run the `2_lstm_model_training.py` script to train the model and generate the results.
