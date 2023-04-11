实践中遇到STL的问题

```cpp
bool findNumberIn2DArray(vector<vector<int>>& matrix, int target) {

}
```

🤣写leetcode时遇到的题，给了我一个二维vector类型的matrix，我想按行遍历矩阵

```cpp
bool findNumberIn2DArray(vector<vector<int>>& matrix, int target) {
    for(int i = 0;i<matrix.size();i++){}
}
```

> matrix.size()是行数；matrix[0].size()是列数

🤣同样是这个题，有这样一个样例 matrix = [[]]

可知matrix.size() == 1, matrix[0].size == 0

因为matrix[0]中没有元素，因此 matrix\[0][0]是没有意义的，对吧。因此，编译器会报错

`runtime error: reference binding to null pointer of type 'int' (stl_vector.h)` 

解决办法：在使用了matrix\[i][j]的语句前，加上判断 if(matrix.size()!=0&&matrix[i].size()!=0)

第一个matrix.size()!=0是防止这样的样例，matrix = []

第二个matrix[i].size() !=0是防止这样的样例，matrix=[ [1,2] , [] ]  或者 matrix = [[]] 等





