# gym_vecenv
Python3 wrapper for running multiple OpenAI Gym environments in parallel

## Difference in this fork
In the original repo, each env is auto reset if one of the agents in the env returns `done`. In this fork, `info['terminal_observation']` will contain the terminal observation for an env if it is auto reset. 

All the code is from [OpenAI Baselines Repository](https://github.com/openai/baselines)

The parallel environment functionality was the only reason I used Baselines, but installing it requires resolving MuJoCo, mujoco-py and various other dependencies which is troublesome. Hence, I repackaged the required functionality into another package which is very easy to install and exposes the same API

Requirements (resolved automatically during installation):
1. `Python 3`
2. `OpenAI Gym`
3. `Cloudpickle`
4. `numpy`

Installation: Easiest way is to do `pip install gym_vecenv`

If you want to build from source,

1. Clone this repository
2. `cd gym_vecenv`
3. `pip install -e .`

Usage:

1. `import gym_vecenv` and then call `gym_vecenv.SubprocVecEnv` or `gym_vecenv.DummyVecEnv` in your code

2. `from gym_vecenv import SubprocVecEnv, DummyVecEnv` etc.
