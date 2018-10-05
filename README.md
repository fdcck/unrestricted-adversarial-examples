# Unrestricted Adversarial Examples Challenge [![Build Status](https://travis-ci.org/google/unrestricted-adversarial-examples.svg?branch=master)](https://travis-ci.org/google/unrestricted-adversarial-examples)

In the Unrestricted Adversarial Examples Challenge, attackers submit arbitrary adversarial inputs, and defenders are expected to assign low confidence to difficult inputs while retaining high confidence and accuracy on a clean, unambiguous test set. You can learn more about the motivation and structure of the contest in [our recent paper](https://drive.google.com/open?id=1T0yiu9LPv_Qh-qYhYFLj9dxjnkca8fkG)

This repository contains code for [the warm-up to the challenge](warmup.md), as well as [the public proposal for the contest](contest_proposal.md). We are currently accepting defenses for the warm-up. 

![image](https://user-images.githubusercontent.com/306655/44686400-f0b74800-aa02-11e8-8967-fa354244813f.png)


### <a name="leaderboard"></a>Leaderboard for the warm-up to the contest
We include three attacks in [the warm-up to the contest](warmup.md):

- 1000 Linfinity-ball adversarial examples generated by [SPSA](https://arxiv.org/pdf/1802.05666.pdf)
- 1000 spatial adversarial examples [(via grid search)](https://arxiv.org/abs/1712.02779)
- 100 L2-ball adversarial examples generated by the [Boundary attack](https://arxiv.org/abs/1712.04248)

The top few distinct models for each dataset are shown below.  You can see all submissions in [the full scoreboard](scoreboard.md). 

#### Two-Class MNIST dataset
| Defense               | Submitted by  | Clean data | Spatial grid attack | SPSA attack | Boundary attack |  Submission Date |
| --------------------- | ------------- | ------------ |------------ |--------------- |--------------- | --------------- |
| [MadryPGD LeNet Baseline](unrestricted-advex/unrestricted_advex/mnist_baselines)  |  Google Brain |    100.0%    |      0%    |     19.6%   |     0%     |  Sept 14th, 2018 |
| [Undefended LeNet Baseline](unrestricted-advex/unrestricted_advex/mnist_baselines)   |  Google Brain   |    100.0%    |     0%    |     0%    |     0%     |  Sept 14th, 2018 |

All percentages above correspond to the model's accuracy at 80% coverage.

#### Bird or Bicycle dataset
| Defense               | Submitted by  | Clean data | Common corruptions | Spatial grid attack | SPSA attack | Boundary attack |  Submission Date |
| --------------------- | ------------- | ------------| ------------ |--------------- |--------------- | --------------- |
| [Keras ResNet <br>(trained on ImageNet)](examples/undefended_keras_resnet)   |  Google Brain   |    100.0%    |    99.2%    |     96.5%    |     1.6%    |     4.0%     |  Sept 29th, 2018 |
| [Pytorch ResNet <br>(trained on bird-or-bicycle extras)](examples/undefended_pytorch_resnet)  |  Google Brain |    98.8%    |   74.6%    |     29.1%   | 2.5%   |     8.0%     |  Oct 1st, 2018 |


All percentages above correspond to the model's accuracy at 80% coverage.


### Submitting a defense for the warm-up

The [warm-up before the contest](warmup.md) is currently underway and is accepting submissions. If you have additional questions, feel free to [submit a new GitHub issue](https://github.com/google/unrestricted-adversarial-examples/issues/new) with the "question" tag and we will respond shortly.

## The contest

The contest phase will begin after the warm-up attacks have been conclusively solved. We have published the [contest proposal](https://github.com/google/unrestricted-adversarial-examples/blob/master/contest_proposal.md) and are soliciting feedback from the community.


## Paper
You can learn more about the motivation and structure of the contest in our [recent paper](https://arxiv.org/abs/1809.08352):

**Unrestricted Adversarial Examples**<br>
*Tom B. Brown, Nicholas Carlini, Chiyuan Zhang, Catherine Olsson, Paul Christiano and Ian Goodfellow*<br>
[Arxiv preprint](https://arxiv.org/abs/1809.08352)

```
@article{unrestricted_advex_2018,
  title = {Unrestricted Adversarial Examples},
  author = {{Brown}, T.~B. and {Carlini}, N. and {Zhang}, C. and {Olsson}, C. and 
	  {Christiano}, P. and {Goodfellow}, I.},
  journal={arXiv preprint arXiv:1809.08352},
  year={2018}
}
```
