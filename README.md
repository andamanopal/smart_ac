# SmartAC with OpenAI Gym
(Part of SuperAI Season 2 qualification process, first round)
This Python notebook consists of how we can create a custom environment for reinforcement learning training in a super simple way using custom environment class from OpenAI Gym Python library. The project was used to record a video for first-round submission during SuperAI Engineer Season 2 (2022), arranged by AIAT, Thailand.

## Custom RL Environment with OpenAI Gym
To properly create a custom environment for single-agent RL environment, below is the list of attributes/properties that are needed to be defined to simulate the characteristics of the environment
- Environment initial condition
- Step function (how environment is affected after an agent takes an action)
- Reward function (what is the criterion to separate good actions from bad actions)
- Observation space (to what extent our agent can see)
- Action space (to what extent our agent can do)

## Case Study : SmartAC
In this mini-project, a case study of Smart airconditioner which can automatically adjust the temperature based on the current room temperature is replicated by OpenAI Gym API as above. 

For simplicity, the possible temperature range is a range of integers from 0 to 99 degrees. The optimum temperature range where the occupants will feel most comfortable is between 23-25 degrees. After each timestep, the temperature can randomly changed due to heat transfer or any other uncontrollable external factors. The goal of our SmartAC is to be able to maintain the room temperature within the optimum range.

![](/images/smart_ac.png)

Using the reward function which gives negative score when the temperature violates the optimum range, our SmartAC is trained by PPO algorithm imported from Stable-Baselines3 and the result between trained and non-trained models from multiple episodes are shown as below histogram. It can be seen that our SmartAC has successfully learn how to better maintain the temperature to reduce the number of timesteps that the temperature isn't within the proper range.

![](/images/trained_vs_non-trained.png)

Note: Huge thanks to Nicolas Renotte for such a wonderful tutorial on Reinforcement Learning with OpenAI Gym ![Reinforcement Learning in 3 Hours | Full Course using Python](https://youtu.be/Mut_u40Sqz4)
