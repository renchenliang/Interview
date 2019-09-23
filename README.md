SVM算法，以及其中的硬间隔、软间隔的意思；核参数的类别？目标函数？为什么变成对偶问题求解？
-
  * [硬间隔] 所有数据线性可分，所有数据均满足分类条件，即存在超平面完全正确分类正负样本
  * [软间隔] 部分数据线性不可分。
  * [核函数] 
 
python list底层实现原理
-
    python中的list与c++的list不同，c++中的list是双向链表，而python list更像c++中的vector。<br>
    python中Cpython list定义如下结构体
    typedef struct {
       PyObject_VAR_HEAD
       PyObject **ob_item;(指向列表元素的指针)
       Py_ssize_t allocated;（分配内存的大小)
       } PyListObject;<br>
    这里的分配内存是成倍增加的0，4，8，16，25，35，46，58，72，88……当列表长度小于总内存的一半时，会自动的删除1/2内存<br>
   (https://zhuanlan.zhihu.com/p/30584550)<br>
   (https://www.jianshu.com/p/cd75475168ae)<br>
    append的复杂度O(1)   insert O(n)     Pop O(1)
   
Batch Normlization运行原理
-
   ![](https://flashgene.com/wp-content/uploads/2019/07/fda81caafb8daf580fc1548ec92f6240.png) <br>
    CNN卷积前向<br>
   ![](https://flashgene.com/wp-content/uploads/2019/07/13267986fe72122e5a5d4a1c4a4aaad4.png) <br>
   ![](https://images2018.cnblogs.com/blog/1053881/201804/1053881-20180412173741958-245242223.png)<br>
    训练阶段：对mini-batch中的每一个实例卷积后的对应位置的同一通道中的所有元素求均值以及方差 <br>
     测试阶段：记录训练mini-batch过程中的每一个均值以及方差，并对所有的均值-方差求无偏估计作为inferere的均值与方差。<br>

LR为什么不用MSE？SVM为什么用hinge，而不用logloss?
-
    LR本质是分类，一般回归用MSE，分类用交叉熵。因为分类，经过MSE，为非凸函数，难以收敛；当接近某一类时，另外一类的数值很小，容易造成梯度消失。

Dropout前向与反向的处理？
-
    前向随机以概率p失活某神经元。

函数间隔与几何间隔
-
    函数间隔是几何间隔没有除以||w||的表达，几何间隔是函数间隔归一化的结果
   
K-Means一定会收敛么？为什么？
-
    一定会收敛。

AUC与ROC的含义？
-
   * ROC曲线: 接收者操作特征(receiver operating characteristic))<br>
   ![](http://images.cnitblog.com/blog2015/712297/201504/081954327748728.jpg)
   纵坐标 真正类率(True Postive Rate)TPR： 在正类中被预测为正类占所有正类的比例
   横坐标 负正类率(False Postive Rate)FPR： 在负类中被预测为正类占所有负类的比例

浅copy与深copy的区别？
-

    浅copy没有单独申请内存，2个变量为同一个id，改了一个变量另外一个变量也会改变； 深copy单独申请内存

朴素贝叶斯与贝叶斯的区别？
-
    朴素贝叶斯的假设为所有的特征相互独立，贝叶斯网络源于贝叶斯定理（即条件概率）。当特征个数肥肠多时，整个贝叶斯网络里的参数是庞大的，源于不同特征间的联和分布。因此将其简化，可得到最简单的朴素贝叶斯。
   
聚类的算法有哪些？评价方法？优化算法？
-
K-means， 

id类特征除了onehot编码还有哪些？遇到高维特征呢？怎么才算高纬？

常用颜色空间？
-
    RGB,HSV,YBR

RPN怎么计算box的实际坐标？
-

常见的损失函数？
-
L1,L2损失。L1-smooth； 交叉熵损失；  triplet损失；  

anchor free算法？
Yolo,SSD, centernet,cornernet

Focal Loss如何进行难分样本挖掘的？
-
 one-stage比two-stage精度低的原因主要是正负样本比例不均衡。 one-stage会产生大量的候选区域，而这些候选区域只有很少的一部分属于正样本。 而two-stage经过RPN网络，初选出那些概率比较大的候选区域，令正负样本的比例在1：3.<br>

 ![](https://images2018.cnblogs.com/blog/1055519/201808/1055519-20180818162755861-24998254.png)<br>
 在二分类的交叉熵损失函数中，y'是于猜测输出数值，正样本预测概率值越大，其损失越小；负样本预测概率越小，损失越大。这样使得越简单的正样本占的损失使得困难样本的损失起的作用很小。因此引出如下focal Loss <br>
 ![](https://images2018.cnblogs.com/blog/1055519/201808/1055519-20180818174822290-765890427.png)<br>
 引入Gamma因子。Gamma>0使得减少易分类样本的损失，使得模型更关注于困难的、错分的样本。<br>
 最后再引入数据平衡因子 Alpha，用来平衡正负样本本身的数量比例不均（即类别不均衡）<br>
 ![](https://images2018.cnblogs.com/blog/1055519/201808/1055519-20180818174944824-933422059.png)<br>



   

  

