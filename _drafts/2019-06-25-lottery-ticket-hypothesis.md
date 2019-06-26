---
layout: post
title: Lottery Ticket Hypothesis
tags: [Deep Learning, Pruning, Model Compression, SOTA, Tutorial]
excerpt_separator: <!--more-->
---

<!--more-->

Lottery Ticket Hypothesis

So I looked into this paper when I saw this [MIT article](https://www.technologyreview.com/s/613514/a-new-way-to-build-tiny-neural-networks-could-create-powerful-ai-on-your-phone/)

After reading the gist of the article, I started looking into the paper.

The purpose of this post is to give you a quick summary and overview of how this algorithm works and perform it in tensorflow.

Pruning is a technique to reduce the number of parameters in a neural network. 

Reducing the number of parameters in a network reduces the size of the network, because now the network has zeroes or non connections

This is done by simply setting the value of a weight to 0.0. This produces weight matricies that contain 0's.

This technique produces matricies called sparse matricies.

What does this paper contributes to the state of the art of pruning?

So when we originally start pruning our networks in practice. 

We start with the pretrained model, that was trained for hours and days, and we prune the weights and find that we have a large amount of sparsity in the network.

This paper asks the question can we just start with a network from scratch and then train a neural network that matches the accuracy of the pruned network?

This paper integrates the pruning in the training step, allowing for quicker training because of the pruned weights produce and a pruned network as the output.


The Lottery Ticket Hypothesis. A randomly-initialized, dense neural network contains a subnetwork that is initialized such that—when trained in isolation—it can match the test accuracy of the
original network after training for at most the same number of iterations.

Identifiying winning tickets


Randomly initialize a neural network try using xavier initialization
train the network for j iterations, arriving at parameters oj

prine p% of the parametsers in the result oj create a mask m of 1 and 0s 

reset the remaining parameters to their values in oo

this is the basic algorithm

but we do this over n rounds each round prune p^1/n


How can we try this out in Tensorflow



