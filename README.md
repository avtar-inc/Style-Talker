# Style-Talker [![arXiv](https://img.shields.io/badge/arXiv-2408.11849-<COLOR>.svg)](https://arxiv.org/abs/2408.11849)
An official implementation of Style-Talker for Spoken Dialogue Generation

## Prerequisites

1. Clone [StyleTTS 2](https://github.com/yl4579/StyleTTS2).
2. In the requirements specify numpy version as numpy==1.26.4, as it is the only version compatible to run with the other requirements of the model.
3. Install necessary packages:

```
conda create --name StyleTalker python=3.9
conda activate StyleTalker
pip install -r requirements.txt
```

Most requirements are copied from StyleTTS 2 and Qwen-Audio.

## Turn-by-turn Inference 

Please check **run_style_talker.ipynb**.

The current model checkpoint takes the previous three rounds of conversation and generates the follow-up speaker, i.e., the model takes SpkA->SpkB->SpkA and generates ->SpkB.

The last SpkA is passed in as raw speech waveform, and the previous context is pre-transcribed.

*The number of previous rounds (context) is restricted by the GPU memory and the data, and could be extended.*

## Training (TODO)

(Files pushed)

## Checkpoints

We have trained (finetuned) Style-Talker on [DailyTalk](https://arxiv.org/abs/2207.01063) dataset.

The checkpoints (Qwen-Audio and StyleTTS 2) can be downloaded from [Google drive](https://drive.google.com/drive/folders/1SBYqzyPdYhdw2YnEBsVtQzBnNRAYHkML?usp=sharing).

Please update QWENAUDIO_CKPT_ROOT and STYLETTS2_CKPT_ROOT to where you store these checkpoints 

and STYLETTS2_CODE_ROOT to where StyleTTS 2's repository was cloned, in run_style_talker.ipynb.


## Citation

If you find this work helpful, please cite:

```bibtex
@article{li2024styletalker,
  title={Style-Talker: Finetuning Audio Language Model and Style-Based Text-to-Speech Model for Fast Spoken Dialogue Generation},
  author={Li, Yinghao Aaron and Xilin, Jiang and Darefsky, Jordan and Zhu, Ge and Mesgarani, Nima},
  journal={First Conference on Language Modeling},
  year={2024}
}
```

This work is built upon StyleTTS 2 and Qwen-Audio.

```bibtex
@inproceedings{NEURIPS2023_3eaad2a0,
   author = {Li, Yinghao Aaron and Han, Cong and Raghavan, Vinay and Mischler, Gavin and Mesgarani, Nima},
   booktitle = {Advances in Neural Information Processing Systems},
   editor = {A. Oh and T. Naumann and A. Globerson and K. Saenko and M. Hardt and S. Levine},
   pages = {19594--19621},
   publisher = {Curran Associates, Inc.},
   title = {StyleTTS 2: Towards Human-Level Text-to-Speech through Style Diffusion and Adversarial Training with Large Speech Language Models},
   url = {https://proceedings.neurips.cc/paper_files/paper/2023/file/3eaad2a0b62b5ed7a2e66c2188bb1449-Paper-Conference.pdf},
   volume = {36},
   year = {2023}
}


@article{Qwen-Audio,
  title={Qwen-Audio: Advancing Universal Audio Understanding via Unified Large-Scale Audio-Language Models},
  author={Chu, Yunfei and Xu, Jin and Zhou, Xiaohuan and Yang, Qian and Zhang, Shiliang and Yan, Zhijie  and Zhou, Chang and Zhou, Jingren},
  journal={arXiv preprint arXiv:2311.07919},
  year={2023}
}

```

