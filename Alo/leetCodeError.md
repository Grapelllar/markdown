# leetCodeError

1、

Line 14: Char 29: error: member reference base type 'int [30005]' is not a structure or union
        for(int i = 0; i < a.size() ; i++){
                           ~^~~~~
1 error generated.

表达式必须具有类类型，但它具有类型"int * 

这种报错会出现在两种情况：

1. 类没有数据成员时，使用类定义对象时带括号了；
2. 定义类时以指针方式定义，对象调用函数时使用“.”。

````c++
#include <iostream>
using namespace std;
 
int main(int argc, char **argv){
  int a[10] = {0,1,2,3,4,5,6,7,8,9};
  int length = sizeof(a)/sizeof(a[0]);
  cout << "数组长度为：" << length << endl;
}
````