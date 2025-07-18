---
Organization: Universitat Autònoma de Barcelona
Code: "https://github.com/maxhormazabal/EaGERS-DVQA"
---

> [!PDF|255, 208, 0] [[[2025 Hormazábal] Spatially Grounded Explanations in Vision Language Models for Document Visual Question Answering.pdf#page=1&annotation=222R|[2025 Hormazábal] Spatially Grounded Explanations in Vision Language Models for Document Visual Question Answering, p.1]]
> > We introduce EaGERS, a fully training-free and model-agnostic pipeline that (1) generates natural language rationales via a vision lan- guage model, (2) grounds these rationales to spatial sub-regions by com- puting multimodal embedding similarities over a conﬁgurable grid with majority voting, and (3) restricts the generation of responses only from the relevant regions selected in the masked image

> [!PDF|255, 208, 0] [[[2025 Hormazábal] Spatially Grounded Explanations in Vision Language Models for Document Visual Question Answering.pdf#page=3&annotation=228R|[2025 Hormazábal] Spatially Grounded Explanations in Vision Language Models for Document Visual Question Answering, p.3]]
> > EaGERS Document VQA pipeline: (1) the multimodal model generates a spatial natural language explanation from the image and the question; (2) the image is segmented into an m × n grid; (3) embeddings of the explanation and each sub-region are obtained using BLIP, CLIP, and ALIGN; (4) majority voting selects the most relevant regions; (5) the image is masked to retain only those regions, and the model is re-queried with the question to generate the final answer.
