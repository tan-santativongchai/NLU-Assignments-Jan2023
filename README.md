# Readings Assignment
Here are my paper lectionaries:</br>
### 1. The Geometry of Multilingual Language Model Representations
#### Source: https://preview.aclanthology.org/emnlp-22-ingestion/2022.emnlp-main.9/
||Contents|
|---|---|
|Related Works|Mean representation distances between languages correlate with phylogenetic distances between languages (Rama et al., 2020), and individual representations can be used to predict linguistic typological features (Choenni and Shutova, 2020), particularly after projecting onto language-sensitive subspaces (Liang et al., 2021). The models also maintain language-neutral subspaces that encode information that is shared across languages. Syntactic information is encoded largely within a shared syntactic subspace (Chi et al., 2020), token frequencies may be encoded similarly across languages (Rajaee and Pilehvar, 2022), and representations shifted according to language means facilitate cross-lingual parallel sentence retrieval (Libovický et al., 2020; Pires et al., 2019)|
|Method|- used the pre-trained language model XLM-R. <br/>- XLM-R follows the Transformer architecture of BERT and RoBERTa<br/>- Model is trained to predict masked tokens in 100 languages.<br/>- Inputted text sequences from the OSCAR corpus of cleaned web text data to extract contextualized token representations from XLM-R<br/>- Inputted text sequences from the OSCAR corpus of cleaned web text data.<br/>- Used the vector representations outputted by each Transformer layer as our token representations in layers one through twelve.<br/>- Used the uncontextualized token embeddings for layer zero.<br/>- Affine subspaces accounted for language modeling performance. To assess the extent to which affine subspaces encoded relevant information in their corresponding languages.<br/>- Affine subspaces accounted for language modeling performance to directly quantified distances between the subspaces themselves. <br/>- To assess the extent to which affine subspaces encoded relevant information in their corresponding languages.<br/>- Then, do either Language-sensitive axes or Language-neutral axes.|
|Result|88 considered languages were skewed substantially towards Indo-European languages; 52 of the 88 languages were in some subfamily of the Indo-European languages|

### 2. A Fast and Accurate Dependency Parser using Neural Networks
#### Source: https://aclanthology.org/D14-1082.pdf
||Contents|
|---|---|
|Related Works|Neural networks in a broad-coverage Penn Treebank parser (Henderson, 2004), Applied Incremental Sigmoid Belief Networks to constituency parsing  (Titov and Henderson, 2007), Transition-based dependency parsers using a Temporal Restricted Boltzman Machine (Garg and Henderson, 2011), Precursive neural networks for transition-based dependency parsing (Stenetorp, 2013), |
|Method|• LEFT-ARC(l): adds an arc s1 → s2 with label l and removes s2 from the stack. Pre-condition: \|s\| ≥ 2.<br/>• RIGHT-ARC(l): adds an arc s2 → s1 with label l and removes s1 from the stack. Pre-condition: \|s\| ≥ 2.<br/>• SHIFT: moves b1 from the buffer to the stack. Precondition: \|b\| ≥ 1.|
|Result|The parser is superior in terms of both accuracy and speed. Comparing with the baselines of arc-eager and arc-standard parsers, the parser achieves around 2% improvement in UAS and LAS on all datasets, while running about 20 times faster.|

### 3. Sentence-Incremental Neural Coreference Resolution
#### Source: https://aclanthology.org/2022.emnlp-main.28.pdf
||Contents|
|---|---|
|Related Works|ncremental transformer architectures (Katharopoulos et al., 2020; Kasai et al., 2021), and adapting these architectures to NLU tasks (though not coreference resolution) (Madureira and Schlangen, 2020; Kahardipraja et al., 2021). In this work, we focus on the simpler sentence-incremental setting, believing it to be sufficient for downstream tasks.|
|Method|Shift-Reduce Framework (Push, Advance, Pop, Peek), Neural Implementation (Mention Detector, Mention Clustering Model)|
|Result|Within partly incremental systems, the ICoref model performs best, below SpanBERT by 0.4 F1. Part-Inc model performs comparably to longdoc only trailing ICoref by 0.7 F1 points. The performance difference is much larger here: 7 F1 compared to 2 F1 in OntoNotes. The gap between the Sent-Inc and Part-Inc is also much smaller: only 2.5 F1 points compared to 6.3 F1 on OntoNotes.|

### 4. Interpreting Language Models with Contrastive Explanations
#### Source: https://aclanthology.org/2022.emnlp-main.14.pdf
||Contents|
|---|---|
|Related Works|Counterfactual explanations for text classification models by erasing certain features from the input and projecting the input representation to the “contrastive space” (Jacovi et al., 2021); (Wallace et al., 2019) attempt to explain language modeling predictions|
|Method|They used GPT-2 (Radford et al., 2019) and GPT-Neo (Black et al., 2021) to extract explanations.|
|Result|overall, contrastive explanations have a higher alignment with linguistic paradigms than their non-contrastive counterparts for both GPT-2 and GPT-Neo across the different metrics.|

### 5. BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding
#### Source: https://arxiv.org/pdf/1810.04805.pdf
||Contents|
|---|---|
|Related Works|Unsupervised Feature-based Approaches<br>- non-neural (Brown et al., 1992;Ando and Zhang, 2005; Blitzer et al., 2006)<br>- neural (Mikolov et al., 2013; Pennington et al., 2014)<br>- ELMo and its predecessor (Peters et al., 2017, 2018a)<br><br>Unsupervised Fine-tuning Approaches<br>- pre-trained word embedding parameters from unlabeled text (Collobert and Weston, 2008)<br>- pre-trained from unlabeled text and fine-tuned for a supervised downstream task (Dai and Le, 2015; Howard and Ruder, 2018; Radford et al., 2018)<br>- OpenAI GPT (Radford et al., 2018)<br>- GLUE benchmark (Wang et al., 2018a)<br><br>Transfer Learning from Supervised Data<br>- natural language inference (Conneau et al., 2017)<br>- machine translation (McCann et al., 2017)<br>- Fine-tune models pre-trained with ImageNet (Deng et al., 2009; Yosinski et al., 2014)|
|Method|BERT’s model architecture is a multi-layer bidirectional Transformer encoder and released in the tensor2tensor library. BERT Transformer uses bidirectional self-attention, while the GPT Transformer uses constrained self-attention where every token can only attend to context to its left. <br><br>Pre-training BERT<br>Masked LM >> Next Sentence Prediction (NSP)<br><br>Fine-tuning BERT<br>They simply plug in the task specific inputs and outputs into BERT and fine tune all the parameters end-to-end.|
|Result|Effect of Pre-training Tasks<br> In order to make a good at strengthening the LTR system, they added a randomly initialized BiLSTM on top. This does significantly improve results on SQuAD, but the results are still far worse than those of the pre-trained bidirectional models. The BiLSTM hurts performance on the GLUE tasks.<br><br>Effect of Model Size<br>Larger models lead to a strict accuracy improvement across all four datasets, even for MRPC which only has 3,600 labeled training examples, and is substantially different from the pre-training tasks. It is also perhaps surprising that They were able to achieve such significant improvements on top of models which are already quite large relative to the existing literature.<br><br>Feature-based Approach with BERT<br>BERT[LARGE] performs competitively with state-of-the-art methods. The best performing method concatenates the token representations from the top four hidden layers of the pre-trained Transformer, which is only 0.3 F1 behind fine-tuning the entire model. This demonstrates that BERT is effective for both fine-tuning and feature-based approaches.|
