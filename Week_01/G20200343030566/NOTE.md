学习笔记-week01总结

本周重点：数组，链表，跳表，栈，队列，优先队列，双端队列

知识概括小细节：
1> 数组是一种线性数据结构，用连续的存储空间存储相同类型数据
2>连续的内存空间、相同的数据，所以数组可以随机访问，但对数组进行删除插入，为了保证数组的连续性，就要进行数据迁移工作
数组支持随机访问，根据下标的随机访问时间复杂度是O(1)
3>链表的内存结构是不连续的内存空间，是将一组零散的内存块串联起来，从而进行数据存储的数据结构。
每一个内存块被称为节点Node。节点除了存储数据外，还需记录链上下一个节点的地址，即后继指针next
4>链表的插入删除数据时间复杂度为O(1),随机访问的效率为O(n),和数组相比，链表的内存消耗较大，每个存储节点都需要额外的空间存储next指针地址
5>双向链表，节点除了存储数据外，还有两个指针分别指向前一个节点地址（前驱指针prev）和下一个节点地址（后继指针next），首节点的前驱指针prev和尾节点的后继指针均指向空地址
6>栈，后进先出
7>队列，先进先出，操作受限的线性表，正常情况下入队和出队的时间复杂度都是O(1),如果队尾已满，进行数据搬迁，搬迁的时间复杂度是O(n),平均时间复杂度还是O(1)

分析 Queue 和 Priority Queue 的源码：
1.PriorityQueue是一种无界的，线程不安全的队列
2.内部实现结构是数组，内部维持一个小顶堆数据结构，
3.上浮节点，关键代码：int parent = (k - 1) >>> 1; 每次与父节点进行比较，小于父节点则进行结构调整，从k指定的位置开始，将x逐层与当前点的parent进行比较并交换，直到满足x >= queue[parent]为止。
4,删除节点的时候，如果是最后一个元素，则直接删除，如果不是最后一个节点，则要进行siftDown结构调整，从k指定的位置开始，将x逐层向下与当前点的左右孩子中较小的那个交换，直到x小于或等于左右孩子中的任何一个为止




