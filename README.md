# tf-char-cnn-lstm
A Tensorflow version of Yoon Kim's char-cnn-lstm [Torch7 code](https://github.com/yoonkim/lstm-char-cnn)

It is a boosting and amended version of [mkroutikov's work](https://github.com/mkroutikov/tf-lstm-char-cnn),to fix some mistakes and improve the speed. The structure of the whole model is the same.Now the training time is within 4 hours on large model, much faster than the original 20+ hours.And we can get slightly better result at the same time.

A simplified and neaty version called **models.py** is also provided for beginners,aimed to make the whole process easy to understand.It is identical to the model.py, but in a straight-forward style, inspired by [sherjilozair](https://github.com/sherjilozair/char-rnn-tensorflow)

## requirement

Tensorflow 0.10
cuda and cudnn should be installed for gpu implement

## usage
 - Train:
```sh
python train_gpu.py
or
python train_sim.py
```
train_sim.py uses the models.py,which produces the same result

 - Evaluate
```sh
python evaluate_gpu.py
```
### for CPU:
 - Train：
```sh
python train_gpu.py --gpuid -1
```
 - Evaluate:
```sh
python evaluate_gpu.py --gpuid -1
```
Large model of Yoon Kim's paper will be trained on PTB and also evaluated.Log will be printed to screen just like the log in repo.

## Time
The training time the large model is about 3.5~3.8 hour on a GPU(k20) with 0.4sec/batch, while the lua code of Yoon Kim is about 5 hours on a GPU.

![img](https://raw.githubusercontent.com/hejunqing/tf-char-cnn-lstm/master/train_loss_0.5.png)


## Previous Results
| Learning rate  |  Train/Valid/Test loss  |  Train/Valid/Test perplexity  |
|:--------------:|:-----------------------:|:------------------------------|
| 1.0            | 4.057 / 4.503 / 4.463   | 57.77 / 90.25 / 86.79         |
| 0.5            | 3.984 / 4.432 / 4.391   | 53.71 / 84.06 / **80.73**     |

**Now the results of models trained on new codes should be identical to Yoon Kim's, as listed in [mkroutikov's work](https://github.com/mkroutikov/tf-lstm-char-cnn)**








