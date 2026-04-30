# Agentic Geo-VQA: A Multimodal Vision-Language Architecture for Spatiotemporal Landslide Susceptibility Forecasting

## Overview
This repository contains the source code and LaTeX documents for my Bachelor Thesis Project (BTP-II) at **IIT Kharagpur**. 

Traditional Landslide Susceptibility Mapping (LSM) models often function as "black boxes," providing probability scores without explaining the underlying geomorphological and temporal rationale. This project introduces **Agentic Geo-VQA**, a paradigm shift that integrates a **Spatiotemporal Vision Agent** (Convolutional LSTM) with a **Cognitive Language Agent** (Qwen 2.5 7B LLM). The framework translates complex spatiotemporal tensors into human-readable, expert-level geotechnical diagnostic reports, explaining *why* specific terrains are susceptible to failure.

## Key Features
- **Spatiotemporal Encoding**: Uses a 4-layer **Convolutional LSTM (ConvLSTM)** to decode 8-year temporal Land Use/Land Cover (LULC) dynamics and 19 topographic/geological conditioning factors.
- **Cognitive Reasoning**: Leverages the **Qwen 2.5 (7B-Instruct)** Large Language Model as a virtual geotechnical expert.
- **Multimodal Alignment**: Implements a custom **MLP Projector** to map visual embeddings from the ConvLSTM into the LLM's latent space.
- **Hardware Optimization**: Utilizes **4-bit Quantization and Low-Rank Adaptation (QLoRA)** to enable training on consumer-grade hardware (16GB VRAM).
- **Interpretability**: Generates natural language diagnostic reports that analyze gravitational potential energy, root-cohesion degradation, and meteorological triggers.

## Performance
- **Vision Agent (ConvLSTM)**: Achieved a state-of-the-art **AUC-ROC of 0.9535** and an accuracy of **87.95%** on the Raigad District dataset.
- **Language Alignment**: Successfully converged from an initial CLM loss of 3.4380 to 1.4264 over 2 epochs.

## Repository Structure
```text
├── main.tex                # LaTeX source for the final thesis report
├── slide.tex               # LaTeX source for the Beamer presentation
├── main_code.ipynb         # End-to-end Python implementation (Pre-training, Alignment, Inference)
├── geo_vqa_aligned_weights/ # Directory containing trained model weights
├── references.bib          # Bibliography for the research
├── IIT_Kharagpur_Logo.png  # Institutional logo for LaTeX docs
└── outputs_publication/    # Generated maps, distribution plots, and benchmark tables
```

## Getting Started

### Prerequisites
- **LaTeX**: To compile the report and slides, you need a TeX distribution (e.g., TeX Live, MiKTeX) or use Overleaf.
- **Python Environment**:
  - `torch`, `torchvision`
  - `transformers`, `accelerate`, `bitsandbytes`, `peft` (HuggingFace stack)
  - `rasterio`, `geopandas`, `shapely` (Geospatial stack)
  - `numpy`, `pandas`, `matplotlib`, `seaborn`

### Installation
```bash
pip install torch transformers accelerate bitsandbytes peft rasterio geopandas
```

### Usage
1. **Model Training**: Open `main_code.ipynb` to view the data preprocessing, ConvLSTM pre-training, and multimodal alignment steps.
2. **Compilation**:
   - Compile `main.tex` using `pdflatex` and `bibtex` for the full report.
   - Compile `slide.tex` using `pdflatex` for the presentation slides.

## Author
**Nabarup Ghosh**  
Roll No: 22GG10028  
Department of Geology and Geophysics  
Indian Institute of Technology Kharagpur  

**Supervisor**: Prof. Paresh Nath Singha Roy

## Acknowledgments
Special thanks to the Department of Geology and Geophysics, IIT Kharagpur, for providing the resources and guidance necessary to complete this project.
