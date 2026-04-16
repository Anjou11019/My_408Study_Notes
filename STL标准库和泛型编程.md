# C++标准库 体系结构与内核分析

# 3.18

##### STL六大部件

容器（Containers）：存放数据

分配器（Allocators）：用来支持容器

算法（Algorithms）：用于处理容器数据

迭代器（Iterators）：算法与容器之间的桥梁，类似泛化的指针

适配器（Adapters）：容器适配器、迭代器适配器、仿函数适配器

仿函数（Functors）

```cpp
#include<vector>
#include<algorithm>
#include<functional>
#include<iostream>

using namespace std;

int main(){
    int ia[6] = {27,210,12,47,109,83};
    vector<int,allocator<int>> vi(ia,ia+6);//vector:container
    //vi.begin:iterator
    //count_if:algorithm
    //not1 bind2nd:function adapter
    //less:function object
    cout << count_if(vi.begin(),vi.end(),not1(bind2nd(less<int>(),40 ) ) );
}
```

##### 复杂度

常见的Big-oh有下列多长情形

O(1)/O(c) :常数时间

O(n):线性时间

$O(\log_2n)$:次线性时间

$O(n^2)$：平方时间

$O(n^3)$:立方时间

$O(2^n)$:指数时间

$O(n\log_2n)$:介于线性及二次方成长的中间行为模式

##### 前闭后开区间[ )

begin()指向第一个元素，end()指的是最后一个元素的下一个元素

##### range-based for statement 基于范围的for（第三次提到）

```cpp
for(decl : coll){
    statement
}

vector<double> vec;
for(auto elem : vec){
    cout << elem << endl;
}
```

##### 容器 - 结构性分类

Sequence Containers（序列式容器）：

    *Array* 数组（其实就是用类包装的普通数组）

    *Vector* 列表：可以自动增长容量的

    *Deque* 双端队列 ：两端可进可出的队列

    *List* 链表 ： 元素并不连续，双向链表

    *Forward List* 单向链表：

Associative Containers（关联式容器）：适合做快速查找

    *Set/Multiset*：内部用红黑树做的，它的value就是key，multiset元素可以重复

    *Map/MultiMap*：内部用红黑树做的，每个结点有一个key，multimap的key可以重复

Unordered Containers（无序容器，其实也是一种关联式容器）：

    *Unordered Set/Multiset* ：内部是hash table做的

    *Unordered Map/Multimap* ： 内部是hash table做的

*hash table* 公认最好用的Separete Chaining

##### vector

特性：可以扩展

放100w个随机元素进去，用try&catch包装，万一有异常，执行abort()

vector是二倍增长，执行完之后：（成长是在另外一个地方把之前的拷贝过去）

    size：100w

    capacity：1048576

    总共花掉：3063ms

使用find查找，以及使用sort排序后用二分查找

    find花掉 0ms(按序查找，刚好在第一个)

    sort并bsearch花掉 2765ms

##### list

特性:就是一个双向链表

放入100w个随机元素进去，依旧用try&catch包装

执行之后：

    总共花费：3265ms

    size：100w

    max_size：357913941（按理而言只要内存供应就可以一直放，不合常理）（后续解释）

    find花费：16ms

    sort花费：2312ms（这次调用的是容器内部自己的sort，一般自己提供的sort都比标准库快）

list不能进行二分查找

##### forwoard-list

特性：一个单向链表

加入100w随机元素

    时间花销：3204ms

    sort排序：2656ms

    find查找：15ms（循序查找）

##### slist（非标准库，和forwoard-list一样）

其代码放在

```cpp
#include<ext\slist>
```

##### deque

特点：两边也可以扩充

一段一段的，一个一个的**buffer**构成

**其结构为：[map] -> buffer1 | buffer2 | buffer3 ...**，所以支持随机访问

分段连续（连续是一种假象，但使用者感觉是连续的）

所以其扩充的时候相当于加入新的buffer即可

放入随机的100w个元素

    花费时间：2704ms

    size：100w

    find一个元素：15ms

    sort花费：3110ms（没有自己的sort，用的全局的）

##### stack

栈  一端进出，先进后出（push，pop）

一个deque相当于包含了一个stack

放入30w个随机元素：

    花费：812ms

    使用top()查看栈顶元素

##### queue

队列 先进先出，一端近一端出（push，pop）

一个deque相当于包含了一个queue

放入30w个随机元素

    花费：890ms

    使用front(),back()查看队头，队尾

由于从技术而言stack和queue都是由deque实现，所以有时候不把二者称为容器，称为容器的适配器，所以二者不提供iterator

##### multiset

multiset及其之后的关联式容器可以想象成小型的关联数据库，其查找非常快

特性：key就是value，value就是key

放入100w个随机数据（不能用set，随机数可能会重复）

    时间开销：6609ms

    size：100w

    不用排序，其本身有序

    ::find一个元素：203ms（全局find）

    find()一个元素：0ms（容器自带的，由于单位是ms而时间过短，所以是0ms）

其插入元素使用insert()

    两个find性能差异的**本质区别为：std::find为线性扫描，而c.find利用了数据结构**

##### multimap

特性：key和value是分开的，内部由红黑树实现

放入100w个随机数

    时间开销：4812ms

    find：0ms

<mark>multimap不可以使用[]做insertion</mark>

由于放入的是key和value的组合，所以放入时需要使用标准库的**pair（一对东西）**去放入

##### unordered_multiset

特性：使用hash_table

set/multiset，map/multimap都有严谨的数学支撑，而unordered_set/multiset,unordered_map/multimap属于经验之谈

使用insert()放入100w个随机元素

    时间开销：4406ms

    bucket_count()：1056323 篮子的个数（哈希表的特性）>元素个数是合理的

    load_factor()：0.94668 载重因子

    max_load_factor: 1

    max_bucket_count(): 357913941

    ::find ：109ms

    find() ：0ms

经验之谈：如果元素个数大于篮子个数，这个时候就需要扩充篮子个数了

##### unordered_multimap

插入100w个元素

    时间花销：4313

    size：100w

    find：0ms

关联式容器，最适合大量查询的查找

##### set

key必须独一无二的

插入100w个随机元素

    时间开销：3922

    size()：32768 实际上只有这么多

其余和multiset一样

##### map

插入100w个随机元素

    时间开销：4890

    size()：100w 代码中写的是key按照for循环放的

    find：0ms

```cpp
for(long i = 0;i < value; ++i){
    ....
    c[i] = string(buf);//这里可以使用[]去
}
```

<mark>map可以使用[]做insertion</mark>

# 3.19

##### 使用分配器allocator

容器本来就有一个默认的分配器

```cpp
void test_list_with_special_allocator(){
    cout << "\ntest_list_with_special_allocator()..."
    list<string,allocator<string>> c1;
    list<string,__gnu_cxx::malloc_allocator<string>> c2;
    list<string,__gnu_cxx::new_allocator<string>> c3;
    list<string,__gnu_cxx::__pool_allocator<string>> c4;
    list<string,__gnu_cxx::__mt_allocator<string>> c5;
    list<string,__gnu_cxx::bitmap_allocator<string>> c6;
}
int choice;
long value;
    cout<<"select:";
    cin>> choice;
    if(choice !=0){
        cout<<"how many elements:";
        cin >> value; 
    }
char buf[10];
clock_t timeStart = clock();
    for(long i = 0;i<value;++i){
        try{
            snprintf(buf,10,"%d",i);
            switch(choice){
                case 1 : c1.push_back(string(buf));
                            break;
                case 2 : c2.push_back(string(buf));
                            break;
                case 3 : c3.push_back(string(buf));
                            break;
                case 4 : c4.push_back(string(buf));
                            break;
                case 5 : c5.push_back(string(buf));
                            break;
                case 6 : c6.push_back(string(buf));
                            break;
            }
        }
        catch(exception& p){
            cout<<"i=" << i << " " << p.what() << endl;
            abort();
        }
    }
    cout << "a lot of push_back(),milli-seconds :" <<
            (clock()-timeStart) << endl;
```

##### OOP vs GP（Generic Programming）

OOP企图将data和methods关联在一起

GP却是将data和method分开来

```cpp
//data structures
template<class T,class Alloc = alloc>
class vector{
    ...
}

//algorithms
//二者通过iterator联系
template<typename _RandomAccessIterator,typename _Compare>
inline void sort(_RandomAccessIterator __first,
                    _RandomAccessIterator,__last,
                    _Compare __comp)
{
    //标准库这里采用的是随机访问迭代器，所以在list里边需要自己写自己的sort
    ...
}
```

**采用GP好处**：

    Containers和Algorithms团队可各自闭门造车，期间使用iterator沟通即可

    Algorithm通过iterator确定操作范围，并通过iterators取用Container元素

所有algorithms，其内部最终**涉及元素**本身的操作，无非就是<mark>**比大小**</mark>

##### 阅读源码必要之基础

**操作符重载operator**

有4个操作符不能重载(::)、(.)、(.*)、(?:)

**模板template**

1.普通模板

2.函数模板 function templates

```cpp
template<class T>
inline
const T& min(const T& a,const T& b){
    return b < a ? b : a;
}
```

编译器会对function template进行**实参推导**

3.member template成员模板

**特化Specialization**

设计模板的时候，一般都很泛化，但当有一些特定的类型传入的时候有更好的解法

这个时候就需要特化

```cpp
//泛化
template<class Key> struct hash { };
//特化
__STL_TEMPLATE_NULL struct hash<char>{
    ...
};
```

**偏特化partial Specialization**

```cpp
//泛化
template <class T,class Alloc = alloc>
class vector{
    ...
};
//偏特化
template<class Alloc>
class vector<bool,Alloc>{
    ...
};
```

所谓局部，是数量上的局部

也有范围上的局部

```cpp
//泛化
template<class Iterator>
struct iterator_traits{
    ...
};
//偏特化
template<class T>
struct iterator_traits<T*>{
    ...
};
template<class T>
struct iterator_traits<const T*>{
    ...
};
```

##### 分配器allocators

一般情况下不建议使用

**allocator 本质目标**

1. 降低系统调用（malloc/free）

2. 减少内存碎片

3. 提高小对象分配效率

**operator new**：里边调用malloc

**malloc**：给你的内存比你需要的多了不少东西

    按比例而言：要的越少附加的越多

**VC6中**，allocator实现（\<xmemory>）

    allocator当他分配内存的到时候调用operator new，operator new内部调用了malloc

    其deallocate调用的是operator delete，其内部调用了free

**VC6**的allocator只是以**\::operator new**和**\::operator delete**完成allocate()和deallocate()，没有任何特殊设计（BC5，G2.9中也是如此）

```cpp
int *p = allocator<int>().allocate(512,(int*)0);
allocator<int>().deallocate(p,512);//居然需要记得有多少个空间，几乎没人记得
//所以不建议直接使用分配器
```

G++\<defalloc.h>有这样的注释：不要使用这个文件，这个SGI STL使用的是另外一个allocator，这个文件没有被include到任何文件中

G2.9所使用的标准库，alloc实现\<stl_alloc.h>,关于这个的讨论，详细将会在内存管理中讨论

其主要诉求就是**尽量减少malloc的次数**（避免额外开销）

额外开销中：cookie记录内存

但是在容器中，不需要cookie

**G2.9** alloc中，有一堆链表管理着内存（#1，#2...#15），每一个#管理一块内存，并且管理的大小为8的倍数（8，16，24...），假设需要50bit的内存，则会先扩容到56，再去找相应的链表，链表malloc到一大块内存用单向链表进行切割，切割成一块一块的，这一块一块的就不带cookie

**G4.9**其allocator中使用了另外一个分配器：new_allocator效果类似VC6，为什么会把之前好多舍弃呢？并不清楚

G4.9中所附的标准库，有许多extention allocators(之前提到的那一堆)

2.9中的alloc在4.9中名为**\__pool_alloc**依然可以使用

```cpp
vector<string,__gnu_cxx::__pool_alloc<string>> vec;
```

**STL allocator本质是一个“二级分配器”** 

##### 容器 结构与分类

以下以缩排的形式表达“基层与衍生层”的关系

所谓衍生，并非继承（inheritance）而是复合（composition）

**序列式容器**：（为这个容器设计一个obj，这个obj的大小）

-array 

-vector（连续空间）12 vs. 12

--heap（以算法形式呈现）

---priority_queue

-list（双向）4 vs. 8

-slist（单向非标准）4 vs. 4 

-deque（分段连续空间）40 vs.40

--stack/queue 40 vs. 40

**关联式容器**：

-rb_tree（非公开）

--set/map/multiset/multimap 12 vs. 24

-hashtable（非公开）

--unordered_set/map/multiset/multimap 20 vs. 28

**大小指的是容器本身的大小**
