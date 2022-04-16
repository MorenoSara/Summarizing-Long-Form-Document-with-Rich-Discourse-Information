# Summarizing-Long-Form-Document-with-Rich-Discourse-Information

This work is an assignment for the course of `Deep Natural Language Processing` at `Politecnico di Torino` in the academic year 2021/2022. 

In this project we tried to implement *HEROES (Hierarchy-Enhanced Graph for Rich-discOurse Document Extractive Summarization)*, a model presented in the paper [Summarizing Long-Form Document with Rich Discourse Information, Tianyu Zhu et al](https://dl.acm.org/doi/abs/10.1145/3459637.3482396)). 

The model is composed of 2 separate modules:
* **Content Ranking Module**: assigns a relevance score to each section and sentence;
* **Extractive Summarization Module**: takes the digested documents produced by the first module and exracts summary-worthy sentences by means of heretorgeneous graphs.

We proposed two extensions:
* **Data enrichment**: we trained the model with a mixture of PubMed and arXiv dataset;
* **Ablation study**: 
  1. Model without Content Ranking Module;
  2. Disable the iterative update of nodes representetions in the Extractive Summarization Module;
  3. Remove the boundary distance feature.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/14xPy1cdP-6FiDkWaMR-m4RfgntJh5H5e?usp=sharing)

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
In our work the only exploited fields are: 
- `abstract_text`: all the strings composing the abstract of the scientific paper;
- `section_names`: a title for each section contained in the document; 
- `sections`: all the sentences of each section of the document.

# Usage
It is possible to exploit the model by simply setting the correct data paths in the **Paths** section of the notebook and running the whole code.

# Output document
Each time the model is tested it creates a file in the `./test` directory (if not already present it creates it) named after the current timestamp. An example of returned document is the following:
```bash
[Reference]  <S> acute occlusion of the superior mesenteric artery ( sma ) causes extensive bowel necrosis , resulting in a poor prognosis with an extremely high mortality rate . </S> <S> an 82-year - old woman was admitted to our hospital with the complaint of abdominal pain . </S> <S> she was diagnosed as having acute sma occlusion by enhanced ct . </S> <S> five hours from onset , the first thrombolytic therapy with urokinase was performed , but failed to complete thrombolysis and recanalization of peripheral blood flow . </S> <S> an exploratory laparotomy following the first thrombolytic therapy showed a mild ischemic change in the affected intestine and mesentery , but no sign of necrosis . </S> <S> after the laparotomy , local thrombolytic therapy with angiographic evaluation of blood flow at 24 , 36 and 48 h from the first thrombolysis was performed . as a result , </S> <S> the residual thrombus disappeared and all branches of the sma became well visualized . </S> <S> the patient was discharged well without a second - look operation or major bowel resection . </S> <S> sequential intermittent thrombolytic therapy with meticulous angiographic evaluation of blood flow is effective for early - stage acute sma occlusion . </S>
[Hypothesis]  acute occlusion of the superior mesenteric artery ( sma ) causes extensive intestinal necrosis due to the difficulty of early diagnosis , resulting in poor prognosis , with a high postoperative mortality rate of 65.2% .a mild ischemic change was observed at the intestinal wall from the jejunum 40 cm distal from the treitz ligament to the ascending colon , but no apparent necrosis .early thrombolytic therapy can not always induce complete thrombolysis , and even if intestinal necrosis is avoided by administration of initial thrombolytic therapy , indications for additional thrombolytic therapy or the method for monitoring intestinal viability during subsequent follow - up have not been established . in this report , we present a case of acute sma occlusion diagnosed early after onset that was successfully treated by sequential and intermittent thrombolytic therapy by intraarterial urokinase infusion with angiographic evaluation of blood flow , thereby avoiding intestinal resection .recent reports indicate that selective thrombolytic therapy with intraarterial infusion of urokinase is effective for acute sma occlusion diagnosed early after onset .24 h after the laparotomy , a second angiography was performed via the catheter that remained in place after first angiography , because clinical signs such as abdominal pain suggested the progression of intestinal ischemia .blood flow in the mesentery was well palpable at the central portion of the sma , while peripheral blood flow was not palpable .the operation was completed without intestinal resection or direct removal of the thrombus from the sma .

[Reference] ...
[Hypothesis] ...

...
```
`Reference`: is the abstract of the scientific paper.

`Hypothesis`: is the extracted summary.
