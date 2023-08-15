# RLGym-PPO
A vectorized implementation of PPO for use with [RLGym](https://github.com/lucas-emery/rocket-league-gym).

## INSTALLATION
`pip install git+https://github.com/AechPro/rlgym-ppo`
Be warned that this will install the CPU version of PyTorch by default. If you would like to use a GPU
make sure you manually install [PyTorch with CUDA](https://pytorch.org/get-started/locally/). If you already
installed this project you will need to `pip uninstall torch` before reinstalling with CUDA.

## USAGE
Simply import the learner with `from rlgym_ppo import Learner`, pass it a function that will return an RLGym environment
and run the learning algorithm. A simple example follows:
```
from rlgym_ppo import Learner

def my_rlgym_function():
    import rlgym_sim
    return rlgym_sim.make()

learner = Learner(timestep_limit=50_000_000)
learner.learn(my_rlgym_env_function)
```
Note that users must implement a function to configure Rocket League (or RocketSim) in RLGym that returns an 
RLGym environment. See the `example.py` file for an example of writing such a function.
