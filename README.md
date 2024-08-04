# Real-Time Prompt Monitoring System

## Overview

This project is a real-time prompt monitoring system designed for companies to monitor the prompts entered into their chatbots by employees. It leverages advanced NLP models to ensure the integrity and security of the interactions by filtering out harmful speech and detecting private information leaks.
Features

Harmful Speech Detection: Utilizes the ToxicBERT model to filter out harmful and toxic speech in real-time.
Private Information Leak Detection: Employs a fine-tuned version of the Llama 2 model, named "Ethical Guardian v2," to detect and prevent any private or sensitive information from being leaked through chatbot prompts.
Technology Stack

ToxicBERT: A pre-trained BERT model specifically fine-tuned to detect toxic speech.
Llama 2: A fine-tuned version of the Llama 2 model, customized to identify and flag private information.
Python: The primary programming language used for model integration and system development.
Flask: A micro web framework used for building the API and serving the models.
Google Colab: Utilized for fine-tuning the Llama 2 model due to its resource requirements.
Installation

## Clone the Repository
sh
Copy code
git clone https://github.com/your-username/prompt-monitoring-system.git
cd prompt-monitoring-system
Set Up Virtual Environment
sh
Copy code
python3 -m venv venv
source venv/bin/activate   # On Windows use `venv\Scripts\activate`
Install Dependencies
sh
Copy code
pip install -r requirements.txt
Run the Application
sh
Copy code
flask run
Model Information

## Ethical Guardian v2
Model Name: NousResearch/Llama-2-7b-chat-hf
Dataset: synapsecai/synthetic-sensitive-information (20% subset)
QLoRA Parameters
lora_r = 64
lora_alpha = 16
lora_dropout = 0.1
BitsAndBytes Parameters
use_4bit = True
bnb_4bit_compute_dtype = "float16"
bnb_4bit_quant_type = "nf4"
use_nested_quant = False
Training Arguments
num_train_epochs = 1
fp16 = False
bf16 = False
per_device_train_batch_size = 32
per_device_eval_batch_size = 16
gradient_accumulation_steps = 1
gradient_checkpointing = True
max_grad_norm = 0.3
learning_rate = 2e-4
weight_decay = 0.001
optim = "paged_adamw_32bit"
lr_scheduler_type = "cosine"
max_steps = -1
warmup_ratio = 0.03
group_by_length = True
save_steps = 0
logging_steps = 25
SFT Parameters
max_seq_length = None
packing = False
Description
Ethical Guardian v2 is an ethically fine-tuned version of Llama 2, specifically trained to detect and flag private or sensitive information within natural text. It serves as a powerful tool for data privacy and security, capable of identifying potentially vulnerable data such as:
API keys
Personally Identifiable Information (PII)
Financial data
Confidential business information
Login credentials
Key Features
Analyzes natural language input to identify sensitive content
Provides explanations for detected sensitive information
Helps prevent accidental exposure of private data
Supports responsible data handling practices
Use Cases
Content moderation
Data loss prevention
Compliance checks for GDPR, HIPAA, etc.
Security audits of text-based communications
This model aims to enhance data protection measures and promote ethical handling of sensitive information in various applications and industries.
