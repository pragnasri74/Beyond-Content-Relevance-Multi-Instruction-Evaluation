# Beyond Content Relevance: Evaluating Multi-Instruction Following in Retrieval Models

 **Course:** DS501 – Information Retrieval  
 **Institute:** IIT Bhilai  
 **Team Name:** QuestQ

 
**Overview**

This repository contains the code, datasets, and documentation for the project **“Beyond Content Relevance: Evaluating Multi-Instruction Following in Retrieval Models (Multi-Attribute Extension)”** as part of the **Information Retrieval** course at **IIT Bhilai**.

The project extends the **InfoSearch** benchmark from ICLR 2025 to evaluate how well retrieval and reranking models can follow **multi-instruction, multi-attribute queries**, such as:

> “Provide a short blog in English for laymen about X.”

rather than only single-attribute or purely topical relevance.

---

## 👥 Team

**Team Name:** QuestQ 

**Team Members**

- Arey Pragna Sri – 12240230  
- Matcha Jhansi Lakshmi – 12241000  
- Nannepaga Vanaja – 12241110  
- Bhagyashree Solanki – 12240400  

---

## 🧩 Project Description

Traditional retrieval benchmarks mostly measure **content relevance**: *Is this document about the same topic as the query?*  

Real users, however, often specify **multiple constraints simultaneously**, such as:

- Format (blog, news, code, manual)  
- Language (English, Chinese, etc.)  
- Length (short, paragraph, article)  
- Audience (layman vs expert)  
- Source type (blog, forum, news)  
- Presence of specific keywords  

The original **InfoSearch** benchmark evaluates **single-instruction** queries along these dimensions. Our project:

1. **Extends InfoSearch to multi-instruction queries**  
   - Combines **2–3 attributes** per query (e.g., *Format + Language + Audience*).
   - Uses GPT-based augmentation and rewriting to ensure gold documents satisfy multiple constraints.

2. **Builds a multi-attribute evaluation pipeline**  
   - Uses **BM25** (sparse baseline),  
   - Multiple **dense embedding-based retrievers**, and  
   - Strong **LLM-based rerankers**.

3. **Adapts and proposes metrics for multi-instruction compliance**  
   - **mSICR** – Multi-Instruction Strict Instruction Compliance Ratio  
   - **mWISE** – Multi-Instruction Weighted Instruction Sensitivity Evaluation  
   - **MDCR_strict / MDCR_soft** – Multi-Dimensional Compliance Ratio (strict & soft)

The goal is to quantify **how well models actually follow complex instructions**, not just whether they retrieve topically relevant documents.

---

## Project Overview 


 ## Frameworks and Tools
 
 • Python, PyTorch, Hugging Face Transformers.
 
 • GPT-4 API for data augmentation and document rewriting.


  ## Architecture

 <img width="890" height="693" alt="image" src="https://github.com/user-attachments/assets/62a61bcc-4f58-4a1a-b242-2df6db9d47f0" />

## 📈 Results & Observations
  The results support the hypothesis that multi-instruction following is substantially harder than standard content-based retrieval and that LLM-based reranking is currently the most promising direction, though at higher compute cost.

 **Sparse vs Dense**
  ![WhatsApp Image 2025-11-13 at 21 19 13_4d039fc8](https://github.com/user-attachments/assets/235e1f02-8875-4f97-b637-cdfcfd932a5f)


 **Dense vs rerankers**
 ![WhatsApp Image 2025-11-13 at 21 19 43_986898fc](https://github.com/user-attachments/assets/6aaa3670-0035-49e7-9ca0-7f7f4b8714bc)

 ## ⚙️ Installation Guide

   1. Clone the Repository
      
     git clone <https://github.com/pragnasri74/Beyond-Content-Relevance-Multi-Instruction-Evaluation.git>

     cd <https://github.com/pragnasri74/Beyond-Content-Relevance-Multi-Instruction-Evaluation.git>



   2.Place Datasets
   
   
   Ensure the following files exist:
   
    final_sorted.jsonl
    query-doc.json

   3. Running Experiments
      
   Run the file
          
     IR_Project_Final.ipynb 
      
   
