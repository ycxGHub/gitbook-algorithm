# 快速排序

{% hint style="info" %}
快速排序是不稳定的排序，其最好情况与归并排序相同2NLgN，但是相比于归并排序它无需额外空间，最差情况N^2
{% endhint %}

简单说就是每一步找一个切分值pivot将其整个数据切分为 pivot左侧都不大于它，右侧不小于它的两个子数组，然后继续切分左右两侧的子数组，直到无法切分为止(也就是只有子数组只有一个元素时)。

伪代码如下：

<pre class="language-java"><code class="lang-java">void sort(int[] arr,int lo,int hi){
 if(hi&#x3C;=lo){
  return;
 }
 int mid=partition(arr,lo,hi);//切分
  sort(arr,lo,mid-1);
  sort(arr,mid+1,hi);
}
/**
**[lo,j-1]&#x3C;=V&#x3C;=[j+1,hi];
**其中a[j]=pivot
**/
int partition(int[] arr,int lo,int hi){
<strong>int v=arr[lo];//切分值
</strong><strong>int i=lo;//++i是i
</strong>int j=hi+1;//--j是hi
 while(true){
   while(v&#x3C;arr[++i]){if(i>=hi)break;}//从左往右找到一个比v大的元素
   while(v>arr[--j]){if(j&#x3C;=lo)break;}//从右往左找到一个比v小的元素
   if(i>=j){//寻找结束了
    break;
   }
   swap(arr,i,j);//交换两个元素
 }
 swap(arr,lo,j);//将j填入v元素
  return j;
}

</code></pre>

这里面比较容易产生问题 partition 方法中左右指针的边界问题。因为v值是在lo位置上右指针，**一定可以找到满足条件的j值**，我们需要考虑i的情况，i退出循环无外乎就两种情况

1. 若i\<j,一定是左右指针都找到了满足条件的值，所以直接交换即可（幸福总是相似的）
2. 若i>=j,则一定有\[lo,j-1]\<V, a\[j]<=V，\[j+1,hi]>V,此时交换lo和j 即可









