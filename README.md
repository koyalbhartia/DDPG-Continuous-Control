# DDPG-Continuous-Conrol
Reinforcement Algorithm with DDPG 
In this Unity environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible.

Below is a glimpse of the model being trained.

https://user-images.githubusercontent.com/40532456/124547175-5d790080-ddf1-11eb-9c49-1bee663811b4.mp4

To train your own model and understand how the Agent works, refer to the below file:

[Continuous Control](https://github.com/koyalbhartia/DDPG-Continuous-Control/blob/main/Continuous_Control/Continuous_Control.ipynb)

The saved trained model can be found here:

[Actor Model](https://github.com/koyalbhartia/DDPG-Continuous-Control/blob/main/Continuous_Control/checkpoint_actor.pth)
[Critic Model](https://github.com/koyalbhartia/DDPG-Continuous-Control/blob/main/Continuous_Control/checkpoint_critic.pth)

## Setup environment:

1. First we have to install conda once the conda is installed we need to update the bash script.  [Install anaconda](https://docs.anaconda.com/anaconda/install/linux/).
Other tools used in the project are Python 3.6, PyTorch, NumPy, UnityEnvironment package and Matplotlib


2. Run the following commands in the terminal.
```
conda create --name drlnd python=3.6
source activate drlnd
```

3. Clone this repo :
```
git clone https://github.com/koyalbhartia/DDPG-Continuous-Control
```

4. Install python dependencies:
```
cd DDPG-Continuous-Control/python
pip install .
```

5. Setup drlnd environment :
```
python -m ipykernel install --user --name drlnd --display-name "drlnd"
```
6. Open Jupyter noetbook to start learning and experimenting :

```
cd DDPG-Continuous-Control/Continuous_Control
jupyter notebook
```

**Note : Do not forget to select Kernal >> Change kernal >> drlnd**

7. Edit the location of Banana linux in code cell 2 with your username and run the notebook( Hit  **Shift + Enter**) 


## Overall Results :

![Screenshot from 2021-07-06 00-25-06](https://user-images.githubusercontent.com/40532456/124546772-c14ef980-ddf0-11eb-918f-f172372dffa7.png)

