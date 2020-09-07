## 构建GYM场景



### 地图

在数据库中直接修改数据,只要保证主键一致就行

主键

tb_hexmap:tf_hm_id

tb_hexmap_data:tf_hmd_id



### 想定

只需要修改  `name `和 `id` 的值就可以了

数据库想定的表:tb_scenario



### 环境

##### nwpu同级的init注册

```
register(
    id='SimuWRTEnv_Scenario3_3-v0',	//环境id码
    entry_point='gym.envs.nwpu:SimuWRTEnv_Scenario3_3',	//环境文件夹路径:类名
    max_episode_steps=200,
    reward_threshold=100.0,
)
```

##### nwpu下的init注册

```
from gym.envs.nwpu.SimuWRTEnv_Scenario3_3_y import SimuWRTEnv_Scenario3_3_y 
# 从环境文件夹路径.环境文件 导入 类名
# scenario 3, graph is 3*3
```

### 训练

训练中的环境创建使用的是环境的ID,利用**环境ID**找到

```
register(
    id='SimuWRTEnv_Scenario3_3-v0',	//环境id码
    entry_point='gym.envs.nwpu:SimuWRTEnv_Scenario3_3',	//环境文件夹路径:类名
    max_episode_steps=200,
    reward_threshold=100.0,
)
```

中的**环境类名**,再**利用类名**找到**相应文件中的环境定义**

```
register(
    id='SimuWRTEnv_Scenario3_3-v0',	//环境id码
    entry_point='gym.envs.nwpu:SimuWRTEnv_Scenario3_3',	//环境文件夹路径:类名
    max_episode_steps=200,
    reward_threshold=100.0,
)
```



### 开始训练

先打开**MCP和UDS**可执行文件,再打开**web端控制台**设置任务,开始推演,最后打开**虚拟机**执行py文件