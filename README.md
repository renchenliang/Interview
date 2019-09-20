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
   
   [https://flashgene.com/wp-content/uploads/2019/07/fda81caafb8daf580fc1548ec92f6240.png]
  Batch Normlization运行原理
  -
