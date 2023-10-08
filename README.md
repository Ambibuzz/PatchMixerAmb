# PatchMixer

## Introduction

This is the official implementation of PatchMixer: [PatchMixer: A Patch-Mixing Architecture for Long-Term Time Series Forecasting](https://arxiv.org/abs/2310.00655). 

**As the paper is under review, the full source code is expected to be released upon conference acceptance.**

## Model Overview 

![alt text](https://github.com/Zeying-Gong/PatchMixer/raw/main/pic/PatchMixer_0928.png)

PatchMixer is primarily composed of two convolutional layers and two forecasting heads. Its distinguishing feature is the “patch-mixing” design, which means the model initially segments the input time series into smaller temporal patches and subsequently integrates information from both within and between these patches.

## Results

### 🏆 Achieve state-of-the-art in Long-Term Time series Forecasting**.

Quantitatively, PatchMixer demonstrates an overall relative reduction of $\mathbf{3.9\%}$ on MSE and $\mathbf{3.0\%}$ on MAE in comparison to the state-of-the-art Transformer (PatchTST). When evaluated against the best-performing MLP-based model (DLinear), our model showcases an overall decline of $\mathbf{11.6\%}$ on MSE and $\mathbf{9.4\%}$ on MAE. Moreover, in comparison to the achievable outcomes with the best CNN-based model (TimesNet), we demonstrate a remarkable overall relative reduction of $\mathbf{21.2\%}$ on MSE and $\mathbf{12.5\%}$ on MAE.

![alt text](https://github.com/Zeying-Gong/PatchMixer/raw/main/pic/sota.png)

### 🌟 Training and Inference Efficiency

Our results highlight two key improvements. First, PatchMixer achieves a 3x faster inference and 2x faster training speed compared to PatchTST. Second, PatchTST's performance is highly sensitive to the length of the look-back window, particularly when it reaches or exceeds 1440. In contrast, PatchMixer exhibits fewer fluctuations in both inference and training times with increasing historic length, contributing to higher accuracy and computational efficiency. 

![alt text](https://github.com/Zeying-Gong/PatchMixer/raw/main/pic/speed.png)

### 🌟 Efficiency on Long Look-back Windows

In principle, the large receptive field is beneficial for improving performance, while the receptive field of the look-back window in time series analysis is also important. Generally speaking, a powerful LTSF model with a strong temporal relation extraction capability should be able to achieve better results with longer input historical sequences. Recent baselines such as PatchTST, DLinear, and our PatchMixer consistently reduce the MSE scores as the receptive field increases, which confirms our model's capability to learn from the longer look-back window.

![alt text](https://github.com/Zeying-Gong/PatchMixer/raw/main/pic/vary_lookback.png)

## Contact

If you have any questions or concerns, please submit an issue. 

## Citation

If you find this repository useful in your research, please consider citing our paper:
```
@inproceedings{Gong2023PatchMixerAP,
  title={PatchMixer: A Patch-Mixing Architecture for Long-Term Time Series Forecasting},
  author={Zeying Gong and Yujin Tang and Junwei Liang},
  year={2023},
  url={https://api.semanticscholar.org/CorpusID:263334059}
}
```

