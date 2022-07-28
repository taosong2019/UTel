# UTel

## Introduction

**Knowing Where and What: Unified Word Block Pretraining for Document Understanding**<br> 

Our code is based on [BROS](https://github.com/clovaai/bros).

## Pre-trained models

| name               | # params                                                    |
|---------:|-------------------------------------------------------------------------------------------------|
| [utel-base-uncased](https://drive.google.com/drive/folders/1gODxg4pkJJJgTt5RIHyfhZU2ofnPxDSa?usp=sharing)  |    110M | 
| [utel-large-uncased](https://drive.google.com/drive/folders/1U4Vmpdj0C1pTZO1SH8p8oyrT7aP376Eo?usp=sharing) |    340M | 

## Fine-tuning on FUNSD

##### Prepare data

We conducted the FUNSD EE experiment based on the FUNSD data preprocessed in LayoutLM.
Original code can be found in [this link](https://github.com/microsoft/unilm/tree/master/layoutlm/deprecated/examples/seq_labeling).
To run it, please follow the steps below:

1) move to `preprocess/funsd/`.
2) run `bash preprocess.sh`.
3) run `preprocess_2nd.py`. This scripts converts the preprocessed data in LayoutLM to fit this repo.
 
Data will be created in `datasets/funsd/`.

##### Perform fine-tuning

Run the command below:
```
CUDA_VISIBLE_DEVICES=0 python train.py --config=configs/finetune_funsd_ee_bies.yaml
```
