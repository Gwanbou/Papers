## TabR: Unlocking the Power of Retrieval-Augmented Tabular Deep Learning

### Overview

- The authors of the paper argue that retrieval-based methods can be used to improve the performance of deep learning models for tabular data.
- They propose TabR, which combines a simple feed-forward architecture with an attention-like retrieval component.

### Key takeaways from the paper

- Retrieval-based methods can be used to improve the performance of deep learning models for tabular data.

### Limitations and comments

- Mostly limited only to numerical features.
- It's still surprising that using an average of the embeddings of the training data fares better than just using a model trained on the training data. There's no additional data that is used at testing time (as opposed to how it was for our payment date prediction use case), so an adequate model should be able to memorize the training set and not need this retrieval step.
- When comparing against Boost methods, they probably have to cheat a bit to win: i.e., they never compare single trainings, but only ensembles of such models. For boosting methods, this adds no value (since they are already ensembles), but likely it does for their algorithm.
- Also there's the risk they overfit their model choice on the test set. They claim that hyperparameter optimization was (correctly) done on the validation set, but the results in the last line of Table 2 (where they evaluate on several datasets to decide which elements of the model to keep and which to discard) are identical to those of Table 3 (where they compare against other deep learning based models), which seems to suggest the test set was used in both cases. Not a big deal, but makes the overall strictness about computing many seeds and analyzing mean and standard deviation a bit weird.
