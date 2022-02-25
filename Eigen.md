### Eigen::Map 类

作用是复用一段数据内存，将其映射为Eigen的数据格式。

#### 1.定义
```
Map<Matrix<typename Scalar, int RowsAtCompileTime, int ColsAtCompileTime> >
```

#### 2.示例

```
double p[9] = {1,2,3,4,5,6,7,8,9};
Map<MatrixXd> A(p+1 , 2,4); 
//等效表达 Map<Matrix<double,2,4>> A = Map<Matrix<double,2,4>>(p+1);
```
经上述定义，矩阵 A 为 2*4 矩阵，且矩阵元素与数组 p[1~8] 一一对应：
```
cout<<A;
------------
2 4 6 8
3 5 7 9
```
复用内存性质：
```
A(1,2) = 10;
cout << p[6];
------------
10
```