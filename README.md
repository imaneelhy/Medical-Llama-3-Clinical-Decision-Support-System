#  Medical Llama-3: Clinical Decision Support System

##  Project Overview
This repository contains the engineering pipeline for fine-tuning Meta's **Llama-3 8B** model to function as a specialized Medical AI Assistant.

Unlike generic LLMs, this model has been fine-tuned using **QLoRA (Quantized Low-Rank Adaptation)** on a specialized dataset of doctor-patient dialogues to ensure clinical accuracy, empathy, and professional terminology.

##  Technical Architecture
* **Base Model:** `unsloth/llama-3-8b-bnb-4bit` (Quantized for efficiency)
* **Fine-Tuning Method:** QLoRA (LoRA Alpha=16, r=16)
* **Optimization:** Unsloth Library (2x faster training, 0% memory degradation)
* **Dataset:** `ruslanmv/ai-medical-chatbot` (Real-world symptom/diagnosis pairs)
* **Infrastructure:** T4 GPU (Google Colab)

##  Performance & Results
The model demonstrates a significant shift from "generic assistant" to "medical professional."

**Example Inference:**
> **Patient Input:** "I have a severe headache and sensitivity to light. What could it be?"
>
> **Model Output:** "Hi, It could be due to many reasons. But the most common cause of headache is tension. It is common in stress and anxiety. You may have to consult a neurologist to find the exact cause... Regards, Dr. Hitesh Bhardwaj, Neurologist"

##  How to Run
The entire training and inference pipeline is contained in the Jupyter Notebook.

1.  Open the file `Medical_Llama3_Finetune.ipynb`.
2.  Run the cells sequentially.
3.  The model is set to load in 4-bit mode to allow inference on consumer-grade hardware (16GB VRAM or less).

##  Future Improvements
* **RAG Integration:** Connect this fine-tuned model to a vector database of local EHR (Electronic Health Records) to reduce hallucinations.
* **Quantization:** Export to GGUF format for local deployment on CPU-only devices.

---
*Project maintained by Imane EL HAJOUY*
