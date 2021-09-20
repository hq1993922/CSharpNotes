# 双向链表(LinkedList)
## 结构
* LinkedList
  * version 通过Enumerator
  * size 也就是数组长度
  * head 头节点
  * version (待补充)
  * syncRoot 处理并发时用于加锁的对象
* LinkedListNode
  * list LinkedList自身
  * next 下一个节点
  * prev 上一个节点

## 实现
### 插入(AddFirst,AddLast,AddBefore,AddAfter)
*  当链表内无节点时, 设置被插入节点为 head 节点, 该节点的 prev 和 next 都设为自身
*  其他不细说了, `AddBefore` 是插入到目标节点与目标节点的 `prev` 节点之间的位置, `AddAfter` 则是之后

### 查找(Find,FindLast)
* `Find` 从 `head` 节点依次向后查找
* `FindLast` 从 `head.prev` 节点依次向前查找

### 删除
* 链表中删除元素不必细说

## 笔记
第一次微软面试的第三面挂在这里了，不知道C#有哪些类似双向队列的结构，痛哉痛哉。
这个数据结构在解决 [239. 滑动窗口最大值](https://leetcode-cn.com/problems/sliding-window-maximum/) 的问题时可以用到。

因为是链表, 所以插入删除效率比较高, 查找效率较低。
