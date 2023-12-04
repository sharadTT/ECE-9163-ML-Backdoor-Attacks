# ECE-9163-ML-Backdoor-Attacks

## Introduction
BadNets or backdoored networks exhibit exceptional performance on clean training and validation sets but behave maliciously when exposed to specific training and validation samples designed by an attacker. In this task, we employ a pruning defense technique on a model that has been intentionally trained with malicious intent. The pruning focuses on eliminating nodes that activate only when malicious data is input into the network.

## Methodology
The primary concept involves trimming the neural network and assessing its performance in contrast to the original network to identify any irregularities induced by the presence of a backdoor. It's worth noting that backdoors activate dormant or spare neurons within the network. The pruning defense strategy unfolds as follows: the defender applies the received Deep Neural Network (DNN) from the attacker to clean inputs sourced from the validation dataset, denoted as Dvalid, capturing the average activation levels of each neuron. Subsequently, the defender systematically prunes neurons from the DNN, prioritizing those with increasing average activations, while documenting the accuracy of the pruned network at each step. The defense procedure concludes when the accuracy of the validation dataset falls below a predefined threshold. Specifically, the pruning targets neurons in the 'pool_3' layer, situated before the `FC` layers. The method employed for pruning involves weights pruning, wherein the pruning action entails setting the weights and bias of the respective channel to 0.

## Observations
As per the instructions it is required to save the model when the accuracy falls below specified thresholds of X% (2%, 4%, and 10%). The corresponding saved models for these accuracy thresholds are denoted as model_X=2.h5, model_X=4.h5, and model_X=10.h5 respectively.
The graph clearly illustrates the model's accuracies on clean data and its attack success rates on malicious data. It visually represents the accuracy of clean test data and the attack success rate on backdoored test data, showcasing how these metrics vary with the fraction of channels pruned (X).
<img width="425" alt="1" src="https://github.com/sharadTT/ECE-9163-ML-Backdoor-Attacks/assets/36073410/2780e7a5-0917-4240-9ed9-204683c4c2aa">

Clean data accuracies and attack success rates versus the degree of pruning can be visualized in this graph.
<img width="637" alt="2" src="https://github.com/sharadTT/ECE-9163-ML-Backdoor-Attacks/assets/36073410/ff42f86d-da8e-491f-bdc0-00f3d045c443">

The combined pruned model and BadNet B created a GoodNet G. The results of the combination of the same data are as follows:
<img width="617" alt="3" src="https://github.com/sharadTT/ECE-9163-ML-Backdoor-Attacks/assets/36073410/c86c9eed-357f-42f8-9775-5c8388f2fc37">

## Installation
Download the dataset and model from this [link](https://github.com/csaw-hackml/CSAW-HackML-2020/tree/master/lab3)

Save the dataset in the source folder like this
<img width="101" alt="image" src="https://github.com/sharadTT/ECE-9163-ML-Backdoor-Attacks/assets/36073410/f4a7d4ed-ef9f-49bf-a0e9-53b1acc69865">

Hit Run All on ML_Lab4_st4870.ipynb file
