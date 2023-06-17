
# Implementing a VAE in SocialGNN


This project is based on this paper "Relational Visual Information explains Human Social Inference: A Graph Neural Network model for Social Interaction Recognition". [Link to Preprint](https://psyarxiv.com/5cuyr)

This repository contains code to train and test the SocialGNN models with the original PHASE input and the VAE-processed input.


## Conda Environment / Prerequisites
conda env create -f Conda Environments/condaenv_macbook_gnnEnv_Oct17_2022.yml

## How to Run the Code?

#### Generating PHASE standard set from VAE
Run generate_vae_video.ipynb
You can find the output videos in PHASE/vae_videos.pickle.

#### Running SocialGNN on the PHASE standard set

###### Training (with bootstrapped train-test splits) SocialGNN 
  ```
  python traintest_bootstrapsplits_PHASE_mainset.py --model_name="SocialGNN_V" --context_info=True
  ```
Results are saved in the PHASE/TrainedModels. We generated models with folder names PHASE_mysplit_humanratings_contextTrue_20230531_x_SocialGNN_V_4_4_12_12_6_3_20_1.0_2.0_1.0_0.001_0.05, with x from 0 to 9.

The code is now train on the van-generated dataset. To train on the original PHASE data set, in traintest_bootstrapsplits_PHASE_mainset.py, comment out line 25-26 and uncomment line 23-24. 

###### Getting Accuracy and Predicted Labels using Trained Models
  ```
  python get_accuracy_predictions_PHASE_mainset.py --model_name="SocialGNN_V" --bootstrap_no=0 --context_info=True
  ```