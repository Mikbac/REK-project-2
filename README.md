# REK - Project 2

## Table of contents
* [Project description](#project-description)
* [Installing](#installing)
* [Requirements](#requirements)
* [Scores](#scores)

## Project description
Recommender for the hotel reservation. The goal was to achieve the best HR@10 in the final evaluation.

Final solution uses:
* GMFModel
* Updated filter ```filter_out_long_stays``` to ```<= 14```

HTML versions of jupyter notebook are in ```html``` catalog.

## Installing
Linux or Mac (in project catalog):
```
conda create --name rekProjectTwo --file requirements.txt python=3.6
source activate rekProjectTwo
```

Windows (in project catalog):
```
conda create --name rekProjectTwo --file requirements.txt python=3.6 
conda install -c anaconda pywin32
activate rekProjectTwo
```

In project catalog:
```
jupyter notebook
```

Notebooks run in the following order: 
1. ```project_1_data_preparation.ipynb```
2. ```project_2_recommender_and_evaluation.ipynb```

In  ```project_2_recommender_and_evaluation.ipynb``` run all cells except second, third, and fourth tuning.

## Requirements

Details for anaconda are in ```requirements.txt```.

## Scores

| Model             | Score HR@10   | params                                                                                               |
| ---               | ---           | ---                                                                                                  |
| GMFModel          | 0.203805       | n_epochs=20, n_neg_per_pos=10, batch_size=16, embedding_dim=6, lr=0.001, weight_decay=0.0001, seed=1 |
| GMFModel          | 0.201785       | n_epochs=20, n_neg_per_pos=7, batch_size=64, embedding_dim=6, lr=0.01, weight_decay=0.001, seed=1 |
| GMFModel          | 0.204023      | n_epochs=3, n_neg_per_pos=10, batch_size=64, embedding_dim=12, lr=0.001, weight_decay=0.0001, seed=1 |
| GMFModel          | 0.206481      | n_epochs=20, n_neg_per_pos=10, batch_size=16, embedding_dim=6, lr=0.001, weight_decay=0.0001, seed=1, validation_set_size=0.3 |
| GMFModel          | 0.208081      | n_epochs=20, n_neg_per_pos=10, batch_size=16, embedding_dim=4, lr=0.001, weight_decay=0.0001, seed=1 |
| GMFModel          | 0.200673      | n_epochs=60, n_neg_per_pos=10, batch_size=16, embedding_dim=8, lr=0.001, weight_decay=0.0001, seed=1 |
| MLPModel          | 0.212795      | n_epochs=25, n_neg_per_pos=10, batch_size=16, embedding_dim=6, lr=0.001, weight_decay=0.0001, seed=1 |
| MLPModel          | 0.211785      | n_epochs=15, n_neg_per_pos=10, batch_size=16, embedding_dim=6, lr=0.001, weight_decay=0.0001, seed=1 |
| MLPModel          | 0.209091      | n_epochs=50, n_neg_per_pos=10, batch_size=16, embedding_dim=6, lr=0.001, weight_decay=0.0001, seed=1 |
| MLPModel          | 0.218182      | n_epochs=14, n_neg_per_pos=4, batch_size=16, embedding_dim=6, lr=0.001, weight_decay=0.0001, seed=1 |
