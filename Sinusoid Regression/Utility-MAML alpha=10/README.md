# Utility-MAML, alpha=10
This repository contains the code used to run the few-shot sinusoid regression. We borrowed code from two separate, prior implementations of MAML: for sinusoid regression, we used the Tensorflow [code](https://github.com/cbfinn/maml) from the [original MAML paper](https://arxiv.org/pdf/1703.03400.pdf), and TRMAML [code](https://github.com/lgcollins/tr-maml) from [TRMAML paper](https://arxiv.org/pdf/2002.04766.pdf)

## Sinusoid Regression

The contents of the "sinusoid" folder are for the sinusoid regression experiments. All requirements can be downloaded and installed by following the instructions in README.md in the original MAML repository. Depending on your version of Tensorflow, you may have to change "import tensorflow.compat.v1 as tf" to "import tensorflow as tf" in main.py and maml.py. 
The sinusoid regression experiments use synthetic data, so no dataset is required.
Our code runs exactly as the TRMAML code and original MAML:
 - TR_MAML : boolean value indicating whether to use TR_MAML (True) or MAML (False) (default: False)
 - p_lr : float specifying the learning rate for p (default: 0.0001)
 
These hyperparameter are specified as flags in the bash command used to run the experiment. To run any experiment, navigate to the "sinusoid" directory and make sure all requirements are installed. Then issue one of the following commands:

### To train Utility-MAML alpha=10: 
#### 5-shot sinusoid MAML train:
python main.py --datasource=sinusoid --logdir=logs/sine/ --log_number=60 --TR_MAML=False --metatrain_iterations=70000 --norm=None --update_batch_size=5 --train=True --resume=False

### To test Utility-MAML alpha=10: 
### 5-shot sinusoid MAML test:
python main.py --datasource=sinusoid --logdir=logs/sine/ --log_number=60 --TR_MAML=False --metatrain_iterations=70000 --norm=None --update_batch_size=5 --train=False --resume=False
