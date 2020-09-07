stable baselines

stable baselines是一组基于OpenAI Baselines 的改进版，用于实现强化学习算法



安装

```
pip install stable-baselines
```



示例：在Cartpole环境中训练和运行PPO2

```
import gym

#Multilayer Perceptron MLP多层感知器，深度学习中的神经网络结构
#Policy策略
#PPO2算法 深度强化学习算法
from stable_baselines.common.policies import MlpPolicy
from stable_baselines.common.vec_env import DummyVecEnv
from stable_baselines import PPO2

env = gym.make('CartPole-v1')
#算法需要一个向量化的环境
env = DummyVecEnv([lambda: env])  

model = PPO2(MlpPolicy, env, verbose=1)
#学习
model.learn(total_timesteps=10000)

obs = env.reset()
for i in range(1000):
    action, _states = model.predict(obs)
    obs, rewards, dones, info = env.step(action)
    env.render()

```

