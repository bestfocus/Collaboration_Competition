# Collaboration_Competition
This is for completing the Udacity Deep Reinforcement Learning Project 3.

## Project Details
This project contains two agents playing a tennis ball in the Unity ML-Agents Tennis environment. The goal of each agent is to keep the ball in play.
 1.	Agents: Two agents control rackets to bounce a ball over a net.
 2.	Actions: Each agent can move horizontally and vertically. Each action has 2 numbers in the range between -1 and 1 corresponding to the 2 dimensions.
 3.	States: States include observations at 3 consecutive time steps for each of the 2 agents. Each agent receives its observation of locations and velocities of itself and the ball represented by 8 components. Each episode has multiple time steps, and a state vector of 2*24 is generated at each step. Each row of the state vector is for an agent, and represents locations and velocities of the agent and the ball in a rolling window of 3 steps: two previous time steps and the current time step. The observation at each step includes 8 components: first 2 components are the 2-d coordinates of the racket location where the coordinate center is the net top, the components 3 and 4 are the velocity coordinates for the ball, the components 5 and 6 are the coordinates of the ball location, the components 7 and 8 are the same as components 3 and 4. When the racket and the ball have similar location values, the racket hits the ball and the ball starts to change its direction.
 4.	Rewards: The task is episodic. After the ball is hit back and moves over the net, if it’s expected to hit within bounds, a reward 0.1 is given to the agent. If the ball hits the ground or is expected to be out of bounds, a reward if -0.01 is given to the agent. There is no limit of rounds for each episode if the agents can keep the ball in play.
 5.	Done: the ball stops.
 6.	Solve the environment: After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 2 (potentially different) scores. We then take the maximum of these 2 scores. This yields a single score for each episode. In order to solve the environment, agents must get an average score of +0.5 (over 100 consecutive episodes, after taking the maximum over both agents).

## Getting Started
The code is written in Python 3 and PyTorch. Instructions for installing dependencies or downloading needed files for Windows, Linux or Mac are provided on https://github.com/udacity/deep-reinforcement-learning#dependencies. The process is summarized as follows:
 1. Download AnaConda3
 2. Open the AnaConda Powershell Prompt to enter the following commands to create and activate a new env "drlnd" using an old Python version 3.6 required by this project:
    * Windows:
    ```
    conda create --name drlnd python=3.6
    conda activate drlnd
    ```
    * Linux or Mac:
    ```
    conda create --name drlnd python=3.6
    source activate drlnd
    ```
 3. In the new env "drlnd", run the following to install the old PyTorch version for installing Unity provided by Udacity:
    ```
    conda install pytorch=0.4.0 -c pytorch
    git clone https://github.com/udacity/deep-reinforcement-learning.git
    cd deep-reinforcement-learning/python
    pip install .
    ```
 4. Create an IPython kernel for the drlnd environment:
    ```
    python -m ipykernel install --user --name drlnd --display-name "drlnd"
    ```
## Instructions
The instructions for running the code are provided below. 
 1. Replace the notebook Tennis.ipynb in deep-reinforcement-learning/p3_collab-compet with the code given here and also copy model.py and agent.py to the same folder.
 2. Download files:
    - For Windows 64-bit: https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86_64.zip
    - For Windows 32-bit: https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86.zip
    - For Linux: https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux.zip
    - For Mac OSX: https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis.app.zip
 3. Unzip the zip file to get a folder and place the folder in the same p3_collab-compet folder.
 3. Open Jupyter Notebook.
 4. On Notebook, open Tennis.ipynb and select drlnd in the Kernel.
 5. Run the code in each cell. The results for the weights are stored in the checkpoint_actor.pth and checkpoint_critic.pth files. The scores per episode are shown in a plot in the Notebook. The environment with the tennis court is shown in another window. The training will take more than 3 hours with GPU.
 6. After the environment is sovled, the environment is closed and the project is completed.
