### Bellman期望方程的求解和算法基础课的完结

#### Bellman期望方程的求解

1. 学会原理之后，使用python sympy模块求解期望方程
2. **sympy.init_printing()**初始化打印环境
3. 定义符号**x, y = symbols('x y')**
4. 定义系数矩阵**sympy.Matrix()**函数
5. 求解线性方程组**solve_linear_system**

##### python代码

```
# 准备工作

import sympy
from sympy import symbols,pprint, Matrix
sympy.init_printing() # 找到合适的打印设备





# 定义要用到的符号

v_hungry, v_full = symbols('v_hungry v_full')
# 定义符号v(饿)，v(饱)
q_hungry_eat, q_hungry_none, q_full_eat, q_full_none = \
        symbols('q_hungry_eat q_hungry_none q_full_eat q_full_none')
# 定义符号q(饿，吃), q(饿，不吃), q(饱，吃), q(饱， 不吃) 
alpha, beta, gamma = symbols('alpha beta gamma')
# 定义符号 αβγ
x, y = symbols('x y')
# 定义符号 x, y





# 开始计算方程组

# 定义系数矩阵
system = sympy.Matrix((
        (1, 0, x-1, -x, 0, 0, 0),
        (0, 1, 0, 0, -y, y-1, 0),
        (-gamma, 0, 1, 0, 0, 0, -2),
        ((alpha-1)*gamma, -alpha*gamma, 0, 1, 0, 0, 4*alpha-3),
        (-beta*gamma, (beta-1)*gamma, 0, 0, 1, 0, -4*beta+2),
        (0, -gamma, 0, 0, 0, 1, 1) ))

# 使用solve_linear_system函数计算线性方程组
# 有三个参数：系数矩阵、待求向量 、 参数flags
result = sympy.solve_linear_system(system,
        v_hungry, v_full,
        q_hungry_none, q_hungry_eat, q_full_none, q_full_eat)


```



#### 算法基础课

1. 学完最后的stl和位运算后
2. 做完最后10道题



#### 总结

1. 用python代码实现了Bellman期望方程的求解
2. 学完了语法基础课
3. 再技术报告会中对Markov模型有了进一步的了解



