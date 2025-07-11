# CarRacing-v3-DQN-Agent

⚠️ This side project is meant for educational exploration only. No benchmark claims here.

An avg 800 Deep Q-Network agent for OpenAI CarRacing-v3 (domain_randomize=True)

In this side project, I only focus on the DQN approach instead of using PPO or more advanced techniques. I put some constraints on myself: NO PPO, just DQN. The original purpose is to test the possible performance of a DQN structure. It is interesting to know that there is something called RainbowDQN, but I don't have the source code. So I decided to build my own DQN agents. In general, I used the common skills: multiple-step, prioritization, frame-stacking, lite reward shaping (only punishing `do-nothing`), dynamically switching the memory, contrast enhancement, residual-CNN, multiple CNN branches (I leave a gate for merging), duelling (Advantage and Value), double network, ensemble Q-head, Dropout in Q-head, multiple type Q-head... Some of those modules were not used, but I planned to test them in the future. 

For some reason, I used multiple Q-heads to mimic the distributional-Q technique, and I used the dropout to mimic the noisyNet. Ok, the reason is here: If I used distributional-Q, I have to modify the loss function. I used `huber` for simplicity, so I decided not to do that. And I know that NoisyNet can generate some internal exploration, which is used to replace the epsilon (exploration rate), but this will cause some issues for me to analyse. For analysis, I plan to test the model's weights by using some tricks like perturbation and instability tests. 

The agent's ability will depend on its training history, so if you run it on your computer, you will find it deviates from mine. In evaluation, I suggest testing the agent on two cases: (1) `model_trainable = False` and (2)  `model_trainable = True`. You will see something different. 

In some VERY challenging cases, the agent's policy could collapse. After I checked the GIF file, I found that the visual blocks are a possible cause: the agent is blind. 

For some reason, in this project, I just want to focus on the model structure and some strategies. So, for the same reason, something minor is helped by our friend, GPT-4o. In the headline of the notebook, I put some meditation notes, just because I want to write something while waiting for the training process. In the future, I will keep updating this notebook and add some analysis blocks and visualisation. You can think of this one as a learning notebook. 

## Demo

**Demo GIF**
![episode_010-929](https://github.com/user-attachments/assets/07ddd52c-6c09-43a9-8940-a9306d731902)


**Evaluation**
![image](https://github.com/user-attachments/assets/24559bb2-ef33-4371-8bdd-ac647ea1f5ea)

##Google Drive of Demo GIF**

[1000_DQN_Agent_Demo](https://drive.google.com/drive/folders/1TuAjSsODtwtL4aF0R1HKaJ8DeT8hMG7z?usp=sharing)


## HOW to USE?
- You can download the notebook and run it on your local computer (I used my MacBook Air M2)
- You can change the number of training episodes ( I used 20,000 )
- CAVEAT: if the training episode number > 20,000, it is possible that policy collapse occurs (I encountered once)
- If you want to run it on your laptop, the training time is estimated from 1 day to 1 week (depends on your computer)
- If you don't want to run it, you can download my model from this link [DQN_model](https://drive.google.com/file/d/1j4Q2jzIQVRlxmR6Kgz3QRvbOsZfiS8ha/view?usp=sharing)
- If you want to test it, you can used the evaluation loop in the notebook (just load the model)

## Features

- ✅ Full Keras implementation (no black-box)
- ✅ Modular & Annotated
- ✅ Uses multi-head dueling DQN
- ✅ Domain randomized training environment
- ✅ Average reward ~ 800 in 100 episodes in `domain_randomize = True`

You can check it on the notebook. [Link](https://github.com/AeneasWeiChiHsu/CarRacing-v3-DQN-/blob/main/Avg%20800%20Car%20Racing%20v3%20Randomize%20%3D%20True%20DQN%20Agent.ipynb)

You can check the GIF files in my Google Drive folder. [Link](https://drive.google.com/drive/folders/1nFQOGM08ElQ55bbsqEr1i_gm19PN0oaz?usp=sharing)

You can also download the model on Kaggle. [DQN_Model](https://www.kaggle.com/models/weichihsu1996/dqn-model-on-car-racing-v3-random-environment)

You can find a mini article describing this agent in the Repo. 



[A Keras-Based DQN Agent Achieving 800+ Average Reward in CarRacing-v3 with Domain Randomization](https://www.researchgate.net/publication/392966784_Backup-PreprintA_Keras-Based_DQN_Agent_Achieving_800_Average_Reward_in_CarRacing-v3_with_Domain_Randomization)

## Requirements

- Python 3.10+
- TensorFlow 2.15+
- OpenAI Gym (`CarRacing-v3`)

## Contact

If you find anything incorrect or interesting, please let me know. Feel free!
And if you have some interesting problems, I would be very happy to hear about them. Perhaps we can co-work on it.

## In The Future
I will upload some notes to explain how I design it.


**`weichihsu1996[at]gmail[dot]com`**

Well, it is a nice journey into Reinforcement Learning. 

---
Now the 100-episode evaluation GIF folder is available:
https://drive.google.com/drive/folders/1ta49u3dJXLZp8NUjI8j90IPIOtuB1nde?usp=sharing
