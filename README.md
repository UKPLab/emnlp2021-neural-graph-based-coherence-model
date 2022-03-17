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
You can run the following command to train our model, our parameter such as paths to datasts can be viewed in src/utils.py
```python

>>> python  experiments_unified.py \
                                     --experiment_path  $PROJECT/Experiments/WSJ/ours/ \
                                     --bilinear_dim 32 \
                                     --batch_size_train 1\
                                     --batch_size_test 1\
                                     --ELMo True
```         
## Evaluation
* You can run run the following command to test our model. We have prepared a trained model under the folder Experiments/ 
```python
>>> python  experiments_unified.py \
                                     --experiment_path  $PROJECT/Experiments/WSJ/ours/ \
                                     --bilinear_dim 32 \
                                     --batch_size_train 1\
                                     --batch_size_test 16\
                                     --ELMo True \
                                     --only_eval True \
                                     --model_name  $PROJECT/Experiments/WSJ/ours/2022_3_13_11_42/Epoch_3 
