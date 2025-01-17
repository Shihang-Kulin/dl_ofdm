# Paper 
Zhongyuan Zhao, Mehmet C. Vuran, Fujuan Guo, and Stephen Scott, Deep-Waveform: A Learned OFDM Receiver Based on Deep Complex-valued Convolutional Networks, accepted to IEEE Journal on Selected Areas in Communications, arXiv preprint [arXiv:1810.07181](https://arxiv.org/abs/1810.07181)

[Pre-Print](https://arxiv.org/abs/1810.07181)

```
@article{zhao2018deepwaveform,
author={Zhongyuan Zhao and Mehmet C. Vuran and Fujuan Guo and Stephen Scott},
title={Deep-Waveform: A Learned OFDM Receiver Based on Deep Complex-valued Convolutional Networks},
journal={accepted to IEEE Journal on Selected Areas in Communications},
vol = {},
month = {July},
year = {2021},
url={https://arxiv.org/abs/1810.07181},
}
```


## Abstract
The (inverse) discrete Fourier transform (DFT/IDFT) is often perceived as essential to orthogonal frequency-division multiplexing (OFDM) systems. In this paper, a deep complex-valued convolutional network (DCCN) is developed to recover bits from time-domain OFDM signals without relying on any explicit DFT/IDFT. The DCCN can exploit the cyclic prefix (CP) of OFDM waveform for increased SNR by replacing DFT with a learned linear transform, and has the advantage of combining CP-exploitation, channel estimation, and intersymbol interference (ISI) mitigation, with a complexity of \mathcal{O}(N^2). Numerical tests show that the DCCN receiver can outperform the legacy channel estimators based on ideal and approximate linear minimum mean square error (LMMSE) estimation and a conventional CP-enhanced technique in Rayleigh fading channels with various delay spreads and mobility. The proposed approach benefits from the expressive nature of complex-valued neural networks, which, however, currently lack support from popular deep learning platforms. In response, guidelines of exact and approximate implementations of a complex-valued convolutional layer are provided for the design and analysis of convolutional networks for wireless PHY. Furthermore, a suite of novel training techniques are developed to improve the convergence and generalizability of the trained model in fading channels. This work demonstrates the capability of deep neural networks in processing OFDM waveforms and the results suggest that the FFT processor in OFDM receivers can be replaced by a hardware AI accelerator.

## About this code
Source code for Deep Learning-Based OFDM Receiver.

+ Modulation: BPSK, QPSK, 8-QAM, 16-QAM, of Gray mapping.
+ SNR: -10:1:29 dB

### Software platform
+ Matlab R2017b, R2018a (replace `rayleighchan` in the code for newer release)
+ Python3 compatiable
+ TensorFlow 1.x: `tensorflow-gpu==1.15`, docker tensorflow image [1.15.5-gpu-jupyter](https://hub.docker.com/layers/tensorflow/tensorflow/1.15.5-gpu-jupyter/images/sha256-5f2338b5816cd73ea82233e2dd1ee0d8e2ebf539e1e8b5741641c1e082897521?context=explore
) is highly recommended. 

### Contents of directories
```bash
.
├── dev # latest working source code
├── test_v1 # archived for old version https://arxiv.org/abs/1810.07181v3
├── README.md 
└── LICENSE
```


### Usage
1. Run `script_rayleigh` in Matlab for benchmarks
2. Run `python3 run_local_ofdm.py --awgn=True` in terminal for training and testing results. 

