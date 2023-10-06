<h1 align="center">
<p>QKWS :eye_speech_bubble:</p>
<p align="center">
<img alt="GitHub" src="https://img.shields.io/github/license/cross-caps/AFLI?color=green&logo=GNU&logoColor=green">
<img alt="python" src="https://img.shields.io/badge/python-%3E%3D3.8-blue?logo=python">
<img alt="pytorch" src="https://img.shields.io/badge/pytorch-%3E%3D1.8-orange?logo=pytorch">
<img alt="PyPI" src="https://img.shields.io/badge/release-v1.0-brightgreen?logo=apache&logoColor=brightgreen">
</p>
</h1>

<h2 align="center">
<p>Quaternion Neural Models for Keyword Spotting</p>
</h2>

Code to accompanying WASPAA-23 Submission:

Towards on-Device Keyword Spotting using Low-Footprint Quaternion Neural Models

## What's New?

- (5/10/2023)  SOTA QCNN model using Skew-Symmetric Digonalization ([Check Leader Board Here](https://paperswithcode.com/sota/keyword-spotting-on-google-speech-commands?metric=Google%20Speech%20Commands%20V2%2035))
- (21/09/2023) Added pretrained QCNN model
- (16/09/2023) Added training recipe for various QCNN models

### Data
Model training and testing requires the [Google Speech Commands V2](http://www.) datasets.

In addition, you need to download the [MUSAN](https://www.openslr.org/17/) noise corpus for data augmentation.

## Training Examples

- Quaternion BCResNet
```
python ./trainSpeakerNet.py --config ./configs/RawNet3_AAM.yaml
```

- Quaternion MatchboxNet
```
python ./trainSpeakerNet.py --config ./configs/DSR_RawNet3_AAM.yaml
```

## Pre-Trained Models
Pretrained models are available in the `/exp/` directory

The following script should return `98\%` Acc the on Test set.
```
python ./trainNet.py --eval --config ./configs/QMatchboxNet.yaml --initial_model models/model.pt
```
### Accelerating training (Feature Upcoming)

- Use `--mixedprec` flag to enable mixed precision training. This is recommended for latest Nvidia RTX cards.

- Use `--distributed` flag to enable distributed training over multiple GPUs.

## Contact
Aryan Chaudhary: email

