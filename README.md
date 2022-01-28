
# A Neural Graph-based Local Coherence Model

Entity grids and entity graphs are two frameworks for modeling local coherence. 
These frameworks represent entity relations between sentences and then extract features from such representations to encode coherence. 
The benefits of convolutional neural models for extracting informative features from entity grids have been recently studied. 
In this work, we study the benefits of Relational Graph Convolutional Networks (RGCN) to encode entity graphs for measuring local coherence. 
We evaluate our neural graph-based model for two benchmark coherence evaluation tasks: sentence ordering (SO) and summary coherence rating (SCR). 
The results show that our neural graph-based model consistently outperforms the neural grid-based model for both tasks. 
Our model performs competitively with a strong baseline coherence model, while our model uses 50% fewer parameters. 
Our work defines a new, efficient, and effective baseline for local coherence modeling.

Your interest to this project is very appreciated.
Please read and cite [this paper](https://aclanthology.org/2021.findings-emnlp.199/) to optimize what you can get from this repo.


https://www.ukp.tu-darmstadt.de/

https://www.tu-darmstadt.de/


Don't hesitate to send us an e-mail, if something is broken (and it shouldn't be) or if you have further questions.

> This repository contains experimental software and is published for the sole purpose of giving additional background details on the respective publication.

## Setup

# Virtual Environment

Our virtual environment is created as follows:
```bash
$ conda create --name coherence
$ source activate coherence
$ pip install -r requirements.txt 
```


# Main Packaged Required

* Python 3.6 with NumPy/SciPy
* PyTorch 1.1 or higher
* Allennlp
* torchtext

# Datasets (SO, SCR)

## Sentence Ordering Dataset (SO)
```bash
cd /ukp-storage-1/mesgar/coherence/graph_nn_for_coherence/Dataset_Generation/Dataset_Generation_so/
```

Scripts for generating SO datasets are in the ``Dataset_Generation_so`` directory. 

What should be done to generate the datasets?

creat *_pos and *_neg files and folders:
```
python Perm.py
```

To create train, dev and test sets:

```
python DataPrep_Docu.py --train_pos ./train_pos/ --train_neg ./train_neg/ --test_pos ./dev_pos/ --test_neg ./dev_neg/

mv ./Dataset/test ./Dataset/dev


python DataPrep_Docu.py --train_pos ./train_pos/ --train_neg ./train_neg/ --test_pos ./test_pos/ --test_neg ./test_neg/
```

Now train, dev, and test sets should be ready in ``Dataset`` directory. 
Followings are some statistics:

```bash
ls -l ./Dataset/train | wc -l
# 49601

ls -l ./Dataset/dev | wc -l
# 5521

ls -l ./Dataset/test | wc -l
# 42121

```

## Summary Coherence Rating Dataset (SCR)
The dataset related to the summary coherence rating task is in ``Dataset_Generation_scr``. 
The dataset is taken from the [github repo](https://github.com/datienguyen/cnn_coherence/) of [Nguyen et al. 2017](https://www.aclweb.org/anthology/P17-1121.pdf). 
You just need to create the vocabulary using the ``create_voc.py``. 

```bash
python creat_voc.py --from_ner True
```

# Experiments
