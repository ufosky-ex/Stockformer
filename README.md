# StockFormer Data File Explanation and Execution Method

## Overview of "StockFormer" Code
This is the code accompanying the paper titled "StockFormer: A Swing Trading Strategy Based on STL Decomposition and Self-Attention Networks," which is currently under consideration for publication in the International Journal of Forecasting. The code provides a comprehensive framework for implementing the StockFormer model, including data preparation, model training, and backtesting.

## Original Data
Due to the large size of the original data, the author has stored it on a cloud drive for readers to use. The link to the original data is as follows: [raw_data](https://drive.google.com/drive/folders/1V-qq2NtCV0T4ULgYLI05Ev8g5ntoC3io?usp=sharing)

## File Description
- `data_cleaned.ipynb`: Data cleaning for raw data.
- `Stockformermodel`
  - The neural network architecture of Stockformer.

- `data/STOCK`
  - `corr_adj.npy`: The correlation matrix for input data (used for generating high-dimensional vector expressions with Struc2vec; see [struc2vec](https://github.com/shenweichen/GraphEmbedding/blob/master/examples/struc2vec_flight.py) for the generation method).
  - `corr_struc2vec_adjgat.npy`: High-dimensional vectors generated by Struc2vec, ready for direct network input.
  - `flow.npz`: The processed real input data.

- `log/STOCK`
  - `logV4`: Log files output by the neural network.

- `lib`
  - `smallStockutils.py`: Preprocessing for Stockformer input data and establishment of evaluation metrics.

- `output`: Folder for output result files.
- `config`: Configuration files for the network.
- `cpt/STOCK`
  - `saved_modelV4_2`: Saved trained neural network models.

- `Stockformer_train.py`: The model training file.
- `backtest`
  - `my_us_backtest.ipynb`: Code used for backtesting stock returns.
  - `us_data_21-23`: The dataset constructed for backtesting based on [qlib](https://github.com/microsoft/qlib).
  - `baseline`: The state-of-the-art (SOTA) used for comparison with the models in this study.

## How to Run
Execute the following command in the terminal to run the model:

```sh
python Stockformer_train.py --config STOCKV4.conf
