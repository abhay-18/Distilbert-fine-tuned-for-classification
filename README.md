# Distilbert-fine-tuned-for-classification

This repo containes the finetuned distilbert for sequence classification. Dataset consists of movie reviews which is to be classified into positive or negative.

LoRA (Low Rank Adaptation) method was used to fine tune the base-model.

Accuracy increases from 48% (Base model) to 90% (Finetuned model) after fine-tuning.

LoRA configuration - 
```
task_type="SEQ_CLS", # sequence classification
r=4, # intrinsic rank of trainable weight matrix
lora_alpha=32, # this is like a learning rate
lora_dropout=0.01, # probablity of dropout
target_modules = ['q_lin']  # we apply lora to query layer only

```
More details about LoRA - [here](https://arxiv.org/pdf/2106.09685.pdf)

## Framework versions
- Transformers 4.32.1
- Pytorch 2.0.1
- Datasets 2.14.4
- Tokenizers 0.13.2
