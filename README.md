# tarot-model
本人是一名刚入门没多久但是算的挺准的塔罗师，基于我的部分读牌经历，我抽取并归纳了一个典型案例：对大二在读历史系学生未来三年的学习发展趋势进行抽牌，分为2024、2025、2026三年，每年对应一张塔罗牌，对最终所得三张牌进行分析、结合，推算牌意结果。

以上所有的案例均由我个人读牌经历提供。因塔罗共有78张牌，其中分为大、小阿卡纳牌，而小阿卡纳牌有4种类型，分别为cups、wands、pentacles、swords，四类分别对应了1-10、knave、knight、queen、king这14张牌，是以小阿卡纳牌总共56张。

为了方便设计模型，我将以上78张牌简化为wands类的14张，同时我给出每张牌拥有4个牌意，每组案例相当于：在14张牌中不放回的随机抽取3张，并且把不同牌和其在不同搭配下应表达的牌意相对应。
<img width="152" alt="image" src="https://github.com/JoyceHai/tarot-model/assets/153286905/0e918865-95db-4c49-abb1-17c73ad55f2d">

为了检测模型效果，我定义了以下变量：

1)sum_mean = ∑测量值i-真实值i

2)avg_loss = sum_mean / k (即k组平均损失)

3)accuracy = 真实值 - 平均损失 / 真实值 
          = train_labels - avg_loss / train_labels 
          = test_labels - avg_loss / test_labels
          
4)相对偏差率 = | 1 - average_result | / 1 * 100%

训练集是1600组数据，可小批次投放，但总体结果大差不差（也许也有我考虑不周之处），所以最终以1600组投放训练。测试集为400组数据，应用为20组数据。

代码和构思都是和朋友一起完成的。
