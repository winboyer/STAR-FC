# STAR-FC #
This code is the implementation for the CVPR 2021 paper "Structure-Aware Face Clustering on a Large-Scale Graph with 10^7 Nodes":star2::star2:. 

## :checkered_flag:News ##

An extended version is proposed for ultra-large-scale face clustering with hierarchical GCN training, whcih boosts the face clustering performance greatly!

The training and Inference processes are as following:



## :mortar_board:Requirements ##

 - Python = 3.6 
 - Pytorch = 1.2.0
 - faiss

## :fairy:Hardware ##

The hardware we used in this work is as follows:

- 24G TITAN RTX
- 48 core Intel Xeon CPU E5-2650-v4@2.20GHz processor

## :cake:Datasets ##

    cd STAR-FC

Create a new folder for training data:

    mkdir data

To run the code, please download the refined MS1M dataset and partition it into 10 splits, then construct the data directory as follows:

    |——data
       |——features
          |——part0_train.bin
          |——part1_test.bin
          |——...
          |——part9_test.bin
       |——labels
          |——part0_train.meta
          |——part1_test.meta
          |——...
          |——part9_test.meta
       |——knns
          |——part0_train/faiss_k_80.npz
          |——part1_test/faiss_k_80.npz
          |——...
          |——part9_test/faiss_k_80.npz
 We have used the data from: [https://github.com/yl-1993/learn-to-cluster](https://github.com/yl-1993/learn-to-cluster)

## :candy:Model ##

Put the pretrained models `Backbone.pth` and `Head.pth` in the `./pretrained_model`.
Our trained models will come soon. Recently, some people ask for the pretrained model. I have't sorted out these models carefully (Maybe early June). However, to help research, I will release a model and you can found it in this link: [https://cloud.tsinghua.edu.cn/d/cbd04a98b7d148dbae9e/](https://cloud.tsinghua.edu.cn/d/cbd04a98b7d148dbae9e/), the password is: STAR-FC_CVPR.

## :shamrock:Training ##

Adjust the configuration in `./src/configs/cfg_gcn_ms1m.py`, then run the algorithm as follows:

    cd STAR-FC
    sh scripts/train_gcn_ms1m.sh


## :cactus:Testing ##

Adjust the configuration in `./src/configs/cfg_gcn_ms1m.py`, then run the algorithm as follows:

    cd STAR-FC
    python test_final.py


## Acknowledgement ##
This code is based on the publicly available face clustering codebase [https://github.com/yl-1993/learn-to-cluster](https://github.com/yl-1993/learn-to-cluster).


## Citation ##
Please cite the following paper if you use this repository in your reseach.

```
@inproceedings{shen2021starfc,
   author={Shen, Shuai and Li, Wanhua and Zhu, Zheng and Huang, Guan and Du, Dalong and Lu, Jiwen and Zhou, Jie},
   title={Structure-Aware Face Clustering on a Large-Scale Graph with 10^7 Nodes},
   booktitle={Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition},
   year={2021}
}
```
