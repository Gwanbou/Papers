---
source: "https://arxiv.org/abs/2310.15149v1"
Code: NA
Organization: Nanjing University, Peking University
---

This article delves into addressing the issue of learned high-dimensional embeddings lacking semantic information in tabular deep models. The authors observe that "the learned tokens (embeddings) exhibit random behavior and lack discriminative properties". To remedy this, they utilize the semantic information provided by labels to understand feature relationships and optimize embeddings.

Specifically, the proposed solution is Contrastive Token Regularization (CTR) incorporated into the objective function. CTR aims to pull instance embeddings (or tokens) toward their class center, operating under the hypothesis that instance tokens of the same class should exhibit proximity.

However, the paper might have limited relevance to our context as it focuses on relatively small models (a few transformer layers as described in models like TabPFN, SCARF, etc.), and employs tokenization/embedding at the cell level. This may not be a significant concern when both model size and data size increase.