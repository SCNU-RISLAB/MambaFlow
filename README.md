# MambaFlow: A Novel and Flow-guided State Space Model for Scene Flow Estimation

[![arXiv](https://img.shields.io/badge/arXiv-2502.16907-b31b1b?logo=arxiv&logoColor=white)](https://arxiv.org/abs/2502.16907) 

## Notice

**This repository has been merged into a new repository.** For the latest features, updates, and developments, please visit [OpenSceneFlow](https://github.com/KTH-RPL/OpenSceneFlow). 

All future development work will be conducted in the new repository.

## Requirements

This code is based on Flow4D. <br>
Please follow the installation instructions from the [Flow4D repository](https://github.com/dgist-cvlab/Flow4D).

Additionally, you need to install `mamba-ssm 2.2.2`  and `causal-conv1d 1.4.0`.<br>
You can find the installation instructions here: [mamba](https://github.com/state-spaces/mamba).


## Training

To train the model, use the following command:

```bash
python 1_train_mambaflow.py
```


## Inference

To perform inference, use the following command:

```bash
python 2_eval_mambaflow.py checkpoint=path_to_checkpoint av2_mode=(val, test)
```

Replace `path_to_checkpoint` with the actual path to your checkpoint file and choose either `val` or `test`.

## Visualization

To visualize scene flow: 

1. Configure `conf/save.yaml` with model name, dataset path and weights path and use the following command to generate inference result:

   ```bash
   pathon save.py
   ```

2. Running following command to visualize scene flow:

   ```bash
   python tools/visualization.py --res_name 'your-method' --data_dir /path/to/dataset
   ```

- `--res_name` should match the name in `save.yaml`
- Ground truth will be generated if `--res_name` is not specified or set as `flow`


## Gratitude
This code is based on the [DeFlow code](https://github.com/KTH-RPL/DeFlow) by Qingwen Zhang and the [Flow4D code](https://github.com/dgist-cvlab) by dgist-cvlab.
We extend our sincere appreciation to both teams for their contributions. Special thanks to Kyle Vedder et al. for organizing and providing support throughout the [Argoverse2 2024 Scene Flow Challenge](https://www.argoverse.org/sceneflow.html).



