# Fine-Tuning Latent Diffusion Model on Naruto-Style Images (LDM-Finetune-Naruto)

This project fine-tunes a Latent Diffusion Model (Stable Diffusion v1.5) to generate Naruto-style images from text prompts. Only the U-Net module is trained on a custom image-caption dataset while keeping the CLIP tokenizer and VAE encoder-decoder frozen. A Streamlit app is used for seamless UI interaction and image generation.

---

## 📌 Objective

Develop a Naruto-styled text-to-image generator using efficient fine-tuning of a pre-trained latent diffusion model.

---

## 📂 Dataset

- **Source**: [Lambda Labs Naruto BLIP Captions](https://huggingface.co/datasets/lambdalabs/naruto-blip-captions)
- **Images**: 1,200+ Naruto-style JPEGs
- **Captions**: BLIP-generated stylized prompts
- **Size**: ~700 MB
- **Split**: Train only

---

## 🧠 Model Architecture

- **CLIP Tokenizer** – Converts prompts to embeddings
- **VAE Encoder/Decoder** – Handles latent image representation
- **U-Net** – Fine-tuned for denoising in latent space
- **Latent Diffusion** – Efficient generation via latent space manipulation

---

## 🔧 Fine-Tuning Details

- **Base Model**: Stable Diffusion v1.5
- **Training Scope**: U-Net only
- **Epochs**: 10 (standard), 5 (Mo-Di-Diffusion variant)
- **Frameworks**: PyTorch, Hugging Face

---

## 🖥️ Streamlit App

- Input prompt and generate image
- Simple, clean UI for demo and testing
- Frontend + backend integration in Python

---
### 📊 Evaluation Summary (Before vs. After Fine-Tuning)

| **Metric**           | **Before Fine-Tuning** | **After Fine-Tuning** | **Change** | **Interpretation**                                             |
|----------------------|------------------------|------------------------|------------|-----------------------------------------------------------------|
| **CLIP Score**       | 23.55                  | 24.763                 | +1.213     | **Improved** text-image alignment                              |
| **LPIPS**            | 0.781                  | 0.709                  | -0.072     | **Improved** style similarity to Naruto                        |
| **FID Score**        | -                      | 412.527                | -          | High value suggests **room for quality improvement**           |
| **Inception Score**  | nan                    | nan                    | -          | Calculation failed due to **inconsistent model outputs**       |



---

## 📈 Results

- Naruto-style images aligned with textual prompts
- Compared outputs from both Stable Diffusion and Mo-Di-Diffusion variants
- Visual improvements observed post fine-tuning
- <img width="843" alt="image" src="https://github.com/user-attachments/assets/f42623b7-5843-4eb4-9a69-122ea85807b7" />
- <img width="946" alt="image" src="https://github.com/user-attachments/assets/be63c0ea-0393-4305-b05f-b2bac16c518a" />



---

## 🚀 Getting Started

```bash
Download Python notebooks
Run on Google Collab
Have atleast 25GB VRAM on your GPU
