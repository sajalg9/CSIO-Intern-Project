# 🐛 AI Methods to Predict Pest Severity Using Crowdsourced Data

## 📌 Overview

This project presents an **AI-driven spatio-temporal pest severity prediction system** built using **crowdsourced agricultural query data** from the **Kisan Call Center (KCC)** initiative of the Government of India.

Traditional pest monitoring techniques rely on manual field inspections, image-based systems, or sensor infrastructure, which often face limitations in scalability, deployment cost, and geographical coverage. This project explores a novel alternative: **leveraging farmer helpline queries as a proxy signal for pest outbreaks**.

By analyzing multilingual farmer queries and combining **Natural Language Processing (NLP)** with **Temporal and Spatio-Temporal Deep Learning Models**, this system predicts pest severity patterns across Indian districts and acts as a potential **early warning system for agricultural pest outbreaks**.

Developed during an internship at **CSIR-Central Scientific Instruments Organisation (CSIR-CSIO), Chandigarh**.

---

## 🎯 Problem Statement

Agricultural pest outbreaks lead to substantial crop losses every year and significantly impact food security. Existing methods suffer from limitations such as:

* Poor scalability across large agricultural regions
* Dependence on manual field inspections
* High deployment and maintenance costs
* Inability to capture regional pest spread dynamics

This project addresses these limitations by utilizing **crowdsourced farmer queries** from the **Kisan Call Center (KCC)** to predict **district-level pest severity patterns** using **AI-based forecasting models**.

---

## 🧠 Key Objectives

* Build a **multilingual preprocessing pipeline** for KCC farmer queries
* Detect language and translate non-English agricultural queries
* Extract pest information using NLP techniques
* Construct district-level **time-series pest datasets**
* Develop and compare **temporal** and **spatio-temporal forecasting models**
* Model **spatial pest spread across neighboring districts**
* Predict **pest severity trends for early warning systems**

---

## 🏗️ Project Pipeline

### 1️⃣ Data Collection

* **Source:** Kisan Call Center (KCC) Dataset
* Farmer queries collected across India
* Includes:

  * District & State
  * Query Date
  * Crop Information
  * Farmer Query Text
  * Agricultural Category

---

### 2️⃣ Multilingual NLP Pipeline

#### 🔹 Language Detection

* Implemented using **IndicLID**
* Supports multiple Indian languages and transliterated text

#### 🔹 Translation

* Non-English queries translated into English using **IndicTrans2**
* Supports **22 scheduled Indian languages**

#### 🔹 Pest Extraction Engine

Custom NLP pipeline for pest extraction:

* Text normalization
* Pest synonym handling
* Multi-pest detection
* **spaCy PhraseMatcher-based extraction**

Supported detection for **40+ agricultural pests** including:

`Whitefly`, `Aphid`, `Thrips`, `Armyworm`, `Bollworm`, `Leaf Folder`, `Stem Borer`, `Fruit Fly`, `Mealybug`, and more.

---

### 3️⃣ Data Aggregation & Time-Series Construction

Processed query data was aggregated into:

**District × Pest × Month**

time-series records to model temporal and spatial pest activity across India.

---

## 📊 Exploratory Data Analysis (EDA)

Key observations:

* Strong seasonal and temporal variability in pest outbreaks
* Geographic clustering of pest severity
* Top pests dominated a major portion of farmer-reported cases
* Significant district-wise concentration of pest activity

---

## 🤖 Models Implemented

### 1. SARIMA

Statistical baseline model for seasonal time-series forecasting.

**Purpose**

* Captures seasonal pest trends
* Baseline temporal forecasting

---

### 2. LSTM (Long Short-Term Memory)

Deep learning-based temporal forecasting model.

**Features**

* Sliding window sequence generation
* MinMax scaling
* Multi-layer LSTM architecture
* Time-series prediction

---

### 3. STGCN (Spatio-Temporal Graph Convolutional Network)

Graph Neural Network model that jointly learns:

* **Temporal pest patterns**
* **Spatial district relationships**

District connectivity modeled using:

**K-Nearest Neighbor (KNN) Spatial Graph**

---

### 4. STGAT (Spatio-Temporal Graph Attention Network)

Enhanced version of STGCN using:

**Graph Attention Networks (GAT)**

Benefits:

* Dynamic neighbor weighting
* Adaptive spatial dependency learning
* Improved contextual modeling

---

### 5. MPNN (Message Passing Neural Network) ⭐

**Best Performing Model**

A customized spatio-temporal message passing architecture:

* Distance-weighted message aggregation
* Spatial graph learning
* LSTM-based temporal modeling
* District-wise pest severity prediction

---

### 6. Spatio-Temporal XGBoost Classification

Classification model for pest severity levels using:

* Weather features
* Temporal lags
* Spatial district connectivity
* Historical pest observations

---

## 🛠️ Tech Stack

### Languages

* Python

### Libraries & Frameworks

* **PyTorch**
* **PyTorch Geometric**
* **TensorFlow / Keras**
* **scikit-learn**
* **spaCy**
* **Transformers (HuggingFace)**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Statsmodels**
* **XGBoost**

### NLP Models

* **IndicLID**
* **IndicTrans2**

### Forecasting & ML

* SARIMA
* LSTM
* STGCN
* STGAT
* MPNN
* XGBoost

---

## 🗺️ Spatial Modeling

A district-level spatial graph was constructed using:

* **Latitude & Longitude Coordinates**
* **Haversine Distance**
* **K-Nearest Neighbors (KNN)**

This enabled modeling of **cross-district pest spread dynamics**, unlike traditional time-series models.

---

## 📈 Results & Findings

* **Spatio-temporal models outperformed purely temporal models**
* Models capturing **spatial dependencies** significantly improved forecasting performance
* **MPNN achieved the best performance**
* Crowdsourced agricultural queries proved to be a reliable proxy for pest outbreak prediction

---

## 🚀 Future Scope

* Real-time pest forecasting dashboard
* Integration with satellite/weather APIs
* State-level agricultural alert systems
* Mobile-based farmer early warning notifications
* Transformer-based spatio-temporal architectures

---

## 🏢 Internship Details

**Organization:** CSIR – Central Scientific Instruments Organisation (CSIR-CSIO), Chandigarh <br>
**Duration:** Internship Semester (January 2026 – April 2026)

---

## 👨‍💻 Author

**Sajal Goel**<br>
B.Tech CSE (Data Science)<br>
Punjab Engineering College (PEC), Chandigarh

---

## ⭐ Acknowledgement

Special thanks to **CSIR-CSIO Chandigarh** and project mentors for guidance and support throughout this work.
