---
cover: >-
  https://images.unsplash.com/photo-1670439073919-2a95bb16ea56?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHJhbmRvbXx8fHx8fHx8fDE3MTY1ODg3MDh8&ixlib=rb-4.0.3&q=85
coverY: 0
---

# 选择排序

选择排序是每次从剩余未排序的队列中选择最小的元素进行交换，直到剩余元素个数为1

{% hint style="info" %}
选择排序优点是交换次数少，对于一些交换开销大的应用场景，可以考虑使用
{% endhint %}

```java
int[] array;
for(int i=0;i<array.length-1;i++){
    int minIndex=i;//初始化最小值下标
    for(int j=i+1;j<array.length;j++){
       if(array[minIndex]>array[j]) {
          minIndex=j;//更新最小下标位置
       }  
    }
    if（minIndex!=i){
       swap(array,minIndex,i);//交换
    }     
}
```

