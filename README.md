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
conda create -n vdpm python=3.12 -y
conda activate vdpm
pip install -r requirements.txt
```

## Viser demo
```bash
python visualise.py ++vis.input_video=examples/videos/camel.mp4
```

## Gradio demo
```bash
python gradio_demo.py
```
