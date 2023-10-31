# CICIoT2023 Dataset - Machine Learning Project

## Overview
This repository contains a machine learning project that utilizes the CICIoT2023 dataset, which was published in the Sensors Journal from the Faculty of Computer Science, University of New Brunswick (UNB) in Canada in 2023. The project focuses on developing machine learning models for the analysis of IoT network traffic data.

The dataset consists of a network topology that mimics a real-world deployment of IoT products and services in a smart home environment. It includes 67 IoT devices directly involved in attacks, along with 83 Zigbee and Z-wave devices connected to five hubs. Additionally, seven Raspberry Pi devices connected to the network via a Cisco switch enabled researchers to perform various attacks to capture both benign and malicious attack traffic.

A Gigamon Network Tap is used to collect all IoT traffic and send it to two network monitors responsible for storing the traffic using Wireshark. Network taps are used to monitor and analyze network traffic non-intrusively and without affecting network performance.

## Dataset
The dataset is organized as follows:
- Data Generation: Different tools are used to execute attacks against IoT devices in the network.
- Data Extraction: Network traffic is captured in pcap format using Wireshark.
- Data Labeling: Each row in the dataset is labeled as belonging to a specific attack based on the attack executed.

### Data Features
The dataset includes features extracted using the DPKT package from fixed-size packet windows. These features represent network data flow and are used for machine learning analysis. The specific features extracted can be found in the dataset documentation.

## Usage
To use this dataset and implement machine learning models for network traffic analysis, follow these steps:

1. Clone this repository to your local machine.
2. Obtain the CICIoT2023 dataset from the [official source](http://205.174.165.80/IOTDataset/CIC_IOT_Dataset2023/).
3. Set up the necessary Python environment with the required libraries.
4. Explore the Jupyter notebook in the `ML-models` branch to see examples of data preprocessing, model training, and evaluation.

## Results

| Model         | 2 Classes (Binary) 60k samples | -                | -           | 8 Classes 3k samples | -                | -           | 34 Classes 10k samples | -                | -           |
|---------------|-------------------|---------|---------|-------------------|---------|---------|------------------------|---------|---------|
|               | Inference Time    | Accuracy |         | Inference Time    | Accuracy |         | Inference Time         | Accuracy |         |
| Naive Bayes   | 5.8e-4            | 0.86    |         | 20e-4            | 0.26    |         | -                      | -       |         |
| LR            | 11e-4             | 0.89    |         | 15e-4            | 0.25    |         | -                      | -       |         |
| SVM           | 545e-4            | 0.99    |         | 907e-4           | 0.24    |         | -                      | -       |         |
| XGBoost       | 80e-4             | 1.00    |         | 159e-4           | 0.88    |         | 480e-4                 | 0.87    |         |
| LightGBoost   | 55e-4             | 1.00    |         | 474e-4           | 0.89    |         | 2.281e-4               | 0.87    |         |

## Credits
- CICIoT2023 dataset: Faculty of Computer Science, University of New Brunswick (UNB) in Canada.
- Contributors: Nikitas Tsinnas NTUA, Aleiferis Ilias Uni Systems


## References
- [Link to the original CICIoT2023 dataset publication](https://www.unb.ca/cic/datasets/iotdataset-2023.html)

- https://drive.google.com/drive/u/0/folders/1HnOg3ff0ar71i1EACIBHoLHJqFfoMMG7 (Presentation)
