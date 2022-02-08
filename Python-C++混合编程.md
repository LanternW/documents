
*适用于Linux*

#### 1. 采用动态链接库方式

C++的函数需要用 extern 描述才能被 Python 调用。新建一个名为 test.cpp 的文件：

```C++
#include <iostream>
using namespace std;
extern int test( int parm )
{
    cout<<"C++"<<endl;
    return parm + 1;
}
```
在 Linux 环境下编译：
```
g++ -o mylib.so -shared -fPIC test.cpp
```
得到 mylib.so 文件。

-----
python 调用代码：

```python
import ctypes
ll = ctypes.cdll.LoadLibrary
lib = ll('./mylib.so')
print(lib.test(4))
```
output:
```
C++
5
```