# NLP_Assignment
This repository is for submitting homework for AT82.05 Artificial Intelligence:NLU at Asian Institute of Technology

## Paper reading assignment
## 1. Improving Chinese Grammatical Error Detection via Data augmentation by Conditional Error Generation
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
| --- | --- |
| Key Related Work | The related work discusses the success of Long Short Term Memory networks (LSTM) in sequence learning tasks and various proposals for improving RNN architectures. The authors focus on studying the properties of LSTM representations and predicting individual error types. Their work complements previous studies on long-term interactions in recurrent networks and draws inspiration from object detection analysis. |
| Datasets | Penn Treebank dataset Marcus et al. (1993). |
|          | Hutter Prize 100MB of Wikipedia dataset Hutter (2012). |
| Solution  | The authors of this study used character-level language models to explore the predictions and learned representations of long short-term memory networks (LSTMs) on real-world data. Their experiments, which included qualitative visualization and cell activation statistics, demonstrated that RNNs are able to learn powerful and often interpretable long-range interactions on real-world data.Also conducted an error analysis, which allowed them to break down cross entropy loss into several interpretable categories and identify the sources of remaining limitations in the model. |
| Results  | The study revealed that increasing the size of the model significantly reduced errors in the n-gram category, indicating that more advanced structural changes might be necessary to address the remaining errors. |

## 3. Semi-supervised sequence tagging with bidirectional language models
### Matthew E. Peters, Waleed Ammar, Chandra Bhagavatula, Russell Power

| Problem  | What is the proposed approach for adding pretrained context embeddings to NLP systems and how is it different from existing approaches?|
| --- | --- |
| Proposal | adding pretrained context embeddings from bidirectional language models to NLP systems to produce context-sensitive representations. |
| Objective | To demonstrate a semi-supervised approach for improving the performance of neural network architectures for natural language processing (NLP) tasks such as named entity recognition (NER) and chunking. |
| Datasets | d entity recognition (NER) and chunking |
| Key Related Work  | 1. Unlabeled data: The TagLM method is inspired by pre-trained word embeddings in supervised sequence tagging models and is similar to Li and McCallum's (2005) probabilistic generative model. Other semi-supervised learning methods for structured prediction problems include co-training, expectation maximization, structural learning, and maximum discriminant functions. LM embeddings are related to methods for learning sentence and document encoders from unlabeled data, which can be used for text classification and textual entailment among other tasks. Dai and Le (2015) pre-trained LSTMs using language models and sequence autoencoders for classification tasks, whereas TagLM uses unlabeled data to learn token-in-context embeddings.|
|                   | 2. Interpreting RNN states. The article cites previous research on interpreting RNN activations, including Linzen et al. (2016), who demonstrated that LSTM units could learn to predict singular-plural distinctions, and Karpathy et al. (2015), who visualized character level LSTM states and identified that individual cells capture long-range dependencies such as line lengths, quotes, and brackets. The authors state that their work complements these studies by demonstrating that LM states are useful for downstream tasks as a means of interpreting what they learn.|
|                   | 3. Other sequence tagging models: Bidirectional RNN models are currently the state-of-the-art for sequence tagging problems. Other sequence tagging models have also been proposed, but it is uncertain if LM embeddings could be effectively used as additional features in these models due to potential limitations in their complexity. |
| Solution  | The approach involves incorporating pre-trained context embeddings from bidirectional language models into the NLP systems. This method is applied to sequence labeling tasks, specifically named entity recognition (NER) and chunking. |
| Results  | The paper demonstrates that the addition of pre-trained context embeddings improves the performance of the NLP system and achieves state-of-the-art results on the two standard datasets for NER and chunking. This approach outperforms previous systems that use other forms of transfer or joint learning with additional labeled data and task-specific gazetteers.|


## 4 PPT: Pre-trained Prompt Tuning for Few-shot Learning

Paper link: https://arxiv.org/pdf/2109.04332.pdf

| Aim | Gu et al. proposed pre-trained prompts by adding soft prompts during the pre-training stage in order to achieve a better initialization for downstream tasks. | 
| ------- | --- | 
| Background | The effectiveness of using prompts for pre-trained language models (PLMs) has been demonstrated as they serve as a link between pre-training tasks and different downstream tasks. However, when PLMs are frozen and only soft prompts are tuned through prompt tuning, this method offers an efficient way to adapt large-scale PLMs to downstream tasks. Despite its good performance when sufficient downstream data is available, prompt tuning performs poorly in few-shot learning scenarios, which limits its application. To overcome this limitation, Gu et al. have introduced pre-trained prompt tuning (PPT) in their paper. | 
| Datasets | The researchers focused their experiments primarily on English and Chinese datasets. They evaluated the performance of the T5 model in various sizes, from small to XXL, using full-model tuning (FT) and compared the results with other baselines such as PPT under prompt tuning (PT). Specifically, they utilized datasets such as SST-2, RACE-m, BoolQ, and CB for English tasks and CCPM, C3, and LCQMC for Chinese tasks. | 
| Methods | They began by pre-training prompts and utilizing them for specific tasks. They took an input sentence and label, then applied a pattern mapping to create a new sequence that included prompt tokens as hints while also retaining the masked tokens, allowing PLMs to predict tokens at the masked positions. They then utilized a verbalizer to map true labels to label tokens, resulting in a pattern-verbalizer pair for each classification task, represented by new sequences and label tokens.
They also assumed that downstream tasks could be grouped into sets of pattern-verbalizer pairs, and pre-trained soft prompts were obtained through pre-training these tasks with fixed model parameters. Soft prompt initialization was used to optimize the process for each task. They categorized typical classification tasks into three formats (sentence-pair classification, multiple-choice classification, and single-text classification) to ensure prompt generalization. They discovered that multiple-choice classification was the most universal format among these, and all classification tasks could be unified in this format. |  
| Results and Findings| The researchers conducted experiments on two variations of PPT, namely Hybrid PPT, which combines carefully designed hard prompts with pre-trained soft prompts, and Unified PPT, which involves unified tasks in the multiple-choice classification format. However, the major findings of their study can be summarized as follows:
1. Larger models showed better performance under the few-shot setting, and the study focused on the large-scale pre-trained model CPM-2, which outperformed mT5-XXL on all tasks on Chinese datasets despite having the same parameter scale.

2. PPT performed significantly better than Vanilla PT and LM Adaption on most datasets, although it performed worse than Hybrid PT on BoolQ. However, using Hybrid PPT by combining PPT and hard prompts led to better performance than all baselines on RACE-m, LCQMC, and C3 datasets.

3. PPT outperformed FT on all Chinese datasets and most English datasets, indicating a gap between masked language modeling and downstream tasks. The researchers plan to extend the proposed method in the future based on this observation.

4. PPT led to lower variances across all datasets with additional hard prompts or further pre-training with language modeling, whereas Vanilla PT or Hybrid PT increased variances for some datasets, which is not different from random guesses.

Moreover, the researchers tested Unified PPT on datasets with more than 5 labels, and it outperformed FT and PT baselines by a large margin. They also observed that PPT sped up the convergence of Vanilla PT on RACE-m and CB datasets, although it converged a bit slower than FT.| 
| Limitations | Although prompt pre-training has helped to reduce the gap between masked language modeling and downstream tasks to some extent, there is still a difference. Additionally, the convergence of prompt pre-training is slower compared to fine-tuning. Hence, this research suggests exploring ways to speed up convergence in the future. |  
| Future Work | The paper suggests three important areas for future research:

1.Creating a consistent format for various tasks (e.g., language generation, relation extraction) with corresponding pre-training objectives.
2.Examining the effectiveness of few-shot learning techniques when combined with other parameter tuning approaches, and adapting unified task pre-training to them.
3.Investigating the performance of unified task pre-training on pre-trained language models beyond the soft-prompt based approaches. | 
