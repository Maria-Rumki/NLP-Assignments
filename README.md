# NLP_Assignment
This repository is for submitting homework for AT82.05 Artificial Intelligence:NLU at Asian Institute of Technology

## Paper reading assignment
## 1. Improving Chinese Grammatical Error Detection via Data augmentation
by Conditional Error Generation
### Tianchi Yue, Shulin Liu, Huihui Cai, Tao Yang, Shengkang Song, Tinghao Yu

| Problem  | How to detect grammatical errors in Chinese texts.|
| --- | --- |
| Proposal | For producing Chinese grammatical errors, they suggest the novel Conditional Non-Autoregressive Error Generation (CNEG) model. |
| Objective | Generate high-quality grammatical errors to improve the performance of CGED models. |
| Datasets | Public datasets from CGED tasks (Lee et al., 2016; Rao et al., 2017, 2018, 2020). |
|          | Select 2016, 2017, 2018 and 2020 training dataset as their training dataset. |
| Key Related Work  | 1. Improving Grammatical Error Correction with Machine Translation Pairs (Zhou et al., 2020) -> They Consider that the Neural Machine Translation (NMT) model is much superior to the Statistical Machine Translation (SMT) model, then use the NMT model to produce right and incorrect sentences, respectively.|
|                   | 2. Improving Grammatical Error Correction Models with Purpose-Built Adversarial Examples (Wang and Zheng, 2020) -> By using a seq2seq model, the most vulnerable tokens are first identified. These tokens are subsequently replaced with training dataset grammatical errors.|
| Solution  | They build their generative model around a BERT encoder with a nonautoregressive decoding layer to produce context-dependent mistakes. They include the original span in their generative model, allowing it to forecast the incorrect span given the original span. Additionally, they include a filtering technique to remove error-free spans.|
| Results  | Achieves better performance than all compared data augmentation methods on the CGED-2018 and CGED-2020 benchmarks. |
| In term of models   | The CNEG model can generate errors that do not appear in the training dataset. |
| In term of measurement  | The perplexities of generated spans are measured using a BERT that has already been trained. |


## 2. VISUALIZING AND UNDERSTANDING RECURRENT NETWORKS
### Author Andrej Karpathy, Justin Johnson, Li Fei-Fei

| Problem  | 1.What is the performance of Long Short-Term Memory (LSTM) models in capturing long-range dependencies such as line lengths, quotes, and brackets, and how can interpretable cells within the LSTM architecture be identified and analyzed to improve LSTM models' performance? |
|          | 2.How do LSTM models compare to finite horizon n-gram models in capturing long-range structural dependencies, and what areas for further study and improvement can be identified based on any remaining errors in the LSTM models?
| --- | --- |
| Key Related Work  |The related work discusses the success of Long Short Term Memory networks (LSTM) in sequence learning tasks and various proposals for improving RNN architectures. The authors focus on studying the properties of LSTM representations and predicting individual error types. Their work complements previous studies on long-term interactions in recurrent networks and draws inspiration from object detection analysis. |
| Solution  | The authors of this study used character-level language models to explore the predictions and learned representations of long short-term memory networks (LSTMs) on real-world data. Their experiments, which included qualitative visualization and cell activation statistics, demonstrated that RNNs are able to learn powerful and often interpretable long-range interactions on real-world data.Also conducted an error analysis, which allowed them to break down cross entropy loss into several interpretable categories and identify the sources of remaining limitations in the model. |
| Results  | The study revealed that increasing the size of the model significantly reduced errors in the n-gram category, indicating that more advanced structural changes might be necessary to address the remaining errors. |
