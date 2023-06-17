<img src="icon.png" align="right" />

# SocialGNN: A Graph Neural Network model for Social Interaction Recognition 

<!--
[![Project Status: WIP – Initial development is in progress, but there has not yet been a stable, usable release suitable for the public.](https://www.repostatus.org/badges/latest/wip.svg)](https://www.repostatus.org/#wip) ![Progress](https://progress-bar.dev/85/?title=completed) -->

This project is described in our paper titled "Relational Visual Information explains Human Social Inference: A Graph Neural Network model for Social Interaction Recognition". [Link to Preprint](https://psyarxiv.com/5cuyr)

This repository contains code to train and test our SocialGNN models (as well as baseline VisualRNN models) on animated and natural stimuli.

P.S.: VisualRNN = CueBasedLSTM

## Conda Environment / Prerequisites
- For macOS: 
```Conda Environments/condaenv_macbook_gnnEnv_Oct17_2022.yml ```
- For Linux: _To Be Added_

## How to Run the Code?
Please refer to our paper for the terminology used here and for changes in parameter settings.

#### Running SocialGNN on the PHASE standard set (400 videos)

###### Getting Accuracy and Predicted Labels using Trained Models
  ```
  python get_accuracy_predictions_PHASE_mainset.py --model_name="SocialGNN_V" --bootstrap_no=0 --context_info=True
  ```
###### Training (with bootstrapped train-test splits) SocialGNN or VisualRNN/CueBasedLSTM models
  ```
  python traintest_bootstrapsplits_PHASE_mainset.py --model_name="SocialGNN_V" --context_info=True
  ```
#### Running SocialGNN on the PHASE generalization set (100 videos)
###### Getting Accuracy using Trained Models
  ```
  python traintest_PHASE_genset.py --mode=test --model_name=SocialGNN_E --context_info=True
  
  ```
###### Training SocialGNN or VisualRNN/CueBasedLSTM models
```
  python traintest_PHASE_genset.py --mode=train --model_name=SocialGNN_E --context_info=True
```


#### Running SocialGNN on the Gaze dataset
Set <prediction_type> to 2 for social v/s non-social classification; set to 5 for classifying into the 5 gaze labels
The first 10 bootstrpas correspond to "dataset=5Jun23", the next 10 to "dataset=14Jun23"

###### Getting Accuracy (on all bootstrapped train-test splits) using Trained Models
  ```
  python traintest_bootstrapsplits_Gaze.py test <model_to_test> <prediction_type> <dataset>
  
  Example:
  python traintest_bootstrapsplits_Gaze.py test CueBasedLSTM-Relation 5
  ```
###### Training SocialGNN or VisualRNN/CueBasedLSTM models
```
  python traintest_bootstrapsplits_Gaze.py train <model_to_train> <prediction_type> <dataset>
```
###### Training/Testing VGG19 model
```
python VGG19full_traintest_gaze.py --mode=test --dataset=5Jun23 --output_type=2
```

<!--- ## Repository Components --->

## To Be Added Soon
- Data Preprocessing files

## Citation
```
```

### For Issues: 👩‍💻 mmalik16@jhu.edu
