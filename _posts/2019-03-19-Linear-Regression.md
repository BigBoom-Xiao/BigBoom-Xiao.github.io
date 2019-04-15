<head>
    <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
    <script type="text/x-mathjax-config">
        MathJax.Hub.Config({
            tex2jax: {
            skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
            inlineMath: [['$','$']]
            }
        });
    </script>
</head>

# 线性回归算法

- 解决回归问题
- 思想简单，实现容易
- 是许多强大的非线性模型的基础
- 结果具有很好的可解释性
- 蕴含机器学习中的很多重要思想

## 简单线性回归

样本特征只有一个

假设我们找到了最佳和的直线方程：
$$y = ax + b$$
则对于每个样本点$$x^{(i)}$$
根据我们的直线方程， 预测值为：
$${\hat{y}}^{(i)} = ax^{(i)} + b$$
真值为：$$y^{(i)}$$

我们希望预测值和真值的差距尽量小，表达差距:

- 如果使用以下方式，可能会出现正负值抵消，不能很好的表达

$$y^{(i)} - {\hat{y}}^{(i)}$$

- 使用绝对值在寻找极值比较困难

$$|y^{(i)} - {\hat{y}}^{(i)}|$$

- x平方是个很好的函数，可抵消正负号问题，处处可导

$${(y^{(i)} - {\hat{y}}^{(i)})}^{2}$$
即
$$\sum_{i=1}^{m}{(y^{(i)} - {\hat{y}}^{(i)})}^{2}$$

### 简单线性回归的目标：

找到a和b使得
$$\sum_{i=1}^{m}{(y^{(i)} - {\hat{y}}^{(i)})}^{2}$$
尽可能小

由于
$${\hat{y}}^{(i)} = ax^{(i)} + b$$
即，
$$\sum_{i=1}^{m}{(y^{(i)} - a{\hat{x}}^{(i)} - b)}^{2}$$
我们称这个函数为 *损失函数（loss function）* 或者度量有效的部分，称为 *效用函数（utility function）*

典型的最小二乘法问题：最小化误差的平方
$$a = \frac{\sum_{i=1}^{m}{(x^{(i)} - \bar{x})(y^{(i)} - \bar{y})}}{\sum_{i=1}^{m}{(x^{(i)} - \bar{x})^2}}$$

$$b = \bar{y} - a\bar{x}$$

# 一般机器学习算法的基本思路

通过分析问题，确定问题的损失函数或者效用函数；

通过优化损失函数或者效用函数，获得机器学习模型

近乎所有的参数学习算法都是这样的套路