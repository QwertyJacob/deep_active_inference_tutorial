# Deep Active Inference Tutorial  


---
A (hopefully) simple & visual introduction to **Active Inference** in continuous partially-observable environments using PyTorch
---

![](figs/actinfcover.jpg)
<p align="center">
  <img src="https://img.shields.io/badge/PyTorch-2.x-orange?style=flat&logo=pytorch" alt="PyTorch">
  <img src="https://img.shields.io/badge/Active%20Inference-Deep%20Learning-blue?style=flat" alt="Active Inference">
  <img src="https://img.shields.io/badge/Status-Work%20in%20Progress-yellow?style=flat" alt="WIP">
</p>

## What is this?

This repository contains a **step-by-step Jupyter notebook tutorial** that walks you through building a **deep active inference agent** from scratch in a simple 2D gridworld with noisy observations.

The agent learns to:

- Infer hidden states from noisy GPS-like observations (**variational perception**)
- Act to reach a goal location (**pragmatic value**)
- Occasionally use a "Hint" action to reduce uncertainty (**epistemic value**)
- Balance exploration and goal-directed behaviour via the **Expected Free Energy (EFE)**

All of this is implemented using **three small neural networks**:

- Posterior network → state inference (minimising variational free energy complexity)
- Critic network → learns to predict EFE (temporal difference learning)
- Policy network → selects actions by matching a Gibbs/soft-max distribution over predicted EFE

## Key Learning Outcomes

By the end of the notebook you will have seen / implemented:

- Generative process vs. generative model
- Markov blankets & conditional independencies in POMDPs
- Variational free energy (VFE) minimisation for perception
- Expected free energy (EFE) decomposition: epistemic + pragmatic
- Gibbs sampling policy from negated EFE
- Experience replay for stable joint training of all components
- Live visualisation of learning trajectories on the grid

## Notebook Structure (main sections)

1. Markov Decision Processes → POMDPs  
2. Generative process vs. generative model  
3. Variational inference & Free Energy principle  
4. Expected Free Energy (EFE) derivation  
5. Gaussian approximation trick for KL terms  
6. Independent training of posterior, policy (proxy EFE), and critic  
7. Introduction to experience replay  
8. Full joint training loop with live trajectory visualisation  
9. Final test episode – watch the trained agent!

## Requirements

```bash
pip install torch numpy matplotlib collections
```

(Should run fine in Google Colab or any local Jupyter environment with PyTorch.)

## How to use

1. Open the notebook  
   [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/QwertyJacob/deep_active_inference_tutorial/blob/main/main.ipynb)

2. Run cells sequentially — everything is self-contained

3. Watch how random behaviour slowly turns into goal-directed + curious behaviour

## Future / Wishlist

- Continuous action spaces
- Prioritized experience replay (PER)
- Multi-step EFE horizons
- More complex environments (e.g. POMDP with partial walls)
- Comparison with PPO / DQN baselines

## Citation / Attribution

If you find this tutorial helpful in teaching, research, or self-study, feel free to star the repo or drop me a line.  
No formal citation needed — just happy to help spread active inference!

```text
@misc{cevallos2025-deep-active-inference-tutorial,
  author = {Jesus F. Cevallos-Moreno},
  title  = {A hopefully simple tutorial on Active Inference for continuous PO-MDPs},
  year   = {2026},
  url    = {https://github.com/QwertyJacob/deep_active_inference_tutorial.git}
}
```


Happy inferring! 🧠🌍

---
Last updated: March 2026

[![ORCID](https://img.shields.io/badge/ORCID-0000--0003--2752--4616-A6CE39?style=for-the-badge&logo=orcid&logoColor=white)](https://orcid.org/0000-0003-2752-4616)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-jesuscevallos-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/jesuscevallos/)
[![Twitter](https://img.shields.io/badge/X-@JesusCevallos9-000000?style=for-the-badge&logo=x&logoColor=white)](https://x.com/JesusCevallos9)
[![Website](https://img.shields.io/badge/Website-dista.uninsubria.it-FF6B6B?style=for-the-badge&logo=google-chrome&logoColor=white)](http://www.dista.uninsubria.it/~jesus.cevallos/)
[![Google Scholar](https://img.shields.io/badge/Google%20Scholar-4285F4?style=for-the-badge&logo=google-scholar&logoColor=white)](https://scholar.google.com/citations?user=26o39YMAAAAJ&hl=en)
