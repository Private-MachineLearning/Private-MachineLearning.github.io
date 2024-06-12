---
layout: narrow
title: FAQ
---

# FAQ

## How are new models and methods added to the list?

This website is [open-source][source] and welcomes updates from the community. Please open an [issue][issues] using the "Submit Report" template or submit
a [pull request][pulls] with proposed changes.


## What is the structure of the tables for each dataset?

For each private dataset, we consider the following common scenarios:

1. **No Public Data:** Models in this category do not use any public data for pretraining.

2. **Public IN1K (ImageNet 1K):** This scenario explicitly considers models that are pretrained using the widely adopted ImageNet 1K as a backbone for various architectures.

3. **Public DC-2B:** This setting focuses on models pretrained on the DataComp-2B dataset, particularly notable due to its use in CLIP Vit models.

4. **Anything Goes:** This setting encompasses any form of pretraining that uses datasets not previously mentioned.

## Should everything be open-sourced?

Ideally, you should open-source everything, including public data, your code, and the weights. However, we understand that some data may be proprietary and therefore not publicly available, which could also limit the accessibility of the weights. In such cases, it is still recommended to make the code available. While there may be other valid reasons for not releasing certain components, the general expectation is to publish all of the above whenever possible. You can explain all circumstances in the notes of your pull request.

## Which datasets are considered?

Considering which datasets the community views as solved or still having room for improvement, 
as well as those in more privacy-sensitive domains, we currently include CIFAR-10, ImageNet, CheXpert, 
and EyePACS. If you would like to suggest a new dataset, please open an [issue][issues].

## Why only vision?

At present, we only document methods for differentially private image classification, 
as it is the most extensively researched area. Nonetheless, we welcome and encourage 
contributions in other machine learning domains, including but not limited to natural 
language processing. If you have novel ideas for other domains, please open an [issue][issues].

## What does  &epsilon; = 0 mean?

&epsilon; = 0 indicates zero-shot performance on the dataset, meaning no privacy was compromised on the private data, as the model was neither trained nor fine-tuned on it. Please note that in this case, the accountant is not applicable (N/A) since no privacy budget was actually consumed.

## Why do some models on the leaderboard only have a general label like 'CNN' or 'DNN'?

If the paper/code explicitly describes the model or mentions the exact architecture name, 
it is specified in the leaderboard. However, if the model is not a widely known architecture 
or it is not quite clear what architecture they have exactly used, a more general term like 'CNN' 
or 'DNN' is used.

## What does (Final Layer)/(Full) after the model name mean?

If only the last layer of the model is fine-tuned, (Final Layer) is used. 
If it is fully fine-tuned, (Full) is used.

## How is this website maintained?

This is a community-maintained website, open-source on [GitHub][source]. All
updates to the site are [auditable][commits], and all discussions related to
content are also publicly visible (as GitHub [issues][issues] / [pull
requests][pulls]).


## How is this different from the other existing resources on robust ML?

[paperswithcode][paperswithcode] is an open-source leaderboard that keeps track of
SOTA datasets and benchmarks. However, due to the specifics of DP settings, 
integrating results into a traditional non-private leaderboard isn't straightforward.
A DP ML leaderboard must consider various factors, including privacy parameters (&epsilon;, &delta;), 
the privacy accountant used, and the public datasets involved. Unlike the non-private setting, 
DP requires mathematical proof of its guarantees. A result could be invalid if there is a bug in the proof. 
This adds to the existing concerns about the reproducibility of results. 
Given the complexity and the high risk of errors in DP proofs, our leaderboard includes a verification system to ensure correctness.

[source]: https://github.com/Private-MachineLearning/Private-MachineLearning.github.io
[commits]: https://github.com/Private-MachineLearning/Private-MachineLearning.github.io/commits/main/

[issues]: https://github.com/Private-MachineLearning/Private-MachineLearning.github.io/issues
[pulls]: https://github.com/Private-MachineLearning/Private-MachineLearning.github.io/pulls

[paperswithcode]: https://paperswithcode.com/sota
