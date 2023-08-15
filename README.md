# Multi-Agent Reinforcement Learning with Emergent Communication for Mixed-Motive Environments

## Repo content

In this repository I implemented two pettingzoo environments for two different versions of the Public Good Game, and PPO reinforcement learning agents that can solve the game with and wthout communication. 

Under the "src" folder you can find:
* in the "environments" the implementations of the two environments, with versions v0 and v1. Both the parallel and sequential Pettingzoo versions are available.
* in the "nets" folder you can find an implementation of the different kind of architectures for the agents playing the game
* in the "algos" folder you can find the implementations of the learning algorithms, which are different versions of the PPO (Proximal Policy Optimization) algorithm. The different versions allow to train different kind of networks, creating different losses given the different network outputs.
* in the "analysis" folder you can find the implementation of different function to analyse the bahavior of the RL agents during and after training
* in the "experiments_pgg_v0" and "experiments_pgg_v1" fodlers you can respectively find the training mains for the different kind of reinfrocement learning agents that solve the two games.

Different kind of agents with different abilities have been implemented: they can or cannot communicate, and agents that can or cannot memorize older actions and messages. All of them are trained using the Proximal Policy Optimization algorithm.


## How to use:

---

create a virtual environment as follows:

```bash
python3 -m venv env

```
and activate it:

```bash
source env/bin/activate

```
Don't forget to update pip:


```bash
pip install --upgrade pip

```

Install the setup file as follows (the -e options allows to change the code while using it):

```bash
pip install -e .
```

Install the required packages:

```bash
pip install -r requirements.txt
```

Install torch, i.e.:

```bash
pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cpu
```

Example to run the training with chosen parameters, in the scenario with 2 agents, bidirectional communication, and no uncertainty:

```bash
python3 caller_given_params.py --n_agents 2 --mult_fact 0.5 3.5 --uncertainties 0 0 --communicating_agents 1 1 --listening_agents 1 1 --gmm_ 0 0 --batch_size 128 --lr_actor 0.002866 --lr_actor_comm 0.07527 --n_hidden_act 2 --n_hidden_comm 1 --mex_size 2 --hidden_size_act 32 --hidden_size_comm 8 --sign_lambda 0. --list_lambda 0.
```
