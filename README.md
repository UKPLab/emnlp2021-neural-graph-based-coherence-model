# A Neural Graph-based Local Coherence Model

Data and code for our paper

```
@inproceedings{mesgar2021neural,
  title={A Neural Graph-based Local Coherence Model},
  author={Mesgar, Mohsen and Ribeiro, Leonardo FR and Gurevych, Iryna},
  booktitle={Findings of the Association for Computational Linguistics: EMNLP 2021},
  pages={2316--2321},
  year={2021}
}
```
## Getting Started
* Install necessary dependencies listed in requirements.txt. Please note that if you fail to install torch-* (e.g. torch-scatter), run the following command
```python
 >>> pip install torch-scatter==2.0.5 torch-sparse==0.6.7 torch-cluster==1.5.7 torch-spline-conv==1.2.0 torch-geometric==1.6.1  -f https://pytorch-geometric.com/whl/torch-1.6.0+cu101.html

``` 
- Download GoogleNews-vectors-negative300.bin from https://s3.amazonaws.com/dl4j-distribution/GoogleNews-vectors-negative300.bin.gz

## Dataset
*  Regard to WSJ license, we can't upload the raw data. All python files relating to data processing (e.g. generating vocab, paired samples) are under the folder data/Dataset_Global.

## Training
* All default parameters including paths to the dataset are list in src/utils.py 
* You can run our_elmo.sh after modifying the parameters to train our models

## Evaluation
* You can run our_elmo_eval.sh to test our model. We have prepared a trained model under the folder Experiments/ 
