Data collections for text summarization
=================

**Students:** Moreno Sara, Galvagno Stefano

   * [PubMed](#PubMed)
   * [arXiv](#arXiv)
---
### PubMed
**Published:** 05-22-2018

**Dataset:** dataset can be downloaded from the official implementation of [A Discourse-Aware Attention Model for Abstractive Summarization of Long Documents](https://github.com/armancohan/long-summarization)

**Paper:** [https://arxiv.org/abs/1804.05685](https://arxiv.org/abs/1804.05685) - for the paper presenting the data collection

**Task:** Summarization

**Dataset Description:**
The dataset include a set of medical long form documents that preserved their discourse structure.

It has been used for the task of summarizing long document withou losing the information contained in its structure.

**Dataset Stats:**

- Training set: 119,924 samples
- Evaluation set: 6,633 samples
- Test Set: 6,658 samples
- Dataset format: JSON
---
### arXiv
**Published:** 05-22-2018

**Dataset:** dataset can be downloaded from the official implementation of [A Discourse-Aware Attention Model for Abstractive Summarization of Long Documents](https://github.com/armancohan/long-summarization))

**Paper:** [https://arxiv.org/abs/1804.05685](https://arxiv.org/abs/1804.05685) - for the paper presenting the data collection

**Task:** Summarization

**Dataset Description:**
The dataset include a set of documents crawled from [arXiv](https://arxiv.org/).

It has been used for the task of summarizing long document withou losing the information contained in its structure.

**Dataset Stats:**

- Training set: 203,037 samples
- Evaluation set: 6,436 samples
- Test Set: 6,440 samples
- Dataset format: JSON

---
**How to use the data collections:** Both the datasets are subsampled, only 600 samples are used for the training, 200 for the evaluation and 200 for testing. The subsamples are optained with the dataset_subset_creation notebook.
This notebook also creates the mixed subset of the original dataset.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/10oWL_RDSoFTJdi-EbNIgTDWLDxEpr__h?usp=sharing)

**Bibtex:**

```
@misc{https://doi.org/10.48550/arxiv.1804.05685,
  doi = {10.48550/ARXIV.1804.05685},
  
  url = {https://arxiv.org/abs/1804.05685},
  
  author = {Cohan, Arman and Dernoncourt, Franck and Kim, Doo Soon and Bui, Trung and Kim, Seokhwan and Chang, Walter and Goharian, Nazli},
  
  keywords = {Computation and Language (cs.CL), FOS: Computer and information sciences, FOS: Computer and information sciences},
  
  title = {A Discourse-Aware Attention Model for Abstractive Summarization of Long Documents},
  
  publisher = {arXiv},
  
  year = {2018},
  
  copyright = {arXiv.org perpetual, non-exclusive license}
}

```
