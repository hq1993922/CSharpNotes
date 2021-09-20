# 队列(Queue)
## 结构
* array数组
* head索引
* tail索引
* size 也就是Count
* version (似乎是做并发控制的,但是好像又没用起来)

## 实现
### 设置容量(SetCapacity)
* 初始化一个长度为 0 的容器数组, 或使用带参构造函数指定容器数组长度
* 当长度不够时, 对容器数组resize操作, 每次扩容为原先的两倍(每次扩容长最小为 4, 不会以 0 的两倍进行扩容)

### 入队 (Enqueue)
注意: size并不是数组的容量, 而是当前元素的数量
1. `array[( tail + 1 ) % array.Length ] = {value}` 
2. `size++`

* 数组无法动态扩容, 出队操作会从数组头部开始移除元素, 取模是为了重复利用已经出队的元素的空间
* 当 size == array.Length 时, 先扩容然后再入队

### 出队 (Dequeue)
1. `array[head] = default(T)`
2. `head = (head + 1) % array.Length`
3. `size--`
* 同上, 索引 `head` 会在抵达数组末端后从头开始移动