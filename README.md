# UTel

## Introduction

**Knowing Where and What: Unified Word Block Pretraining for Document Understanding**<br> 

Our codes is based on [BROS](https://github.com/clovaai/bros).

## Pre-trained models

| name               | # params | Hugging Face - Models                                                                           |
|--------------------|---------:|-------------------------------------------------------------------------------------------------|
| bros-base-uncased  |   < 110M | [naver-clova-ocr/bros-base-uncased](https://huggingface.co/naver-clova-ocr/bros-base-uncased)   |
| bros-large-uncased |   < 340M | [naver-clova-ocr/bros-large-uncased](https://huggingface.co/naver-clova-ocr/bros-large-uncased) |


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
