# DAU
This is the code of the paper "Backdoor Defense via Decoupled Adversarial Unlearning".

## **Abstract:** *Abstract:

Extensive studies have demonstrated that deep neural networks (DNNs) are vulnerable to backdoor attacks in the training phase. In this paper, we introduce a novel training-time defense method, dubbed Decoupled Adversarial Unlearning (DAU), which consists of two
main stages: decoupled adversarial learning and backdoor unlearning. In the first stage, we first decouple DNN into a feature extractor and a classifier. Inspired by the training paradigm of the discriminator in Generative Adversarial Network, we retrain the classifier based on a small pre-filtered poisoned set while keeping the feature extractor fixed to create a poisoned sample discriminator. Subsequently, the compromised training dataset can be precisely split into the poisoned set and the clean set based on the poisoned sample discriminator. In the second stage, we propose an effective backdoor unlearning method based on complementary cross-entropy, a new concept we introduce, and conduct a theoretical analysis of its advantages and limitations compared with the widely used global gradient ascent method. Furthermore, we enhance our DAU to achieve the removal of backdoors with minimal impact on model performance for clean tasks, even in practical scenarios with poor filtering performance, where the filtered poisoned set and clean set are mixed with a certain amount of each other’s samples. Extensive experiments on multiple benchmark datasets with different levels of classification difficulty against representative backdoor attacks validate the effectiveness and universality of our proposed methods.

## Requirements

- Python >= 3.9
- PyTorch >= 2.5

## Setup Environment and Install Dependencies

### Conda 

Please follow the instructions at the following link to set up anaconda: [Anaconda Setup](https://docs.anaconda.com/anaconda/install/index.html)
The following commands create a conda environment inside the repository with the dependencies.

```bash
conda env create -f environment.yml
source activate ./env
```

## Usage

### anti_learning

```
python test_DAU.py --subtask "anti_learning" --dataset "CIFAR-10" --attack "BadNets"

```

### unlearning

```
python test_DAU.py --subtask "unlearning"  --dataset "CIFAR-10"  --attack "BadNets"

```

### test

```
 python test_DAU.py --subtask "test"  --dataset "CIFAR-10"  --attack "BadNets"

```

