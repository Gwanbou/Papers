## Pool-Search-Demonstrate: Improving Data-wrangling LLMs via better in-context examples

Paper: [https://openreview.net/attachment?id=6Kb3pE9nWQ&name=pdf](https://openreview.net/attachment?id=6Kb3pE9nWQ&name=pdf)

Code: NA

Organization: University of Wisconsin–Madison

This paper introduces a demonstration strategy for data wrangling by LLMs. The central idea is the Pool-Search-Demonstrate (PSD) approach, which involves selecting in-context examples from the embedding space to construct LLM prompts (few-shot learning). The authors evaluate PSD across three tasks: Data Imputation (DI), Entity Matching (EM), and Error Detection (ED). The results indicate that PSD enhances performance, showing an 84\% improvement over random example demonstrations and a 49\% improvement over manually selected examples.

However, the paper is not very exciting. The PSD method is quite straightforward:
- Step 1. Given $n$ entries $E = \{e_1 , ..., e_n\}$, create embedded entries as $x_i = {\rm Embedder}({\rm serialize}(e_i))$, and embedded dataset as $X = \{x_1, ..., x_n\}$.
- Step 2. Get centroids by k-means ${\rm (centroidX, centroidE)} = {\rm kMeans}(X, E , k)$.
- Step 3. Create example pool by ${\rm Pool}(E) := \{(e, y_e) | e \in centroidE, y_e\ {\rm is\ a\ label\ for\ }e\}$.
- Step 4. Select $m$ examples as demonstration set: $M_e := {\rm kNN}(x, {\rm Pool}(E) , m)$, $x := {\rm Embedder}({\rm serialize}(e))$.

For experiments, they use FLAN-T5-3B and Vicuna-7B as base models and the overall results are satisfactory but not remarkable. The combination of A LLM with PSD does outperform manual demonstrations or even random selection (not to mention traditional ML models) across all three tasks by average, but not every task. Additionally, the authors note that "PSD worked better with a full demo pool of training data than the pool of centers in k-means clustering in most cases." While it can reduce costs, the proposed PSD approach may not make sense to some extent.