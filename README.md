# 🎨 CompLift: Improving Compositional Generation with Diffusion Models

<p align="center">
<img src="text-to-image/figures/accepted_vs_rejected.png" width="800px"/>
<br>
Our CompLift approach offers a straightforward solution to improve diffusion models without any extra training. When using regular diffusion models (shown above), combining multiple concepts in one generation often results in missing or incorrectly rendered elements. CompLift solves this problem by introducing a smart rejection way that measures how well each generated sample matches the individual intended components in the prompt, which we call the Lift Score. For more details, please refer to our paper.
</p>

## 📋 Overview

This repository contains the official implementation of *Improving Compositional Generation with Diffusion Models Using Lift Scores*. The project is split into two main components:

1. **🎯 2D and CLEVR Tasks** ([2d-and-clevr/](https://github.com/rainorangelemon/complift-2d-and-clevr)): Implementation for synthetic 2D tasks and CLEVR position tasks.
2. **🖼️ Text-to-Image Generation** ([text-to-image/](https://github.com/rainorangelemon/complift-t2i)): Implementation for improving compositional generation in text-to-image diffusion models like Stable Diffusion.

Note: the SAM2 folder is only used for the CLEVR task. See the [CLEVR README](https://github.com/rainorangelemon/complift-2d-and-clevr#2-evaluate-samples-using-sam2) for more details.

## 🔗 Quick Links

- [📚 2D and CLEVR Documentation](https://github.com/rainorangelemon/complift-2d-and-clevr)
- [📚 Text-to-Image Documentation](https://github.com/rainorangelemon/complift-t2i)
- [📓 2D Tasks Colab Notebook](https://colab.research.google.com/drive/1bVjGY-ym67CV8FiUxxkaMpbkWg9EQGcd?usp=sharing)
- [📓 CLEVR Tasks Colab Notebook](https://colab.research.google.com/drive/1JPm_N8NThABc5jZmgiTB4RWnNUkKp491?usp=sharing)
- [📓 Text-to-Image Colab Notebook](https://colab.research.google.com/drive/1bVjGY-ym67CV8FiUxxkaMpbkWg9EQGcd?usp=sharing)

## ✨ Key Features

- **🚀 No Extra Training Required**: CompLift improves diffusion models without requiring additional training.
- **🎯 Smart Rejection Mechanism**: Measures how well generated samples match their intended descriptions.
- **🔄 Multiple Model Support**: Works with various diffusion models including Stable Diffusion 1.4, 2.1, and XL.
- **📊 Comprehensive Evaluation**: Includes both synthetic 2D tasks and real-world CLEVR position tasks.
- **🎮 Easy to Use**: Provides Jupyter notebooks for quick experimentation and familiarization.

## 🛠️ Installation

Each component has its own installation requirements. Please refer to the respective README files:

- [📥 2D and CLEVR Installation](https://github.com/rainorangelemon/complift-2d-and-clevr#-installation)
- [📥 Text-to-Image Installation](https://github.com/rainorangelemon/complift-t2i#setup)

## 💻 Example Usage

### 🎨 2D Tasks

```bash
# Train models
bash 2d-and-clevr/scripts/train_2d.sh

# Evaluate baselines
python -m 2d-and-clevr/scripts.run_baselines_2d
```

### 🎯 CLEVR Tasks

```bash
python -m 2d-and-clevr/scripts.run_baselines_clevr +method=METHOD experiment_name=YOUR_EXPERIMENT_NAME num_constraints=NUM_CONSTRAINTS num_samples_to_generate=NUM_SAMPLES_TO_GENERATE
```

### 🖼️ Text-to-Image Generation

```bash
python text-to-image/run.py --prompt "a cat and a dog" --seeds [0] --sd_xl=True --run_standard_sd=True --save_intermediate_latent=True --output_path "outputs/example"
```

For detailed usage instructions, please refer to the respective component READMEs.
- [📥 2D and CLEVR Usage](https://github.com/rainorangelemon/complift-2d-and-clevr#-2d-synthetic-dataset--)
- [📥 Text-to-Image Usage](https://github.com/rainorangelemon/complift-t2i#usage)

## 📝 Citation

If you use this code for your research, please cite our work:

```bibtex
```

## 🙏 Acknowledgements

- [Attend-and-Excite](https://github.com/AttendAndExcite/Attend-and-Excite)
- [Diffusion Classifier](https://github.com/diffusion-classifier/diffusion-classifier)
- [diffusers](https://github.com/huggingface/diffusers)
- [Prompt-to-Prompt](https://github.com/google/prompt-to-prompt/)
- [SAM2](https://github.com/facebookresearch/sam2)
- [tiny diffusion](https://github.com/tanelp/tiny-diffusion)
- [MCMC for Diffusion Models](https://github.com/yilundu/reduce_reuse_recycle)
- [Composable Diffusion](https://github.com/energy-based-model/Compositional-Visual-Generation-with-Composable-Diffusion-Models-PyTorch)
