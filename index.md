[Overview](#overview)

[Ontology](#ontology)

[Language Understanding](#language-understanding)

[Dailogue Management](#dialogue-management)

[Natural Language Generation](#natural-language-generation)

# Overview

If you are not so familiar with PTT, don’t worry! Our PTT-BOT is here for you.
With it, you are going to be a professional villagers!(鄉民)
Here are some functionalities you must try!

(1) BOT Full Of Emotion
The greeting and the reply of our BOT will adjust bdfased on the facial expression of the
user.

(2) Search Desired Posts For U
Our BOT can search for related posts according to the information provided by
users.

(3) 「Search Desired Board For U 」
Often having no idea what board it has/which board to find the things/topics you want ?
Our BOT can recommend related board according to the keywords.

(4) 「Track Users U R Interested In」
Our BOT can find shared accounts of the same user. (找分身)

(5) 「Customized Features and So on...」
Wait for you to Discover !

(6) 「All Chat-BOTs IN THIS ONE PTT-BOT 」
Support multi-domain Searching :Moive, Music, Course, Stock, Food, Job...etc

# Ontology

# Language Understanding

# Dialogue Management

### Model architecture: Reinforcement Learning (RL)-Deep-Q learning (DQN)

- We take Keras-rl and GYM as our reference to build our model.

- RL states: The NLU turns the sentences from simulated user (environment) into observation, in which we extract our desired states as the input of the agent.

- Action: The policy in DQN agent is Boltzmann Q policy, and the behavior is trained by the reward given by the simulated user.

### User Simulator

- When an instance of simulated user is created, it will own a semantic frame itself, where
the intent is randomly picked, and in each intent, the instance will have a corresponding
semantic frame.

- For example, When the simulated user wants to request post, the semantic frame of this instance includes (i) board (ii) key words (iii) # of pushes.

### Success rate / Reward
- Setting:
(a) The user will check if the intents in the semantic frame is
matched. If it’s matched, the user will give BOT a positive
reward, otherwise, negative.

(b) The Bot will pass the action to the user, and the user will
determine if this action is appropriate in this dialogue case to give the responding reward.

(c) If the BOT has already received the information which has been told before, but it asked
repeatedly, it will also get a negative reward.

(d) If the BOT outputs the result once it gets enough information, it will get a relatively
positive reward.

# Natural Language Generation
