# Proximal Policy Optimization on a Unity Environment
*Solution to the third project on the Udacity Deep Reinforcement Learning Course*

## Introduction
This repo contains my solution to the third project in the Udacity Deep Reinforcement Learning Course: Collaboration and Competition. The Unity enviornment contains 2 tennis players that both follow the same policy. Their task is to keep the ball in play.

The reward function is as follows. For each agent, hitting the ball over the net gets a reward of +0.1. If the ball hits the ground or is outside the court, the reward is -0.01. 

Two continuous action variables control movement towards the net (the game is 2D not 3D) and a jumping motion.

The observations (local to each agent) are 8 continuous variables representing ball and racket state (from the agent’s point of view).

After each episode, the maximum score from the two agents is taken. This is then averaged over the last 100 episodes. When this trailing average passes +0.5, the task is considered solved.
The code uses the PPO (Proximal Policy Optimization) algorithm to arrive at a solution in 1500-1800 episodes.

This solution contains some new code to perform automated hyperparameter searches.

## Installation

To set up your python environment to run the code in this repository, follow the instructions below.

1. [Download and install Anaconda](https://www.anaconda.com/download/), if you don't already have it.


2. Create (and activate) a new environment with Python 3.6.

	- __Linux__ or __Mac__: 
	```bash
	conda create --name drlnd python=3.6
	source activate drlnd
	```
	- __Windows__: 
	```bash
	conda create --name drlnd python=3.6 
	activate drlnd
	```
	
3. Clone the repository and navigate to the root folder.  Then, install several dependencies.
```bash
git clone https://github.com/SimonBirrell/ppo-collaboration-and-competition.git
cd ppo-collaboration-and-competition
pip install .
```

4. Create an [IPython kernel](http://ipython.readthedocs.io/en/stable/install/kernel_install.html) for the `drlnd` environment.  
```bash
python -m ipykernel install --user --name drlnd --display-name "drlnd"
```

5. Run the notebook
```bash
jupyter notebook Navigation.ipynb
```

6. Before running the code in the notebook, change the kernel to match the `drlnd` environment by using the drop-down `Kernel` menu. You should only need to do this the first time. 

7. Download the environment from one of the links below.  You need only select the environment that matches your operating system:
    - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux.zip)
    - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis.app.zip)
    - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86.zip)
    - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86_64.zip)
    
    (_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

8. Place the file in the root directory of this repository and unzip (or decompress) the file. 

9. Run the code (by clicking the top cell and then using Shift-Enter to execute each cell in turn) right down to and including the "Train the Policy" cell but skipping the "Search for hyperparameters (optional)" cell. This should solve the environment in 1400-2000 episodes using the default hyperparameters. Make sure the Unity window is visible, as otherwise the simulation has atendency to pause itself.

10. To see the trained agent, then run the cell titled "Run the policy". Watch the Unity app window to see how well it performs.

11. To perform a full hyperparameter search, which takes around 27 hours, run the "Search for hyperparameters (optional)" cell.


