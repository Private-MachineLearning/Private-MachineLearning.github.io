---
layout: narrow
title: FAQ
---

# FAQ

<!-- ## Which datasets are included? -->

<!-- Currently, we list defenses that are claimed to be secure in the white-box
model. Defenses that only aim to be secure in an oblivious attacker / black-box
/ grey-box model, but not in a white-box model, are out of scope. It is unclear
how to properly evaluate such defenses, as it is challenging to model lack of
awareness of a defense (or part of a defense) being in place. In the future, we
may expand to include more threat models.

Defenses must also have open-source code available, along with pre-trained
models. Public availability of defenses enables third parties to more easily
perform security analyses. In the absence of first-party implementations, we
accept third-party implementations. If a first-party implementation for a
listed defense becomes available, please [let us know][issues] (or submit a
[pull request][pulls] with the update).

Defenses must also implement the [robustml API][robustml]. Implementing the
interface requires minimal additional effort, and it enables straightforward
evaluation of attacks.

We maintain two lists: one for [published defenses][defenses] and one for
[unpublished defenses][preprints]. Both contain defenses for the white-box
threat model that are open-source, implement the robustml API, and have
pre-trained models available. -->

## What is the structure of the tables for each fine-tuning dataset?

For each private dataset, we consider the following very common scenarios:

1. **No Public Data:** Models in this category do not use any publicly available data for pretraining.

2. **Public IN1K (ImageNet 1K):** This scenario explicitly considers models that are pretrained using the widely adopted ImageNet 1K as a backbone for various architectures.

3. **Public DC-2B:** This setting focuses on models pretrained on the DataComp-2B dataset, particularly notable due to its use in prominent CLIP Vit models.

4. **Anything Goes:** This setting encompasses any form of pretraining that uses datasets not previously mentioned.

## Should everything be open-sourced?
 
Ideally, you should open-source everything, including public data, your code, and the weights. However, we understand that some data might be proprietary and therefore not publicly available, which would also restrict the availability of the weights. In such cases, it is still recommended to make the code available. There might be other valid reasons for not publicizing some components, but generally, it is expected to publish all the above.


<!-- ## How are new defenses added to the list?

Defenses must be open-sourced, implement the robustml API, and have a
pre-trained model available to be eligible to be added to the list. See
[here][instructions] for instructions. Please submit a [pull request][pulls] to
add a new defense to the list.

By default, we list a single claim from the paper (for the “largest” dataset).
Authors can list up to 3 claims, with a single claim allowed for a (dataset,
threat model) pair.

## Why is defense X missing?

The defense is either not open-sourced or no one has implemented the [robustML
API][robustml] yet. Since this is a community-run website we can't expect it to be 100%
complete. Maybe you can implement the defense and/or the API and add it to the list!

## How are analyses chosen?

We list all analyses that [implement the robustml attack interface][attack] to
attack the defense and respect the threat model of the paper. Because we
require both defenses and analyses to implement the robustml interfaces, they
can be easily [run][run] against each other.

## How are threat models chosen?

The threat models listed correspond to models [defined in the robustml
framework][threat models] and are based on models considered in published
papers. If you wish to add a new threat model, please open an [issue][issues].

## Which datasets are considered?

We include the datasets [defined in the robustml framework][datasets]
(currently MNIST, Fashion-MNIST, CIFAR-10, GTS, and ImageNet ILSVRC 2012). If
you wish to add a new dataset, please open an [issue][issues]. -->

## Why only vision? why only classification?

At present, we only document methods for differentially private image classification, 
as this is the most extensively researched area. Nonetheless, we welcome and encourage 
contributions in other machine learning domains, including but not limited to natural 
language processing. If you have novel ideas for other domains, please open an [issue][issues].

## How do I submit an update?

This website is [open-source][source]. Please open an [issue][issues] or submit
a [pull request][pulls] with proposed changes.

## What does  &epsilon; = 0 mean?
&epsilon; = 0 indicates zero-shot performance on the dataset, meaning no privacy was compromised on the private data, as the model was neither trained nor fine-tuned on it. Please note that in this case, the accountant is not applicable (N/A) since no privacy budget was actually consumed.

## Why do some models on the leaderboard only have a general label like 'CNN' or 'DNN'?
If the architecture is explicitly mentioned in the paper or code, it is specified in the leaderboard. However, note that while a name is listed, for full architectural details, one must refer to the related paper or code. If the model is not a widely known architecture, a more general term like 'CNN' or 'DNN' is used. This indicates that the architecture is a combination of layers described in the paper, or it is not mentioned at all.

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

<!--## How is this different from the other existing resources on robust ML?

[CleverHans][cleverhans] is a library providing open-source implementations of
various known attack methods. This is an important resource that provides us
with a broad set of tools useful in working on robust ML. However, the key goal
of robust-ml.org, reflecting the current progress on key datasets and threat
models, is not a part of CleverHans's focus.

[robust.vision][robust vision] maintains a comparison between existing defenses
by evaluating each one of them against all currently known attacks. This
provides a useful overview of the relative power of known attacks and defenses.
However, due to its focus on evaluating defenses only on known, static attacks,
it might not necessarily reflect the actual progress on the defense front.
After all, defenses often appear effective by resisting all previously known
attacks but can be completely bypassed by new, adaptive ones. -->

[source]: https://github.com/Private-MachineLearning/Private-MachineLearning.github.io
[commits]: https://github.com/Private-MachineLearning/Private-MachineLearning.github.io/commits/main/
<!-- [defenses]: /defenses/
[preprints]: /preprints/
[robustml]: https://github.com/robust-ml/robustml
[instructions]: https://github.com/robust-ml/robustml#usage -->
[issues]: https://github.com/Private-MachineLearning/Private-MachineLearning.github.io/issues
[pulls]: https://github.com/Private-MachineLearning/Private-MachineLearning.github.io/pulls
<!--[threat models]: https://github.com/robust-ml/robustml/blob/master/robustml/threat_model.py
[datasets]: https://github.com/robust-ml/robustml/blob/master/robustml/dataset.py
[attack]: https://github.com/robust-ml/robustml/blob/master/robustml/attack.py
[run]: https://github.com/robust-ml/robustml/blob/master/robustml/evaluate.py
[cleverhans]: https://github.com/tensorflow/cleverhans
[robust vision]: https://robust.vision/ -->
[paperswithcode]: https://paperswithcode.com/sota