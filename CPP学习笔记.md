# CPP学习笔记

1. 排序赋值

~~~
class Solution {
//定义名为solution的类
public:
//共有，可在类外访问
    vector<int> arrayRankTransform(vector<int>& arr) {
//返回整形向量，函数名，&引用名为arr的向量
        vector<int> b = arr;
//赋值给名b
        sort(b.begin(), b.end());
//排序【默认升序】，降序可通过
/*
bool cmp(int x, int y) {  // 自定义比较函数，按照升序排列
    return x > y;
}
sort(b.begin(), b.end(), cmp);  // 使用自定义比较函数对 b 向量进行排序
*/
        b.erase(unique(b.begin(), b.end()), b.end());
//unique(b.begin(), b.end())返回一个指向第一个重复元素的迭代器，然后b.erase()函数将从该位置开始的所有重复元素删除，使得b中只保留了唯一的元素。
        for(auto &x: arr)
            x = upper_bound(b.begin(), b.end(), x) - b.begin();
//在循环中，for(auto &x: arr)用于遍历原始的arr向量中的每个元素。然后，upper_bound(b.begin(), b.end(), x)返回一个指向b中第一个大于x的元素的迭代器。通过计算该迭代器与b.begin()的距离，可以确定x在排序后的b中的排名。
将x更新为在向量b中查找大于x的第一个元素的位置，并将其与b.begin()的位置相减。
        return arr;
//最后，将每个元素的排名赋值给arr，并返回最终结果。
    }
};
~~~

