# ncta2022

Repository for the paper [Deep learning of structural changes in historical buildings: the case study of the Pisa tower]()

## Installation

Clone this repository

```
git clone https://github.com/galatolofederico/ncta2022.git
cd ncta2022
```

Create a virtualenv and install the requirements

```
virtualenv --python=python3.8 env
. ./env/bin/activate
pip install -r requirements.txt
```

If you are interested in the dataset please [contact us](mailto:federico.galatolo@ing.unipi.it)

## Usage

### To train a model run

```
python train.py train.save_model=<save_path> dataset=<dataset> train.wandb=<true/false> wandb.tag=<tag> architecture=<architecture>
```
Where
 - dataset can be: `post` `prepost` or `full`
 - architecture can be: `LSTMRegressor` `VectorAutoRegressor` or `TransformerRegressor`

This script will save the trained model in `<save_path>`

### To run the inference with a model run

```
python predict.py predict.model=<path-to-checkpoint> predict.split=<split> dataset=<dataset> architecture=<architecture>
```
Where
 - predict.split can be: `train` `validation` `test` or `post` (`post` is available only using the `prepost` dataset)
 - dataset can be: `post` `prepost` or `full`
 - architecture can be: `LSTMRegressor` `VectorAutoRegressor` or `TransformerRegressor`

This script will save the outputs and the plots in the folder `./plots`

### To compute the performance metrics run

```
python evaluate.py evaluate.model=<path-to-checkpoint> evaluate.split=<split> dataset=<dataset> architecture=<architecture>
```
Where
 - evaluate.split can be: `train` `validation` `test` or `post` (`post` is available only using the `prepost` dataset)
 - dataset can be: `post` `prepost` or `full`
 - architecture can be: `LSTMRegressor` `VectorAutoRegressor` or `TransformerRegressor`

This script will save the results in the folder `./results`

## Scripts

To train all the models from the paper run

```
./train_all.sh
```

To run the inference with the trained models run

```
./predict_all.sh
```

To compute the performance metrics for all the models run

```
./evaluate_all.sh
```

## Contributions and license

The code is released as Free Software under the [GNU/GPLv3](https://choosealicense.com/licenses/gpl-3.0/) license. Copying, adapting and republishing it is not only allowed but also encouraged. 

For any further question feel free to reach me at  [federico.galatolo@ing.unipi.it](mailto:federico.galatolo@ing.unipi.it) or on Telegram  [@galatolo](https://t.me/galatolo)