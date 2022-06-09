# CarPilotEnv
RL-based solution to driving a car over a slippery grid using Dyna-Sarsa algorithm

The car starts in the top leftcorner (x = 0, y = 0) facing South and receives a reward of 10 and terminates a training episode if it loops counterclockwise around the grip map and transitions from cell position (x = 1, y = 0) to the starting cell. The agent’s absolute orientations and action set are encoded in CarMDP as: 

$$ orientations = 0: North, 1: East, 2: South, 3: West $$

$$ actions = 0: Forward, 1: Left, 2: Right, 3: Brake $$

The agent’s complete state at each time step is encoded as the 3-element tuple (x, y, Orientation). For example, the starting state S0 is encoded (0, 0, 2).

The environment model is a 9-by-6 grid map, outside of the fixed grid map is considered as terminal “crash” state that reward a penalty of −5. Any other non-terminating action receives a penalty of −0.01. The discount factor is 1. Initially, the agent has no knowledge of the environment model. The agent can gradually learn the environment model based on its real experience over time.
