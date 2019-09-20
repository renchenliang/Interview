SVM算法，以及其中的硬间隔、软间隔的意思；核参数的类别？
-
  * [硬间隔] 所有数据线性可分，所有数据均满足分类条件，即存在超平面完全正确分类正负样本
  * [软间隔] 部分数据线性不可分。
  * [核函数] 
 
 python list底层实现原理
 -
    python中的list与c++的list不同，c++中的list是双向链表，而python list更像c++中的vector。
    python中Cpython list定义如下结构体
    typedef struct {
       PyObject_VAR_HEAD
       PyObject **ob_item;(指向列表元素的指针)
       Py_ssize_t allocated;（分配内存的大小)
       } PyListObject;
   这里的分配内存是成倍增加的0，4，8，16，25，35，46，58，72，88……当列表长度小于总内存的一半时，会自动的删除1/2内存
   (https://zhuanlan.zhihu.com/p/30584550)
   (https://www.jianshu.com/p/cd75475168ae)
   append的复杂度O(1)   insert O(n)     Pop O(1)
   
Batch Normlization运行原理
-
   ![](https://flashgene.com/wp-content/uploads/2019/07/fda81caafb8daf580fc1548ec92f6240.png) <br>
   CNN卷积前向<br>
   ![](https://flashgene.com/wp-content/uploads/2019/07/13267986fe72122e5a5d4a1c4a4aaad4.png)
   ![](https://images2018.cnblogs.com/blog/1053881/201804/1053881-20180412173741958-245242223.png)<br>
   训练阶段：对mini-batch中的每一个实例卷积后的对应位置的同一通道中的所有元素求均值以及方差 <br>
   测试阶段：记录训练mini-batch过程中的每一个均值以及方差，并对所有的均值-方差求无偏估计作为inferere的均值与方差。<br>
  

