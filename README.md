# Improving Low-Resource Question Answering with Cross-Lingual Data Augmentation Strategies

This repo is forked form [indonlu-repo](https://github.com/indobenchmark/indonlu) with several adjusment and addition. This repo is implementation of "Improving Low-Resource Question Answering with Cross-Lingual Data Augmentation Strategies" paper (accepted on ICOICT 2022) ([paper](https://ieeexplore.ieee.org/document/9914847)).




### Requirement
Check on [requirment_file](https://github.com/ryanpram/2step_finetuning_xlda/blob/master/requirements.txt)

### Reproduce Step

* Clone This Repo
* Run Training Script
```
CUDA_VISIBLE_DEVICES=6 \
python3 main.py \
      --n_epochs=25 \
      --train_batch_size=8 \
      --model_checkpoint=xlm-roberta-base \
      --step_size=1 \
      --gamma=0.9 \
      --device=cuda \
      --experiment_name=xlm-roberta-base-2step-indo-dataset-e3 \
      --lr=1e-5 \
      --early_stop=12 \
      --dataset=qa-factoid-itb \
      --lower \
      --num_layers=12 \
      --max_norm=10 \
      --seed=42 \
      --data_type=original \
      --force
```
* Or you can test your own model with eval_only

```
CUDA_VISIBLE_DEVICES=6 \
python3 main.py \
      --n_epochs=25 \
      --train_batch_size=8 \
      --model_checkpoint=./save/qa-factoid-itb/xlm-roberta-base-english-only-dataset-e3/xlm-roberta-pretrained \
      --step_size=1 \
      --gamma=0.9 \
      --device=cuda \
      --experiment_name=xlm-roberta-base-2step-indo-dataset-e3 \
      --lr=1e-5 \
      --early_stop=12 \
      --dataset=qa-factoid-itb \
      --lower \
      --num_layers=12 \
      --max_norm=10 \
      --seed=42 \
      --data_type=original \
      --eval_only \
      --force
```



## Help

You can submit a GitHub issue for asking a question or help. Or you can contact me directly at ryan.pramana@ui.ac.id as well

