# Citation Detector with IBM Granite 3.3 8B Instruct

## Title Project
Citation Detector with IBM Granite 3.3 8B Instruct

## Project Overview
Proyek ini bertujuan membangun model untuk mendeteksi apakah sebuah paper atau jurnal melakukan sitasi terhadap paper lain.  
Model yang digunakan adalah IBM Granite 3.3 8B Instruct untuk melakukan klasifikasi biner:  
- 1 = paper mereferensikan/mengutip paper lain  
- 0 = paper tidak mengutip  

Proyek ini merupakan eksperimen NLP untuk citation prediction.

## Raw Dataset
Dataset terdiri dari pasangan dokumen (paper_text, reference_text) beserta label sitasi.  
Link dataset: https://www.kaggle.com/competitions/gammafest25/data

## Insight & Findings
- Model baseline tradisional (misalnya bag-of-words + machine learning klasik) cenderung bias terhadap kelas mayoritas.  
- IBM Granite 3.3 8B Instruct lebih baik dalam memahami konteks teks dan hubungan sitasi.  
- Tantangan utama adalah preprocessing (panjang teks, token limit, dan chunking).  
- Recall pada kelas 1 (referenced) meningkat setelah tuning parameter dan strategi chunking.  

## AI Support Explanation
- LLM yang digunakan: IBM Granite 3.3 8B Instruct  
- Alasan pemilihan: model ini dirancang untuk instruction-following dan lebih baik dalam pemahaman teks ilmiah.  
- Pipeline eksperimen:  
  1. Preprocessing teks (cleaning, lowercasing, tokenization, chunking).  
  2. Membentuk pasangan teks (paper, reference).  
  3. Memasukkan teks ke model Granite dengan prompt klasifikasi.  
  4. Mengubah output model menjadi label 0 atau 1.  
