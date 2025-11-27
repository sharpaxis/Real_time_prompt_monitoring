


# Real-Time Prompt Monitoring System

<p align="center">
  <a href="#"><img src="https://img.shields.io/badge/build-passing-brightgreen" /></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue" /></a>
  <a href="https://huggingface.co/Sharpaxis/Llama-2-7_Ethical_Guardian"><img src="https://img.shields.io/badge/Model-Llama_2_Ethical_Guardian-orange" /></a>
  <a href="https://huggingface.co/Sharpaxis/distilbert-sensitive-classification"><img src="https://img.shields.io/badge/Model-DistilBERT_Sensitive-red" /></a>
  <a href="https://huggingface.co/datasets/Sharpaxis/Synthetic-Sensitive-data"><img src="https://img.shields.io/badge/Dataset-Synthetic_Sensitive_Data-yellow" /></a>
</p>



# Overview

The Real-Time Prompt Monitoring System is designed for companies that use chatbots internally and want to ensure that employee-entered prompts remain safe, compliant, and free from sensitive information leaks.

The system processes every prompt in real-time and performs two major checks:
	•	Hate/Toxic Speech Detection
	•	Sensitive Information Leak Detection
(passwords, API keys, emails, tokens, credentials, and other confidential identifiers)

This solution acts as an AI firewall between employees and corporate LLM systems.



# ✨ Features

🔒 Private Information Leak Detection

Powered by a fine-tuned Llama 2 model:
➡ Ethical Guardian v2
### 🔗 https://huggingface.co/Sharpaxis/Llama-2-7_Ethical_Guardian

Detects:
	•	API keys
	•	Passwords
	•	Access tokens
	•	Internal IDs
	•	Sensitive corporate data
	•	Personally Identifiable Information (PII)

## 🛡 Harmful Speech Detection

Using ToxicBERT, the system detects and blocks:
	•	Abusive language
	•	Harassment
	•	Discriminatory or toxic sentences

## 🧪 Sensitive-String Classifier (DistilBERT)

Model:
### ➡ https://huggingface.co/Sharpaxis/distilbert-sensitive-classification

This model specifically detects:
	•	Keys
	•	Passwords
	•	API tokens
	•	Private strings that follow known credential patterns

Works as a second-layer safety filter.


## 🧰 Technology Stack

Component	Description
Python	Primary backend language
Flask	API server for real-time inference
ToxicBERT	Toxic speech detection
Llama-2 (Ethical Guardian v2)	Sensitive information leak detection
DistilBERT Sensitive Classifier	Detects credential-pattern leaks
Google Colab	Used for fine-tuning Llama 2
QLoRA	Parameter-efficient training methodology



## 🚀 Installation

1. Clone the Repository

git clone https://github.com/your-username/prompt-monitoring-system.git
cd prompt-monitoring-system

2. Create Virtual Environment

python3 -m venv venv
source venv/bin/activate     # macOS & Linux
venv\Scripts\activate        # Windows

3. Install Dependencies

pip install -r requirements.txt

4. Run the Application

flask run


# 🤖 Model Information

## 🦙 Ethical Guardian v2 — Llama-2 Fine-Tuned Model

Property	Value
Base Model	NousResearch/Llama-2-7b-chat-hf
Dataset	synapsecai/synthetic-sensitive-information (20%)
QLoRA Rank	64
QLoRA Alpha	16
Dropout	0.1
Quantization	4-bit NF4
Training Epochs	1 epoch
Batch Size	32
Learning Rate	2e-4
Optimizer	paged_adamw_32bit
Max Grad Norm	0.3
Warmup	3%
Gradient Checkpointing	Enabled

DistilBERT Sensitive Classifier

Detects:
	•	Passwords
	•	API Keys
	•	Tokens
	•	Other credential strings

### 🔗 https://huggingface.co/Sharpaxis/distilbert-sensitive-classification

ToxicBERT

Used for filtering:
	•	Toxic, harmful, or unsafe text
	•	Threatening/abusive content


# 📊 Dataset

The primary dataset used for fine-tuning:

🔗 Synthetic Sensitive Data
### https://huggingface.co/datasets/Sharpaxis/Synthetic-Sensitive-data

Contains examples of:
	•	API keys
	•	Passwords
	•	Database credentials
	•	PII samples
	•	Sensitive corporate identifiers

