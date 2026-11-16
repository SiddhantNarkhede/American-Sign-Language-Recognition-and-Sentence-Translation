# American Sign Language Recognition and Sentence Translation

An end-to-end American Sign Language (ASL) recognition system that combines computer vision, deep learning, and natural language processing to recognize individual signs and translate sign sequences into grammatically coherent English sentences.

## Overview

The project implements a two-stage pipeline:

1. **Sign Recognition:** Extracts spatial and facial landmarks using MediaPipe Holistic and classifies temporal sign sequences using a custom LSTM-based neural network.
2. **Sentence Translation:** Converts recognized sign sequences into natural English sentences using a fine-tuned T5 Transformer.

## Technical Architecture

### 1. Landmark Extraction & Sign Recognition
- Used **MediaPipe Holistic** to extract 1,662 pose, face, and hand keypoints per frame.
- Processed 30-frame sequences from the **WLASL dataset**.
- Developed a custom three-layer LSTM architecture incorporating a Bidirectional LSTM, LeakyReLU activations, and fully connected classification layers.
- Implemented real-time inference using OpenCV with confidence-thresholded predictions.

### 2. Sentence Translation
- Fine-tuned **T5-small** on ASL grammar–English sentence pairs to translate recognized sign sequences into natural English.
- Incorporated rule-based question detection to improve sentence interpretation.
- Explored GPT-2 and Transformer-based approaches for language modelling and classification.

### 3. Model Optimisation & Experimentation
- Experimented with interpolation-based sequence normalisation and data augmentation.
- Evaluated alternative Transformer architectures for sign classification.
- Used confidence thresholds to improve the reliability of live predictions.

## Technology Stack

| Category | Technologies |
|---|---|
| Programming | Python |
| Computer Vision | OpenCV, MediaPipe Holistic |
| Deep Learning | TensorFlow, Keras, PyTorch |
| Sequence Modelling | LSTM, Bidirectional LSTM |
| NLP & Transformers | Hugging Face Transformers, T5-small, GPT-2 |
| Data Processing | NumPy, Pandas, SciPy |
| Machine Learning | Scikit-learn |
| Visualisation | Matplotlib |
| Dataset | WLASL |

## Pipeline

```text
Video Input
    |
    v
MediaPipe Holistic
    |
    v
1,662 Keypoints per Frame
    |
    v
30-Frame Sequence
    |
    v
Custom LSTM Classifier
    |
    v
Recognised Sign Sequence
    |
    v
Fine-tuned T5-small
    |
    v
Natural English Sentence
```

## Key Highlights

- End-to-end integration of computer vision, temporal deep learning, and NLP.
- Custom recurrent neural network architecture for dynamic sign recognition.
- Transformer-based translation for converting sign sequences into grammatically coherent sentences.
- Real-time video inference with confidence-based prediction filtering.

---

*This project explores the intersection of human-computer interaction, sequence learning, and natural language understanding to make communication more accessible.*
