# Summarizing-Long-Form-Document-with-Rich-Discourse-Information

This work is an assignment for the course of `Deep Natural Language Processing` at `Politecnico di Torino` in the academic year 2021/2022. 

In this project we tried to implement *HEROES (Hierarchy-Enhanced Graph for Rich-discOurse Document Extractive Summarization)*, a model presented in the paper [Summarizing Long-Form Document with Rich Discourse Information, Tianyu Zhu et al](https://dl.acm.org/doi/abs/10.1145/3459637.3482396)). 

The model is composed of 2 separate modules:
* **Content Ranking Module**: assigns a relevance score to each section and sentence;
* **Extractive Summarization Module**: takes the digested documents produced by the first module and exracts summary-worthy sentences by means of heretorgeneous graphs.

We proposed two extensions:
* **Data enrichment**: we trained the model with a mixture of PubMed and arXiv dataset;
* **Ablation study**: we tested the model without Content Ranking Module, disabling the iterative update of nodes representetions in the Extractive Summarization Module and the last one, without the boundary distance feature.

# Implementation details
The Python version used is `3.7.13`
## Libraries details
- [PyTorch](https://pytorch.org/): `1.10.0+cu111`
- [Rouge](https://github.com/pltrdy/rouge): `1.0.1`
- [DGL](http://dgl.ai): `0.6.1`
- dgl-cu101: `0.6.1`
- others:
  -  NumPy
  -  json

# Inputa data format
Each document is a JSON with the following structure:
```bash
{
    article_id: str
    abstract_text: List[str]
    article_text: List[str]
    section_names: List[str]
    sections: List[List[str]]
}
```
