<div align="center">
<h1>V-DPM: 4D Video Reconstruction with Dynamic Point Maps 实验</h1>

[comment]: <> (  <h2 align="center">PAPER</h2>)
  <h3 align="center">
  <a href="https://github.com/eldar/vdpm">Github</a>
  | <a href="https://arxiv.org/pdf/2601.09499">Paper</a>
  </h3>

</div>

## Setup

First, clone the repository and create a Conda environment (install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or Anaconda if you do not have `conda` yet).

```bash
git clone git@github.com:eldar/vdpm.git
cd vdpm

# VGGT 放在项目目录下的 vggt/，便于本地改代码；需与原先锁定提交一致时再执行 checkout
git clone org-16943930@github.com:facebookresearch/vggt.git vggt
git -C vggt checkout 44b3afb

conda create -n vdpm python=3.12 -y
# conda remove --name vdpm --all
conda activate vdpm
# 针对5090安装cuda13.0
# pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu128
# pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu130
pip install torch torchvision torchaudio \
  --extra-index-url https://download.pytorch.org/whl/cu128 \
  --timeout 1000
  
pip install -r requirements.txt

# 验证torch
python -c "import torch; print(torch.__version__, torch.cuda.is_available(), torch.version.cuda); print(torch.cuda.get_device_name(0) if torch.cuda.is_available() else 'no cuda')"
```

## Viser demo
```bash
python visualise.py ++vis.input_video=examples/videos/camel.mp4
```

## Gradio demo
```bash
python gradio_demo.py
```
