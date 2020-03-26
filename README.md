# NLP_masters_project
Code base used for NLP project 2020.

By Daniel de Vassimon Manela, Boris van Breugel, Tom Fisher, David Errington

---
## Contents
* `process_ontonotes.ipynb`: Loads the Ontonotes Release 5.0 data from [Github](https://github.com/yuchenlin/OntoNotes-5.0-NER-BIO.git), and processes
raw data into a suitable formatting for modelling. Notebook is also dependent on data loaded from [UCLA NLP Group](https://github.com/uclanlp/gn_glove.git). Both these files are loaded within the notebook. Running notebook back-to-front returns `original_data.csv` and `flipped_data.csv`, which are used in training a BERT Masked Language Model.
* `BERT_fine_tuning_full_ontonotes.ipynb`: Loads the output of `process_ontonotes.ipynb` and trains a BERT Masked Language Model using [Huggingface](https://github.com/huggingface/transformers) directory. Be sure to correctly comment/uncomment out the lines for loading the data. Data Augmented models require loadeing in both `original_data.csv` and `flipped_data.csv`. To train a regular unaugmented finetuned models, only load `original_data.csv`.
* `Bias_analysis.ipynb`: Analyses streo and skew bias in out-of-the-box BERT, distilBERT and RoBERTa using WinoBias dataset [Zhao 2018]. Includes visualisations of professional embedding bias, and compares bias in BERT to industry statistics. Includes ELMo Baseline 
