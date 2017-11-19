# Non-parametric的意义
当预测值和实际值偏差呈正态分布时，损失函数为平方损失时，恰好可以表征这种
分布。当误差分布非正态时，这时候再Fit一个线性模型，预测就不是那么准确了

__Locally weighted linear regression__ 的思路是让损失函数与带预测点和训练
样本的距离联系起来，让离样本近的点，误差占更大的权重。而离样本较远的点，
降低其在最终损失函数中的权重。

具体来说，__Linear Regression__ 中的优化目标是
$$\mbox{Minimize } \sum_i(y^{(i)} - \theta^T x^{(i)})^2 $$,
求出$$\theta$$, 即找到了模型参数，任意给定待预测点，很快可以计算出预
测值。而 __Locally weighted linear regression__ 的优化目标是
$$\mbox{Minimize } \sum_i \omega^{(i)}(y^{(i)}-\theta^T x^{(i)})^2$$
对于每个输入$$x$$，都需要单独计算一次新的$$\theta$$, 然后才能计算目标值

