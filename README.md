#### 数据结构
1. 线性表
  1. 顺序存储结构  
    顺序存储结构就是两个相邻的元素在内存中也是相邻的。  
    优点是查询的时间复杂度为O(1)  
    缺点是插入和删除的时间复杂度最坏能达到O(n)
  2. 链式存储结构  
    优点是插入和删除的时间复杂度为O(1)  
    缺点是访问的时间复杂度最坏为O(n)
2. 链表  
  链表就是链式存储的线性表。  
  根据指针域的不同，链表分为`单向链表`、`双向链表`、`循环链表`等等。
  1. 单向链表(slist)  
    每个元素包含两个域，`值域`和`指针域`，我们把这样的元素称之为`节点`。  
    每个节点的指针域内有一个指针，指向下一个节点，而最后一个节点则指向一个空值。  

#### 算法分析
##### 一、比较排序算法  
插入排序、归并排序、堆排序、快速排序都是比较排序算法。  
![排序复杂度](http://7i7io5.com1.z0.glb.clouddn.com/sort.PNG)  
1. 插入排序  
有5张牌(arr[5]={5,2,4,3,1})，先取第二张牌(key=arr[j], j=1)，拿key和它之前的每一位比较，比它大的则往后挪(arr[i+1]=arr[i])，最后将key插入，然后取下一个key。
```C
#define LEN 5
void insertion(int arr[])
{
    int i = 0;
    int j = 1;
    int key = 0;
    while (j < LEN)
    {
        key = arr[j];
        i = j - 1;
        while (arr[i] > key && i >= 0)
        {
            arr[i + 1] = arr[i];
            i--;
        }
        arr[i + 1] = key;
        j++;
    }
}
```