# Deep Session Interest Network for Click-Through Rate Prediction

Experiment code on Advertising Dataset of paper Deep Session Interest Network for Click-Through Rate Prediction(https://arxiv.org/abs/1905.06482)  

Yufei Feng , Fuyu Lv, Weichen Shen and Menghan Wang and Fei Sun and Yu Zhu and Keping Yang.  

In Proceedings of 28th International Joint Conference on Artificial Intelligence (IJCAI 2019)

----------------
## Operating environment
- python==3.6
- tensorflow-gpu==1.4.0
- deepctr==0.4.1
- numpy==1.15.1
- pandas==0.22.0
- scikit-learn==0.19.2
- tqdm==4.19.5

--------------------------
## Download dataset and preprocess
### Download dataset

1. Download Dataset [Ad Display/Click Data on Taobao.com](https://tianchi.aliyun.com/dataset/dataDetail?dataId=56)
2. Extract the files into the ``raw_data`` directory
   
### Data preprocessing

1. run  `0_gen_sampled_data.py`,
sample the data by user
2. run `1_gen_sessions.py`,
generate historical session sequence for each user

## Training and Evaluation

### Train DIN model
1. run `2_gen_din_input.py`,generate input data
2. run `train_din.py`

### Train DIEN model
1. run `2_gen_dien_input.py`,generate input data(It may take a long time to sample negative samples.)
2. run `train_dien.py`

### Train DSIN model
1. run `2_gen_dsin_input.py`,generate input data
2. run `train_dsin.py`
   > The loss of DSIN with `bias_encoding=True` may be NaN sometimes on Advertising Dataset and it remains a confusing problem since it never occurs in the production environment.We will work on it and also appreciate your help.