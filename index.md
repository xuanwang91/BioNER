## [Cross-type Biomedical Named Entity Recognition with Deep Multi-task Learning](https://academic.oup.com/bioinformatics/advance-article/doi/10.1093/bioinformatics/bty869/5126922?guestAccessKey=403bcc14-3eca-4ff0-b9fb-5ecd1c1744d2)
Xuan Wang, Yu Zhang, Xiang Ren, Yuhao Zhang, Marinka Zitnik, Jingbo Shang, Curtis Langlotz and Jiawei Han. _Bioinformatics_, 2018.

### Biomedical Named Entity Recognition (BioNER)
Biomedical named entity recognition (BioNER) is one of the most fundamental task in biomedical text mining that aims to automatically recognize and classify biomedical entities (e.g., genes, proteins, chemicals and diseases) from text. State-of-the-art BioNER systems often require handcrafted features (e.g., capitalization, prefix and suffix) to be specifically designed for each entity type. This feature generation process takes the majority of time and cost in developing a BioNER system, and leads to highly specialized systems that cannot be directly used to recognize new types of entities. Recent NER studies consider neural network models to automatically generate quality features. However, these models have millions of parameters and require very large datasets to reliably estimate the parameters. This poses a major challenge for biomedicine, where datasets of this scale are expensive and slow to create and thus neural network models cannot realize their potential. Although neural network models can outperform traditional sequence labeling models (e.g., CRF models), they are still outperfomed by handcrafted feature-based systems in multiple domains.

### Our Framework
we propose a new multi-task learning framework using character-level neural models for BioNER. The proposed framework, despite being simple and not requiring any feature engineering, achieves excellent benchmark performance. Our multi-task model is built upon a single-task neural network model ([Liu et al., 2018](https://arxiv.org/pdf/1709.04109.pdf)). In particular, we consider a BiLSTM-CRF model with an additional context-dependent BiLSTM layer for modeling character sequences. A prominent advantage of our multi-task model is that inputs from different datasets can efficiently share both character- and word-level representations, by reusing parameters in the corresponding BiLSTM units.

![lstm](https://github.com/xuanwang91/BioNER/blob/master/Screen%20Shot%202018-10-16%20at%208.27.31%20PM.png)

![mtms](https://github.com/xuanwang91/BioNER/blob/master/Screen%20Shot%202018-10-16%20at%208.27.42%20PM.png)

### Performance
We compare our model with recent state-of-the-art models on the five datasets mentioned above. We use F1 score as the evaluation metric.

|Model | [BC2GM](https://github.com/cambridgeltl/MTL-Bioinformatics-2016/tree/master/data/BC2GM-IOBES) | [BC4CHEMD](https://github.com/cambridgeltl/MTL-Bioinformatics-2016/tree/master/data/BC4CHEMD-IOBES) | [BC5CDR](https://github.com/cambridgeltl/MTL-Bioinformatics-2016/tree/master/data/BC5CDR-IOBES) | [NCBI-disease](https://github.com/cambridgeltl/MTL-Bioinformatics-2016/tree/master/data/NCBI-disease-IOBES) | [JNLPBA](https://github.com/cambridgeltl/MTL-Bioinformatics-2016/tree/master/data/JNLPBA-IOBES) |
| ------------- |-------------| -----| -----| -----| ---- |
| Dataset Benchmark | - | 88.06 | 86.76 | 82.90 | 72.55 |
| [Crichton et al. 2016](https://github.com/cambridgeltl/MTL-Bioinformatics-2016) | 73.17 | 83.02 | 83.90 | 80.37 | 70.09 |
| [Lample et al. 2016](https://github.com/glample/tagger) | 80.51 | 87.74 | 86.92 | 85.80 | 73.48 |
| [Ma and Hovy 2016](https://github.com/XuezheMax/LasagneNLP) | 78.48 | 86.84 | 86.65 | 82.62 | 72.68 |
| [Liu et al. 2018](https://github.com/LiyuanLucasLiu/LM-LSTM-CRF) | 80.00 | 88.75 | 86.96 | 83.92 | 72.17 |
| MTM-CW | **80.74** | **89.37** | **88.78** | **86.14** | **73.52** |

### Resources
Codes and datasets have been uploaded to [Github](https://github.com/yuzhimanhua/LM-LSTM-CRF).

### Reference
If you find the code and datasets useful, please cite the following paper:
```
@article{doi:10.1093/bioinformatics/bty869,
author = {Wang, Xuan and Zhang, Yu and Ren, Xiang and Zhang, Yuhao and Zitnik, Marinka and Shang, Jingbo and Langlotz, Curtis and Han, Jiawei},
title = {Cross-type Biomedical Named Entity Recognition with Deep Multi-Task Learning},
journal = {Bioinformatics},
volume = {},
number = {},
pages = {bty869},
year = {2018},
doi = {10.1093/bioinformatics/bty869},
URL = {http://dx.doi.org/10.1093/bioinformatics/bty869},
eprint = {/oup/backfile/content_public/journal/bioinformatics/pap/10.1093_bioinformatics_bty869/1/bty869.pdf}
}
```
