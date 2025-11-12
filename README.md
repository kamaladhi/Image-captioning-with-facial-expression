# Image Captioning with Facial Expression  
*A combined pipeline for face‑emotion detection and image captioning*

**Authors:** Jeevakamal K. R. ([@kamaladhi](https://github.com/kamaladhi)), Guhan K. B. ([@Guhanbala](https://github.com/Guhanbala)), Gowtham S. D. ([@GowthamDhanaraju](https://github.com/GowthamDhanaraju)), Shatha Varsha Sree T. ([@ShathaVarsha](https://github.com/ShathaVarsha))  
**Course:** Introduction to AI & Machine Learning  
**Supervisor:** Dr. Krithish Gupta  
**Semester Project – 2nd Semester**

---

## 📘 Project Overview  
This repository presents a two‑stage system that takes images containing human faces, detects the facial emotion (e.g., happy or sad), and then generates an image caption that incorporates the detected emotion for more expressive, enriched descriptions.

Key functionalities:  
- Real‑time (or static) detection of a human face’s emotion (happy vs. sad)  
- Image captioning model based on encoder‑decoder architecture (CNN encoder + Transformer decoder)  
- Integration of emotion information into the caption generation process using an NLP component (e.g., GPT‑2)  
- Pipeline designed to combine vision (emotion + image features) and language (caption generation)  

---

## 🔧 Architecture & Modules  

### 1. Emotion Detection  
A Convolutional Neural Network (CNN) is trained (or fine‑tuned) to classify each detected human face into one of two emotional states: **Happy** or **Sad**. Facial feature extraction → emotion classification.

### 2. Image Captioning  
The image captioning module comprises:  
- **Encoder**: A CNN that extracts a feature vector from an input image.  
- **Decoder**: A Transformer or sequence model that takes the feature vector and generates a caption via a softmax–based word‑by‑word language generation process.

### 3. Emotion + Caption Integration  
Once the emotion is detected and a base caption is generated, an NLP module (e.g., GPT‑2 or another language model) takes both the base caption **and** the emotion label as input, and outputs a refined caption (max length ~30 words) that reflects both what’s visually present *and* the emotional state of the face.

---

## 📁 Repository Contents  
| File / Folder              | Description                                                                 |
|----------------------------|-----------------------------------------------------------------------------|
| `Emotion_Recognition_CNN.ipynb` | Notebook for training & evaluating the face‑emotion detection CNN.         |
| `Image_captioning_TRANSFORMERS.ipynb` | Notebook for training the encoder‑decoder captioning model.           |
| `NLP_Emotion+Captioning.ipynb`         | Notebook for the integration of emotion label and base caption into final refined caption. |
| `LICENSE`                        | MIT License (see below).                                                |
| `README.md`                      | (This file)                                                               |

---

## 🛠️ Setup & Usage  
1. Clone the repository:  
   ```bash
   git clone https://github.com/kamaladhi/Image-captioning-with-facial-expression.git
   cd Image-captioning-with-facial-expression
   ```  
2. Make sure you have the required environment (e.g., Python 3.x, Jupyter notebooks, PyTorch/TensorFlow, HuggingFace Transformers, OpenCV).  
3. **Emotion Detection** module: Open and execute `Emotion_Recognition_CNN.ipynb`. Train / load the CNN model and test on sample images.  
4. **Image Captioning** module: Open `Image_captioning_TRANSFORMERS.ipynb`. Train / load the captioning model, generate captions from images.  
5. **Integration Module**: Open `NLP_Emotion+Captioning.ipynb`. Pass the emotion label + base caption into the NLP model to produce final captions.  
6. (Optional) Extend or modify:  
   - Expand emotion classes (beyond happy/sad)  
   - Use other captioning architectures or datasets  
   - Deploy as a web service or integrate into a larger application  

---

## 🎯 Potential Extensions  
- Increase the emotion classification granularity (e.g., angry, surprised, disgusted, neutral)  
- Use more sophisticated image captioning datasets (e.g., MS COCO, Flickr30k) with transfer‑learning  
- Real‑time webcam feed: grab a frame, detect face + emotion, generate caption on the fly  
- User interface: simple web or mobile app interface to upload image → show final caption  
- Evaluation metrics: For captioning (BLEU, METEOR, CIDEr), for emotion detection (accuracy, confusion matrix)

---

## ✅ Limitations & Considerations  
- Current emotion detection module is limited to **two** classes (happy / sad) — may misclassify other emotional states.  
- Captioning model is basic: depending on dataset size & compute resources, generated captions may be generic or inaccurate.  
- Integration of emotion into captioning is simple — more nuanced emotional contexts (e.g., “she looks anxiously happy”) are not handled.  
- Ethical / privacy concerns: face detection/emotion recognition can raise issues in real‑world deployment (consent, bias, fairness).  
- Dataset biases and model overfitting: ensure proper validation and diverse data.

---

## 🧑‍💻 Contributors  
- [Jeevakamal K. R.](https://github.com/kamaladhi)  
- [Shatha Varsha Sree T.](https://github.com/ShathaVarsha)  
- [Gowtham S. D.](https://github.com/GowthamDhanaraju)  
- [Guhan K. B.](https://github.com/Guhanbala)  

---

## 📄 License  
This project is licensed under the MIT License – see the [LICENSE](LICENSE) file for details.  
You are free to use, modify, and distribute this code, but please give appropriate credit.

---


