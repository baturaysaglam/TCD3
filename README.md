# Estimation Error Correction in Deep Reinforcement Learning for Deterministic Actor-Critic Methods
PyTorch implementation of the _Triplet Critic Delayed Deep Deterministic Policy Gradient_ algorithm (TCD3). 
Note that the implementation of the TD3 algorithm is heavily based on the [author's Pytorch implementation of the TD3 algorithm](https://github.com/sfujim/TD3). 

The [paper](https://arxiv.org/abs/2109.10736#) was presented at [IEEE International Conference on Tools with Artificial Intelligence (ICTAI) 2021](https://ictai.computer.org/). The presentation slides and video are found under [./Presentation](https://github.com/baturaysaglam/TCD3/tree/main/Presentation). If you use our code or data, please cite the [paper](https://arxiv.org/abs/2109.10736#).

The algorithm is tested on [MuJoCo](https://gym.openai.com/envs/#mujoco) and [Box2D](https://gym.openai.com/envs/#box2d) continuous control tasks.

### Computing Infrastructure
Following computing infrastructure is used to produce the results.
| Hardware/Software  | Model/Version |
| ------------- | ------------- |
| Operating System  | Ubuntu 18.04.5 LTS  |
| CPU  | AMD Ryzen 7 3700X 8-Core Processor |
| GPU  | Nvidia GeForce RTX 2070 SUPER |
| CUDA  | 11.1  |
| Python  | 3.8.5 |
| PyTorch  | 1.8.1 |
| OpenAI Gym  | 0.17.3 |
| MuJoCo  | 1.50 |
| Box2D  | 2.3.10 |
| NumPy  | 1.19.4 |

### Usage
```
usage: main.py [-h] [--policy POLICY] [--env ENV] [--seed SEED] [--gpu GPU]
               [--start_time_steps N] [--buffer_size BUFFER_SIZE]
               [--eval_freq N] [--max_time_steps N] [--exploration_noise G]
               [--batch_size N] [--discount G] [--tau G] [--policy_noise G]
               [--noise_clip G] [--policy_freq N] [--save_model]
               [--load_model LOAD_MODEL]
```

### Arguments
```
optional arguments:
  -h, --help            show this help message and exit
  --policy POLICY       Algorithm (default: TCD3)
  --env ENV             OpenAI Gym environment name
  --seed SEED           Seed number for PyTorch, NumPy and OpenAI Gym (default: 0)
  --gpu GPU             GPU ordinal for multi-GPU computers (default: 0)
  --start_time_steps N  Number of exploration time steps sampling random actions (default: 1000)
  --buffer_size BUFFER_SIZE Size of the experience replay buffer (default: 1000000)
  --eval_freq N         Evaluation period in number of time steps (default: 1000)
  --max_time_steps N    Maximum number of steps (default: 1000000)
  --exploration_noise G Std of Gaussian exploration noise
  --batch_size N        Batch size (default: 256)
  --discount G          Discount factor for reward (default: 0.99)
  --tau G               Learning rate in soft/hard updates of the target networks (default: 0.005)
  --policy_noise G      Noise added to target policy during critic update
  --noise_clip G        Range to clip target policy noise
  --policy_freq N       Frequency of delayed policy updates
  --save_model          Save model and optimizer parameters
  --load_model LOAD_MODEL Model load file name; if empty, does not load
  ```


### Bibtex
```
@INPROCEEDINGS{9643358,
    author={Saglam, Baturay and Duran, Enes and Cicek, Dogan C. and Mutlu, Furkan B. and Kozat, Suleyman S.},
    booktitle={2021 IEEE 33rd International Conference on Tools with Artificial Intelligence (ICTAI)},
    title={Estimation Error Correction in Deep Reinforcement Learning for Deterministic Actor-Critic Methods},
    year={2021},
    volume={},
    number={},
    pages={137-144},
    doi={10.1109/ICTAI52525.2021.00027}
}
```
