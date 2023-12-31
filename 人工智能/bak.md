# 1

## 术语

监督学习（有确定的结果） 无监督学习（无确定的结果）

数据集

* 训练集
* 测试集
* 验证集

损失函数 代价函数(cost funcation) J 是整个训练集的函数 梯度下降(lose funcation) L 只针对一个样本数据 学习率 矢量化 欠拟合（高偏差） 泛化 过拟合（高方差）

## 机器学习

### 监督学习

#### 线性回归

![images](<images/屏幕截图 2023-10-13 182544.png>) ![images](<images/屏幕截图 2023-10-13 182900.png>) ![images](<images/屏幕截图 2023-10-13 204302.png>) ![images](<images/屏幕截图 2023-10-13 205543.png>) ![images](<images/屏幕截图 2023-10-13 210418.png>) ![images](<images/屏幕截图 2023-10-13 211321.png>) ![images](<images/屏幕截图 2023-10-13 211834.png>) ![images](<images/屏幕截图 2023-10-13 212428.png>) ![images](<images/屏幕截图 2023-10-13 212630.png>) ![images](<images/屏幕截图 2023-10-13 212924.png>) ![images](<images/屏幕截图 2023-10-13 213117.png>) ![images](<images/屏幕截图 2023-10-13 214812.png>) ![images](<images/屏幕截图 2023-10-13 215047.png>)

**梯度下降** ![images](<images/屏幕截图 2023-10-14 124842.png>) ![images](<images/屏幕截图 2023-10-14 125417.png>) ![images](<images/屏幕截图 2023-10-14 131327.png>) ![images](<images/屏幕截图 2023-10-14 133651.png>) ![images](<images/屏幕截图 2023-10-14 134226.png>) ![images](<images/屏幕截图 2023-10-14 140227.png>) ![images](<images/屏幕截图 2023-10-14 140859.png>) ![images](<images/屏幕截图 2023-10-14 141130.png>) ![images](<images/屏幕截图 2023-10-14 142752.png>)

**导数推导** ![images](<images/屏幕截图 2023-10-14 143109.png>) ![images](<images/屏幕截图 2023-10-14 143308.png>)

**线性回归模型的代价函数是一个凸函数（convex function）一定会收敛到最小值** ![images](<images/屏幕截图 2023-10-14 143619.png>) ![images](<images/屏幕截图 2023-10-14 144904.png>)

#### 多维特征

![images](<images/屏幕截图 2023-10-14 171217.png>) ![images](<images/屏幕截图 2023-10-14 171502.png>) ![images](<images/屏幕截图 2023-10-14 171935.png>)

**矢量化** ![images](<images/屏幕截图 2023-10-14 172756.png>) ![images](<images/屏幕截图 2023-10-14 181436.png>) ![images](<images/屏幕截图 2023-10-14 181815.png>)

**多元线性回归梯度下降** ![images](<images/屏幕截图 2023-10-14 182324.png>) ![images](<images/屏幕截图 2023-10-14 182711.png>) ![images](<images/屏幕截图 2023-10-14 183001.png>) ![images](<images/屏幕截图 2023-10-14 185222.png>)

特征缩放 ![images](<images/屏幕截图 2023-10-14 185432.png>) ![images](<images/屏幕截图 2023-10-14 185749.png>)

**特征缩放的实现**

![images](<images/屏幕截图 2023-10-14 193408.png>) 方法一：每个特征除每个特征的最大值

![images](<images/屏幕截图 2023-10-14 194123.png>) 方法二：执行均值归一化

![images](<images/屏幕截图 2023-10-14 194451.png>) 方法三：执行Z分数归一化

![images](<images/屏幕截图 2023-10-14 194728.png>) 可能需要特征缩放的数据

**判断梯度下降是否收敛**

![images](<images/屏幕截图 2023-10-14 195430.png>) 通过迭代次数和代价函数的图像观察或者设定阈值

![images](<images/屏幕截图 2023-10-14 200506.png>) ![images](<images/屏幕截图 2023-10-14 200733.png>) 如何选择合适的学习率

**特征工程**

![images](<images/屏幕截图 2023-10-14 202133.png>) 通过对问题的了解修改特征

![images](<images/屏幕截图 2023-10-14 202512.png>) ![images](<images/屏幕截图 2023-10-14 202641.png>) 修改特征的具体方法

#### 分类算法-逻辑回归

![images](<images/屏幕截图 2023-10-15 183627.png>) ![images](<images/屏幕截图 2023-10-15 184333.png>)

**逻辑回归**

![images](<images/屏幕截图 2023-10-15 195853.png>) sigmoid函数和logistic函数

![images](<images/屏幕截图 2023-10-15 200222.png>) 将线性回归变为逻辑回归

![images](<images/屏幕截图 2023-10-15 200617.png>) 逻辑回归公式

**决策边界**

![images](<images/屏幕截图 2023-10-16 144948.png>) ![images](<images/屏幕截图 2023-10-16 145302.png>) 线形的决策边界

![images](<images/屏幕截图 2023-10-16 145724.png>) 非线形的决策边界

![images](<images/屏幕截图 2023-10-16 150324.png>) 通过特征工程可以得到复杂的决策边界

**逻辑回归中的代价函数**

![images](<images/屏幕截图 2023-10-16 151518.png>) 直接使用最小二乘法做损失函数

![images](<images/屏幕截图 2023-10-16 152157.png>) 真实值为1时的损失函数

![images](<images/屏幕截图 2023-10-16 152542.png>) 真实值为0时的损失函数

当模型预测的值和实际的结果误差越大，损失就越大

![images](<images/屏幕截图 2023-10-16 154332.png>) 简化的损失函数

![images](<images/屏幕截图 2023-10-16 154619.png>) 简化的代价函数

![images](<images/屏幕截图 2023-10-17 202702.png>) ![images](<images/屏幕截图 2023-10-17 203224.png>) 逻辑回归实现梯度下降

**过拟合问题**

![images](<images/屏幕截图 2023-10-17 204450.png>) ![images](<images/屏幕截图 2023-10-17 204638.png>)

**解决过拟合问题**

![images](<images/屏幕截图 2023-10-18 175028.png>) 收集更多训练数据

![images](<images/屏幕截图 2023-10-18 175621.png>) 选择合适的特征

![images](<images/屏幕截图 2023-10-18 175924.png>) 通过减小w的值减小特征对模型的影响避免过拟合

**正则化**

![images](<images/屏幕截图 2023-10-18 182018.png>) ![images](<images/屏幕截图 2023-10-18 182457.png>) ![images](<images/屏幕截图 2023-10-18 190311.png>) 在代价函数上加入正则项当正则化率大时图像近乎于一条直线 当正则化率小时图像会过拟合 选择合适的正则化率可以减少$\vec{w}$的的值避免过拟合

**用于线性回归的正则方法**

![images](<images/屏幕截图 2023-10-18 201113.png>) ![images](<images/屏幕截图 2023-10-18 203514.png>) ![images](<images/屏幕截图 2023-10-18 203821.png>)

**用于逻辑回归的正则方法**

![images](<images/屏幕截图 2023-10-18 204602.png>) ![images](<images/屏幕截图 2023-10-18 204930.png>)

#### 神经网络

![images](<images/屏幕截图 2023-10-19 153141.png>) 神经网络的发展

![images](<images/屏幕截图 2023-10-19 154742.png>) 简单类比生物神经元和神经网络

![images](<images/屏幕截图 2023-10-19 155027.png>) 神经网络发展的原因

![images](<images/屏幕截图 2023-10-19 162314.png>) 建议神经网络示例

![images](<images/屏幕截图 2023-10-19 163243.png>) ![images](<images/屏幕截图 2023-10-19 164018.png>) ![images](<images/屏幕截图 2023-10-19 164541.png>) 有多个隐藏层的神经网络

**举例图像识别**

![images](<images/屏幕截图 2023-10-19 170222.png>) ![images](<images/屏幕截图 2023-10-19 170352.png>)

**神经网络中的网络层**

![images](<images/屏幕截图 2023-10-19 180507.png>) 第一层

![images](<images/屏幕截图 2023-10-19 180810.png>) 第二层

![images](<images/屏幕截图 2023-10-19 180925.png>) 结果

**更复杂的神经网络**

![images](<images/屏幕截图 2023-10-19 203228.png>) ![images](<images/屏幕截图 2023-10-19 203712.png>)

**前向传播**

![images](<images/屏幕截图 2023-10-19 204048.png>) ![images](<images/屏幕截图 2023-10-19 204144.png>) ![images](<images/屏幕截图 2023-10-19 204254.png>) ![images](<images/屏幕截图 2023-10-21 125313.png>) 手写数字识别

**简易代码实现(基于TensorFlow)**

![images](<images/屏幕截图 2023-10-21 124645.png>) ![images](<images/屏幕截图 2023-10-21 125122.png>)

**TensorFlow中的数据格式**

![images](<images/屏幕截图 2023-10-21 135003.png>) ![images](<images/屏幕截图 2023-10-21 135233.png>) ![images](<images/屏幕截图 2023-10-21 135523.png>) ![images](<images/屏幕截图 2023-10-21 135627.png>)

**搭建简易神经网络**

![images](<images/屏幕截图 2023-10-21 141040.png>) ![images](<images/屏幕截图 2023-10-21 150001.png>) ![images](<images/屏幕截图 2023-10-21 150552.png>)

**单个网络层上的前向传播**

![images](<images/屏幕截图 2023-10-21 151939.png>) ![images](<images/屏幕截图 2023-10-21 171303.png>)

**强人工智能**

![images](<images/屏幕截图 2023-10-21 171808.png>) ANI和AGI

**神经网络的矢量化**

![images](<images/屏幕截图 2023-10-21 212516.png>)

**矩阵乘法**

![images](<images/屏幕截图 2023-10-21 212910.png>) 点积和矩阵乘法

![images](<images/屏幕截图 2023-10-21 213119.png>) 向量矩阵乘法

![images](<images/屏幕截图 2023-10-21 213349.png>) ![images](<images/屏幕截图 2023-10-21 213812.png>) ![images](<images/屏幕截图 2023-10-21 214013.png>) ![images](<images/屏幕截图 2023-10-21 214259.png>) 矩阵乘法

![images](<images/屏幕截图 2023-10-21 214624.png>)

#### TensorFlow代码实现

![images](<images/屏幕截图 2023-10-21 215113.png>) ![images](<images/屏幕截图 2023-10-22 191128.png>) 模型训练的步骤

![images](<images/屏幕截图 2023-10-22 191709.png>) ![images](<images/屏幕截图 2023-10-22 193022.png>) ![images](<images/屏幕截图 2023-10-22 193308.png>) 具体实现

**不同的激活函数**

![images](<images/屏幕截图 2023-10-22 194547.png>) sigmomid and ReLU

![images](<images/屏幕截图 2023-10-22 194726.png>) 常用激活函数

**选择激活函数**

![images](<images/屏幕截图 2023-10-22 195319.png>) 根据输出层的不同选择不同的激活函数

![images](<images/屏幕截图 2023-10-22 195736.png>) 隐藏层通常选择ReLU因为计算更快，梯度下降也快训练效果好

![images](<images/屏幕截图 2023-10-22 195925.png>)

**激活函数的作用**

![images](<images/屏幕截图 2023-10-23 170310.png>)

![images](<images/屏幕截图 2023-10-23 170530.png>) ![images](<images/屏幕截图 2023-10-23 170756.png>) 不使用激活函数多层的神经网络就相当于一层的线性回归

**多分类问题**

![images](<images/屏幕截图 2023-10-23 171009.png>) ![images](<images/屏幕截图 2023-10-23 171056.png>)

**softmax函数**

![images](<images/屏幕截图 2023-10-23 213235.png>) ![images](<images/屏幕截图 2023-10-23 213835.png>) softmax函数的损失函数

![images](<images/屏幕截图 2023-10-23 214434.png>) ![images](<images/屏幕截图 2023-10-23 214613.png>)

![images](<images/屏幕截图 2023-10-23 220008.png>) ![images](<images/屏幕截图 2023-10-23 220449.png>) 优化代码通过底层计算浮点数的不同使结果更加准确 缺点代码可读性差

![images](<images/屏幕截图 2023-10-23 220805.png>) ![images](<images/屏幕截图 2023-10-23 220920.png>)

**多个输出的分类**

![images](<images/屏幕截图 2023-10-25 140846.png>) ![images](<images/屏幕截图 2023-10-25 141301.png>) 查看途中有没有人，汽车，公交车

**高级优化方法(Adam算法)**

![images](<images/屏幕截图 2023-10-25 141718.png>) ![images](<images/屏幕截图 2023-10-25 142133.png>) ![images](<images/屏幕截图 2023-10-25 142430.png>) Adam算法可以自动调整学习率，更好的训练模型

**其他网络层类型**

![images](<images/屏幕截图 2023-10-25 142805.png>) 密集层

![images](<images/屏幕截图 2023-10-25 142949.png>) ![images](<images/屏幕截图 2023-10-25 143200.png>) 卷积层

**导数知识**

![images](<images/屏幕截图 2023-10-25 152219.png>) ![images](<images/屏幕截图 2023-10-25 152531.png>) ![images](<images/屏幕截图 2023-10-25 153728.png>)

**计算图**

![images](<images/屏幕截图 2023-10-25 154022.png>) ![images](<images/屏幕截图 2023-10-25 154624.png>) ![images](<images/屏幕截图 2023-10-25 154726.png>) ![images](<images/屏幕截图 2023-10-25 154942.png>)

**大型神经网络**

![images](<images/屏幕截图 2023-10-25 160406.png>) ![images](<images/屏幕截图 2023-10-25 160617.png>)

### 偏差和方差

![images](<images/屏幕截图 2023-10-25 161146.png>)

**模型评估**

![images](<images/屏幕截图 2023-10-25 175721.png>) ![images](<images/屏幕截图 2023-10-25 175858.png>) ![images](<images/屏幕截图 2023-10-25 180128.png>) ![images](<images/屏幕截图 2023-10-25 180254.png>) ![images](<images/屏幕截图 2023-10-25 180356.png>) ![images](<images/屏幕截图 2023-10-25 180506.png>)

**模型选择**

![images](<images/屏幕截图 2023-10-25 181156.png>) 只通过测试集得到的损失函数泛化度不够

![images](<images/屏幕截图 2023-10-25 181357.png>) 通过添加dev test选择模型

![images](<images/屏幕截图 2023-10-25 181944.png>) ![images](<images/屏幕截图 2023-10-25 182438.png>)

**偏差和方差**

![images](<images/屏幕截图 2023-10-26 144412.png>) 高偏差$J\_{train}$高 高方差$J\_{cv}>J\_{train}$

![images](<images/屏幕截图 2023-10-26 144716.png>) ![images](<images/屏幕截图 2023-10-26 145058.png>)

**正则化，偏差和方差**

![images](<images/屏幕截图 2023-10-26 145506.png>) ![images](<images/屏幕截图 2023-10-26 145914.png>) ![images](<images/屏幕截图 2023-10-26 150105.png>)

**实例语音识别**

![images](<images/屏幕截图 2023-10-26 150940.png>) ![images](<images/屏幕截图 2023-10-26 151129.png>) ![images](<images/屏幕截图 2023-10-26 151435.png>)

**学习曲线**

![images](<images/屏幕截图 2023-10-26 152040.png>) ![images](<images/屏幕截图 2023-10-26 152443.png>) 高偏差增加数据集基本没用，模型出现问题

![images](<images/屏幕截图 2023-10-26 152902.png>) 高方差可以增加数据集

**结论**

![images](<images/屏幕截图 2023-10-26 154038.png>) ![images](<images/屏幕截图 2023-10-26 154526.png>) ![images](<images/屏幕截图 2023-10-26 183204.png>) ![images](<images/屏幕截图 2023-10-26 183340.png>) ![images](<images/屏幕截图 2023-10-26 183607.png>) 选择合适的正则化参数可以让神经网络避免过拟合，但是会增加计算量

### 机器学习开发的迭代循环

![images](<images/屏幕截图 2023-10-26 184720.png>) ![images](<images/屏幕截图 2023-10-26 184841.png>) 垃圾邮件示例

**误差分析**

![images](<images/屏幕截图 2023-10-29 161450.png>) ![images](<images/屏幕截图 2023-10-29 161538.png>) ![images](<images/屏幕截图 2023-10-29 161711.png>)

**添加数据**

![images](<images/屏幕截图 2023-10-29 163128.png>) ![images](<images/屏幕截图 2023-10-29 163233.png>) ![images](<images/屏幕截图 2023-10-29 163450.png>) ![images](<images/屏幕截图 2023-10-29 163659.png>) 数据增强修改现有的数据来构建新的数据集

![images](<images/屏幕截图 2023-10-29 163802.png>) ![images](<images/屏幕截图 2023-10-29 163952.png>) ![images](<images/屏幕截图 2023-10-29 164538.png>) ![images](<images/屏幕截图 2023-10-29 164412.png>) 创建新的数据通过原始数据和不同的字体结合生成不同的数据

![images](<images/屏幕截图 2023-10-29 164752.png>)

**迁移学习**

![images](<images/屏幕截图 2023-10-29 170614.png>) ![images](<images/屏幕截图 2023-10-29 170914.png>) ![images](<images/屏幕截图 2023-10-29 171211.png>)

**机器学习项目的完整周期**

![images](<images/屏幕截图 2023-10-29 180355.png>) ![images](<images/屏幕截图 2023-10-29 180923.png>)

**道德相关**

![images](<images/屏幕截图 2023-10-29 182513.png>) ![images](<images/屏幕截图 2023-10-29 182622.png>) fake video

![images](<images/屏幕截图 2023-10-29 182916.png>) ![images](<images/屏幕截图 2023-10-29 183055.png>)

**倾斜数据集**

![images](<images/屏幕截图 2023-10-29 184932.png>) ![images](<images/屏幕截图 2023-10-29 185816.png>) 对于罕见的数据预测时可能一直预测0，你的模型准确度可能很高，但是缺没有意义，引入其他指标来评估模型 precision：猜的准确率 recall：避免漏检

**精确率和召回率**

![images](<images/屏幕截图 2023-10-29 190944.png>) ![images](<images/屏幕截图 2023-10-29 191347.png>)

### 决策树

**决策树模型**

![images](<images/屏幕截图 2023-10-30 213303.png>) ![images](<images/屏幕截图 2023-10-30 213659.png>) ![images](<images/屏幕截图 2023-10-30 213819.png>)

**学习过程**

![images](<images/屏幕截图 2023-10-30 214348.png>) ![images](<images/屏幕截图 2023-10-30 214733.png>) ![images](<images/屏幕截图 2023-10-30 214934.png>) ![images](<images/屏幕截图 2023-10-30 215116.png>)

**纯度**

![images](<images/屏幕截图 2023-10-30 215902.png>) 引入熵来衡量数据的纯度

![images](<images/屏幕截图 2023-10-30 220243.png>) 规定$0\*\log\_20 = 0$

**区分信息**

![images](<images/屏幕截图 2023-10-30 221255.png>) 通过熵的减少量选择分支，熵的减少也叫信息增益(information gain)

![images](<images/屏幕截图 2023-10-30 221522.png>) 计算公式

**整合**

![images](<images/屏幕截图 2023-10-31 183400.png>) ![images](<images/屏幕截图 2023-10-31 184556.png>) 递归的思想来构建决策树，通过树的深度设定来避免过拟合

**one-hot编码**

![images](<images/屏幕截图 2023-10-31 190120.png>) ![images](<images/屏幕截图 2023-10-31 190258.png>) ![images](<images/屏幕截图 2023-10-31 190335.png>) 编码规则

![images](<images/屏幕截图 2023-10-31 190617.png>)

**连续的特征值**

![images](<images/屏幕截图 2023-10-31 190834.png>) ![images](<images/屏幕截图 2023-10-31 191431.png>) 遍历计算信息增益，来决定分割数据的阈值

**回归树**

![images](<images/屏幕截图 2023-10-31 204432.png>) ![images](<images/屏幕截图 2023-10-31 204704.png>) ![images](<images/屏幕截图 2023-10-31 205234.png>) 用方差衡量数据的混乱程度，同样计算信息增益来选择分支

**决策树集群**

![images](<images/屏幕截图 2023-10-31 205619.png>) 只训练一个树的话只更改一个数据就会得到不同的决策树，为了是算法更加强大可以训练多个树

![images](<images/屏幕截图 2023-10-31 205913.png>) 让三颗树投票决定最终的结果

**有放回抽样(sampling with replacement)**

![images](<images/屏幕截图 2023-10-31 210429.png>) ![images](<images/屏幕截图 2023-10-31 210613.png>) 有放回抽样可以构建新的训练集

**随机森林**

![images](<images/屏幕截图 2023-10-31 212451.png>) ![images](<images/屏幕截图 2023-10-31 212704.png>)

**XGBoost**

![images](<images/屏幕截图 2023-10-31 214328.png>) boost优化方法

![images](<images/屏幕截图 2023-10-31 214529.png>) XGBoost优化方法

![images](<images/屏幕截图 2023-10-31 214627.png>) 使用

**何时使用决策树**

![images](<images/屏幕截图 2023-10-31 215032.png>) ![images](<images/屏幕截图 2023-10-31 215213.png>)

### 无监督学习

![images](<images/屏幕截图 2023-11-02 170105.png>)

**聚类算法**

![images](<images/屏幕截图 2023-11-02 170316.png>) 监督学习：二元分类

![images](<images/屏幕截图 2023-11-02 170502.png>) 无监督学习：聚类算法

![images](<images/屏幕截图 2023-11-02 170725.png>) 聚类算法的应用

**K-means算法**

![images](<images/屏幕截图 2023-11-02 171124.png>) 计算每个点到两个簇心的距离将其分为两类离红色近的或者离蓝色近的

![images](<images/屏幕截图 2023-11-02 171335.png>) 移动簇心使其到每个点的距离最小

![images](<images/屏幕截图 2023-11-02 171851.png>) 重复

**K-means算法具体实现**

![images](<images/屏幕截图 2023-11-02 191556.png>) ![images](<images/屏幕截图 2023-11-02 191954.png>) ![images](<images/屏幕截图 2023-11-02 192100.png>) 特殊情况：有一个簇没有点，那么这个簇会被删除

![images](<images/屏幕截图 2023-11-02 192355.png>)

**优化目标**

![images](<images/屏幕截图 2023-11-02 194144.png>) 重新确定簇心的过程就是代价函数 这个函数也叫失真函数(distortion function) 每个点到与他最近的簇心距离的平均和

![images](<images/屏幕截图 2023-11-02 194422.png>) ![images](<images/屏幕截图 2023-11-02 194928.png>) ![images](<images/屏幕截图 2023-11-02 195125.png>) $C^{(i)}$:离簇心最近的点的集合 i:簇心的索引 $\mu\_k$:簇心

**初始化K-means**

![images](<images/屏幕截图 2023-11-02 200458.png>) ![images](<images/屏幕截图 2023-11-02 200818.png>) 方法一：随机选择数据集中的数据作为簇心

![images](<images/屏幕截图 2023-11-02 201405.png>) 方法二：得到了多个模型后使用代价函数来选择模型

![images](<images/屏幕截图 2023-11-02 201708.png>)

**选择聚类数量**

![images](<images/屏幕截图 2023-11-02 202447.png>) ![images](<images/屏幕截图 2023-11-02 202639.png>) 肘法(不推荐)

![images](<images/屏幕截图 2023-11-02 202806.png>) 通过业务具体分析选择K值

### 异常检测算法

![images](<images/屏幕截图 2023-11-02 203542.png>) ![images](<images/屏幕截图 2023-11-02 203736.png>) ![images](<images/屏幕截图 2023-11-02 203904.png>) 应用示例

**高斯正态分布**

![images](<images/屏幕截图 2023-11-04 120153.png>) ![images](<images/屏幕截图 2023-11-04 120502.png>) 图形的面积为一

![images](<images/屏幕截图 2023-11-04 121109.png>) 应用于异常检测算法

![images](<images/屏幕截图 2023-11-04 121249.png>)

**异常检测算法**

![images](<images/屏幕截图 2023-11-04 122139.png>) 对于多个特征的异常检测

![images](<images/屏幕截图 2023-11-04 125436.png>) 矢量化计算

![images](<images/屏幕截图 2023-11-04 122737.png>) 算法的工作流程

![images](<images/屏幕截图 2023-11-04 123128.png>) 应用示例

**开发和评估异常检测**

![images](<images/屏幕截图 2023-11-04 124614.png>) 通过标记的数据测试模型来决定$\epsilon$

![images](<images/屏幕截图 2023-11-04 125929.png>) ![images](<images/屏幕截图 2023-11-04 130105.png>) 也可以使用精确率和召回率来评估模型

**异常检测对比监督学习**

![images](<images/屏幕截图 2023-11-04 130651.png>) 异常检测更适合预测未出现的异常种类，监督学习度已经出现过的错误可以更好地检测

![images](<images/屏幕截图 2023-11-04 130946.png>) 示例

**选择特征**

![images](<images/屏幕截图 2023-11-04 131308.png>) ![images](<images/屏幕截图 2023-11-04 131730.png>) ![images](<images/屏幕截图 2023-11-04 131833.png>)

### 推荐系统

![images](<images/屏幕截图 2023-11-04 153944.png>) 示例

**使用每个特征**

![images](<images/屏幕截图 2023-11-04 160731.png>) ![images](<images/屏幕截图 2023-11-04 161426.png>) ![images](<images/屏幕截图 2023-11-04 161639.png>)

**协同过滤算法**

![images](<images/屏幕截图 2023-11-04 162220.png>) ![images](<images/屏幕截图 2023-11-04 162558.png>) ![images](<images/屏幕截图 2023-11-04 163114.png>) 协同过滤算法

![images](<images/屏幕截图 2023-11-04 163524.png>) 梯度下降

**对二元标签的泛化**

![images](<images/屏幕截图 2023-11-04 164123.png>) ![images](<images/屏幕截图 2023-11-04 164348.png>) ![images](<images/屏幕截图 2023-11-04 164523.png>) ![images](<images/屏幕截图 2023-11-04 165041.png>)

**均值归一化**

![images](<images/屏幕截图 2023-11-07 135955.png>) ![images](<images/屏幕截图 2023-11-07 140056.png>) 处理数据

![images](<images/屏幕截图 2023-11-07 140633.png>)

### TensorFlow实现推荐系统

![images](<images/屏幕截图 2023-11-07 141030.png>) ![images](<images/屏幕截图 2023-11-07 141554.png>) TensorFlow 自动求代价函数导完成梯度下降

![images](<images/屏幕截图 2023-11-07 142037.png>)

**推荐相关项目(Finding related items)**

![images](<images/屏幕截图 2023-11-07 142659.png>) ![images](<images/屏幕截图 2023-11-07 143013.png>)

### 基于内容的过滤算法和普通过滤算法

![images](<images/屏幕截图 2023-11-07 144230.png>) ![images](<images/屏幕截图 2023-11-07 144658.png>) ![images](<images/屏幕截图 2023-11-07 145115.png>)

**深度学习和基于内容的过滤算法**

![images](<images/屏幕截图 2023-11-07 145752.png>) ![images](<images/屏幕截图 2023-11-07 150117.png>) ![images](<images/屏幕截图 2023-11-07 150337.png>)

**从大型目录中推荐**

![images](<images/屏幕截图 2023-11-07 184346.png>) ![images](<images/屏幕截图 2023-11-07 184900.png>) ![images](<images/屏幕截图 2023-11-07 185059.png>) ![images](<images/屏幕截图 2023-11-07 185259.png>)

**推荐系统中的伦理问题**

![images](<images/屏幕截图 2023-11-08 195016.png>) ![images](<images/屏幕截图 2023-11-08 195249.png>) ![images](<images/屏幕截图 2023-11-08 195352.png>)

**基于内容过滤的TensorFlow实现**

![images](<images/屏幕截图 2023-11-09 151055.png>)

**降低特征数量**

![images](<images/屏幕截图 2023-11-09 152038.png>) 第一个例子

![images](<images/屏幕截图 2023-11-09 152524.png>) 第二个例子

![images](<images/屏幕截图 2023-11-09 152823.png>)

![images](<images/屏幕截图 2023-11-09 152919.png>) ![images](<images/屏幕截图 2023-11-09 153231.png>) ![images](<images/屏幕截图 2023-11-09 153306.png>) ![images](<images/屏幕截图 2023-11-09 153334.png>) ![images](<images/屏幕截图 2023-11-09 153453.png>) ![images](<images/屏幕截图 2023-11-09 153615.png>)

**PCA算法**

![images](<images/屏幕截图 2023-11-09 153856.png>) ![images](<images/屏幕截图 2023-11-09 154235.png>) ![images](<images/屏幕截图 2023-11-09 154334.png>) ![images](<images/屏幕截图 2023-11-09 154445.png>) ![images](<images/屏幕截图 2023-11-09 154820.png>) ![images](<images/屏幕截图 2023-11-09 155011.png>) ![images](<images/屏幕截图 2023-11-09 155517.png>) PCA和线性回归的区别

![images](<images/屏幕截图 2023-11-09 155744.png>) ![images](<images/屏幕截图 2023-11-09 155910.png>)

**PCA代码实现**

![images](<images/屏幕截图 2023-11-09 162627.png>) ![images](<images/屏幕截图 2023-11-09 162741.png>) ![images](<images/屏幕截图 2023-11-09 162902.png>) ![images](<images/屏幕截图 2023-11-09 163034.png>)

### 强化学习

![images](<images/屏幕截图 2023-11-09 164718.png>) ![images](<images/屏幕截图 2023-11-09 164821.png>)

**火星探测器**

![images](<images/屏幕截图 2023-11-09 221917.png>)

**强化学习的回报(奖励)**

![images](<images/屏幕截图 2023-11-10 154943.png>) ![images](<images/屏幕截图 2023-11-10 155754.png>)

**在强化学习中做出决策**

![images](<images/屏幕截图 2023-11-10 160229.png>) ![images](<images/屏幕截图 2023-11-10 160322.png>)

**审查关键概念**

![images](<images/屏幕截图 2023-11-11 141134.png>) ![images](<images/屏幕截图 2023-11-11 141359.png>)

### 状态动作函数

![images](<images/屏幕截图 2023-11-11 142537.png>) ![images](<images/屏幕截图 2023-11-11 142831.png>)

### 朴素贝叶斯

**贝叶斯定理**

![images](<images/屏幕截图 2023-11-18 171240.png>) ![images](<images/屏幕截图 2023-11-19 124031.png>)

![images](<images/屏幕截图 2023-11-19 124031.png>) ![images](<images/屏幕截图 2023-11-19 124348.png>) 实例

**朴素贝叶斯**

![images](<images/屏幕截图 2023-11-19 124636.png>) ![images](<images/屏幕截图 2023-11-19 124744.png>) ![images](<images/屏幕截图 2023-11-19 124936.png>)

**贝叶斯为何而朴素**

![images](<images/屏幕截图 2023-11-19 125354.png>) ![images](<images/屏幕截图 2023-11-19 125509.png>)

朴素翻译自英文单词naive：假设每个特征相互独立基本上是不可能的事 ![images](<images/屏幕截图 2023-11-19 130418.png>) ![images](<images/屏幕截图 2023-11-19 130639.png>)

**后验概率最大化准则**

![images](<images/屏幕截图 2023-11-19 131509.png>) ![images](<images/屏幕截图 2023-11-19 132001.png>)

**极大似然估计**

![images](../%E4%BA%BA%E5%B7%A5%E6%99%BA%E8%83%BD) ![images](../%E4%BA%BA%E5%B7%A5%E6%99%BA%E8%83%BD) ![images](../%E4%BA%BA%E5%B7%A5%E6%99%BA%E8%83%BD) ![images](../%E4%BA%BA%E5%B7%A5%E6%99%BA%E8%83%BD)
