# EMI-FGSM

This repository contains code to reproduce results from the paper:

[Boosting Adversarial Transferability with Enhanced Momentum](https://arxiv.org/abs/2103.10609) (BMVC 2021)

[Xiaosen Wang](https://xiaosen-wang.github.io/), Jiadong Lin, Han Hu, Jingdong Wang, Kun He

> We also include the torch version code in the framework [TransferAttack](https://github.com/Trustworthy-AI-Group/TransferAttack).

## REQUIREMENTS

- Python >= 3.6.5
- Tensorflow >= 1.12.0 
- Numpy >= 1.15.4 
- opencv >= 3.4.2
- scipy >= 1.1.0
- pandas >= 1.0.1
- imageio >= 2.6.1

## Qucik Start

### Preparing data and models

You should download the [data](https://drive.google.com/drive/folders/1CfobY6i8BfqfWPHL31FKFDipNjqWwAhS) and [pretrained models](https://drive.google.com/drive/folders/10cFNVEhLpCatwECA6SPB-2g0q5zZyfaw) and place the data and pretrained models in [dev_data/](dev_data) and [models/](models), respectively.


### EMI-FGSM

All the provided codes generate adversarial examples on inception_v3 model. If you want to attack other models, replace the model in `graph` and `batch_grad` function and load such models in `main` function.

#### Runing attack

Taking Admix attack for example, you can run this attack as following:

```
CUDA_VISIBLE_DEVICES=gpuid python epi_fgsm.py 
```

#### Evaluating the attack

The generated adversarial examples would be stored in directory `./outputs`. Then run the file `simple_eval.py` to evaluate the success rate of each model used in the paper:

```
CUDA_VISIBLE_DEVICES=gpuid python simple_eval.py
```

## Acknowledgments

Code refers to [SI-NI-FGSM](https://github.com/JHL-HUST/SI-NI-FGSM).

## Contact

Questions and suggestions can be sent to xswanghuster@gmail.com.
