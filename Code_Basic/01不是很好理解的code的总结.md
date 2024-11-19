###程序一，一段不是很完善的快速排序子程序
###来自《变成珠玑》快速排序章节

```c
void qsort1(int l, int u)
{
    int i, m;
    int temp;
    if (l >= u)
        return;
    m = l;
    for (i = l + 1; i <= u; i++)
        if (a[i] < a[l])        //如果当前i小于l指向的受元素时就增长m并发生交换
            /*swap(++m, i);*/   //这样可以确保m指向遍历过的最后一个小于l指向的元素的元素
        {
            m++;
            temp = a[m];
            a[m] = a[i];
            a[i] = temp;
        }
    swap(l, m);
    qsort1(l, m - 1);
    qsort1(m + 1, u);
}
```
