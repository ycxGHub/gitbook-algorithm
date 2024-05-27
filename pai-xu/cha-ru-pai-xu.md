# 插入排序

向一个有序队列中插入一个元素，直到剩余元素个数为1。

{% hint style="info" %}
插入排序是稳定性的，但是交换次数多
{% endhint %}

```java
int[] arr;
for(int i=1;i<arr.length;i++){
    int s=i;
    for(int j=i;j>=0;j--){
        if(arr[j]>arr[eIndex]){
            swap(arr,j,s);
            s=j;//更新需要插入的下标位置
        }else{
            break;
        }
    }
}
```
