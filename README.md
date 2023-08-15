# Multi-Agent Reinforcement Learning with Emergent Communication for Mixed-Motive Environments

## Repo content

This repository contains the code used for to the paper "Emergent Cooperation and Deception in Public Good Games"

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

You can also run hyperparameter search via optuna, using for example:

```bash
python3 caller_optuna.py --n_agents 2 --mult_fact 0.5 3.5 --uncertainties 0 0 --communicating_agents 1 1 --listening_agents 1 1 --gmm_ 0 0 --optimize 1
```

When the hyperparameter search is completed, you can run the training using the best hyperparameters found by optuna setting the parameter ```optimize``` to 0.
