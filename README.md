# Lunar Lander Deep Q-Network from OpenAI Gymnasium!
<img width="597" alt="image" src="https://github.com/ghubnerr/LunarLander_Test/assets/91924667/4ce98099-81b7-4d64-9bff-7166dbfab970">

<hr>

"This environment is a classic rocket trajectory optimization problem. According to Pontryagin’s maximum principle, it is optimal to fire the engine at full throttle or turn it off. This is the reason why this environment has discrete actions: engine on or off.
There are two environment versions: discrete or continuous. The landing pad is always at coordinates (0,0). The coordinates are the first two numbers in the state vector. Landing outside of the landing pad is possible. Fuel is infinite, so an agent can learn to fly and then land on its first attempt."

### [Documentation: Gymnasium](https://gymnasium.farama.org/environments/box2d/lunar_lander/) 

### Usage and Packages
`pip install torch gymnasium 'gymnasium[box2d]'`


You might need to install Box2D Separately, which requires a `swig` package to compile code from Python into C/C++, which is the language that Box2d was built in:
 
`brew install swig`

`pip install box2d`

### Average Score: 137.91
For each step, the reward:
- is increased/decreased the closer/further the lander is to the landing pad.
- is increased/decreased the slower/faster the lander is moving.
- is decreased the more the lander is tilted (angle not horizontal).
- is increased by 10 points for each leg that is in contact with the ground.
- is decreased by 0.03 points each frame a side engine is firing.
- is decreased by 0.3 points each frame the main engine is firing.

The episode receive an additional reward of -100 or +100 points for crashing or landing safely respectively. An episode is considered a solution if it scores at least 200 points.**

### `land()` and `learn_to_land()`
`land()` function loads a pre-trained model that ran through 500 episodes of training, while `learn_to_land()` does training from scratch. You can edit which one of the functions is running from the bottom of the `main.py` file. If you set `render_mode=False`, the program will train a lot faster.
