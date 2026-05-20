# SCORE DA Activity

Activity on Score-Based Data Assimilation (SDA) on the Lorenz system available on the following link 
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pdenailly/score-da-colab/blob/main/notebook_sda.ipynb)
Please, check that the execution mode is set on GPU before launching trainings.

**SDA approach**: Uses diffusion models to learn score functions over trajectory segments. At inference time, we generate trajectories conditioned on sparse noisy observations. The neat thing is the observation model is decoupled from training, so we can do zero-shot inference on different observation scenarios.

SDA are evaluated on the Lorenz system with two scenarios:
- `lo`: sparse observations (every 8 steps, low noise σ=0.05)
- `hi`: dense observations (every step, higher noise σ=0.25)

**Training**: Denoising score matching on trajectory windows (sizes 4 and 9 are tested).

**Inference**: Reverse SDE sampling, conditioned on observations via Langevin dynamics.

## reference
- Rozet & Louppe (2023): [Score-based Data Assimilation](https://arxiv.org/abs/2306.10574)



