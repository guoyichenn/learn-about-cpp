# 基础语法

## hello world

```c++
#include <iostream>
using namespace std;

// main() 是程序开始执行的地方

int main()
{
   cout << "Hello World"; // 输出 Hello World    return 0; 
} 

// 运行 
// 1. 编译：g++ hello-world.cpp 
// 2. 执行编译后文件 ./a.out 
```

## 数据类型

* bool
* char
* int
* float
* double
* void
* wchar_t 宽字符类型

---

* 修饰类型
* signed 有符号
* unsigned 无符号
* short
* long
* 例子： char -128 到 127 或者 0 到 255； unsigned char：0 到 255

---
typeof 可以申明类型变量

---
枚举
enum enum-name { list of names } var-list;

## 常量

```c++
// 方法1
#define identifier value
// 方法2
const type variable = value;
```

## 修饰符类型

这个例子非常的迷

```c++
#include <iostream>
using namespace std;
/*
 * 这个程序演示了有符号整数和无符号整数之间的差别
*/
int main()
{
   short int i;           // 有符号短整数
   short unsigned int j;  // 无符号短整数

   j = 50000;

   i = j;
   cout << i << " " << j;

   return 0;
}

// 结果 -15536 50000
```

## 存储类

* auto 存储类是所有局部变量默认的存储类
* register 用于定义存储在寄存器中而不是 RAM 中的局部变量（不是RAM中， 所以寄存器是什么鬼）
* static 存储类指示编译器在程序的生命周期内保持局部变量的存在
* extern 存储类用于提供一个全局变量的引用，全局变量对所有的程序文件都是可见的
* mutable 适用于类

```c++
    // 用法
    static int count = 10
```

## 算数运算符

### 基础的运算符就不介绍了

### 位运算符 应用于二进制

* &
* ｜
* ^ ( 1^1 = 0)
* ~(反转二进制)
* << (左移 00111100<<2 = 11110000)

### 杂项运算符

* sizeof // sizeof(a)
* Condition ? X : Y  //三目
* ， //逗号 顺序执行运算
* . -> 点和箭头应用于对象中
* Cast 强转类型 // int(2.2000)
* & 指针运算符  // &a; 将给出变量的实际地址。
* 指针运算符 // *var; 将指向变量 var。

### 运算符优先级（掠过）

## 循环

while | for | do while

## 判断

if | switch

## 函数

```c++
return_type function_name( parameter list )
{
   body of the function
}
```

## 数字

### 数学函数 sin cos tan

double cos(double);

### 随机数

rand() 生成随机数之前必须先调用 srand() 函数

```c++
#include <iostream>
#include <ctime>
#include <cstdlib>

using namespace std;
 
int main ()
{
   int i,j;
 
   // 设置种子
   srand( (unsigned)time( NULL ) );

   /* 生成 10 个随机数 */
   for( i = 0; i < 10; i++ )
   {
      // 生成实际的随机数
      j= rand();
      cout <<"随机数： " << j << endl;
   }

   return 0;
} 
```

## 数组

type arrayName [ arraySize ];

```c++
double balance[5] = {1000.0, 2.0, 3.4, 17.0, 50.0};
```

## 字符串

char greeting[] = "Hello";
string str1 = "Hello";

## 指针

int  var1;
cout << &var1 //0xbfebd5c0

```c++
#include <iostream>

using namespace std;

int main ()
{
   int  var = 20;   // 实际变量的声明
   int  *ip;        // 指针变量的声明

   ip = &var;       // 在指针变量中存储 var 的地址

   cout << "Value of var variable: ";
   cout << var << endl;

   // 输出在指针变量中存储的地址
   cout << "Address stored in ip variable: ";
   cout << ip << endl;

   // 访问指针中地址的值
   cout << "Value of *ip variable: ";
   cout << *ip << endl;

   return 0;
}
// Value of var variable: 20
// Address stored in ip variable: 0xbfc601ac
// Value of *ip variable: 20
```

## 引用

引用变量是一个别名，也就是说，它是某个已存在变量的另一个名字。一旦把引用初始化为某个变量，就可以使用该引用名称或变量名称来指向变量。

与指针的区别

* 不存在空引用。引用必须连接到一块合法的内存。
* 一旦引用被初始化为一个对象，就不能被指向到另一个对象。指针可以在任何时候指向到另一个对象。
* 引用必须在创建时被初始化。指针可以在任何时间被初始化。

int    i = 17;
int&    r = i;

## 日期 & 时间

需要在 C++ 程序中引用 <ctime> 头文件。

有四个与时间相关的类型：clock_t、time_t、size_t 和 tm。类型 clock_t、size_t 和 time_t 能够把系统时间和日期表示为某种整数。

## 基本的输入输出

### I/O 库头文件

<iostream>
<iomanip>
<fstream>

### 输出 (cout)

预定义的对象 cout 是 ostream 类的一个实例。cout 对象"连接"到标准输出设备，通常是显示屏。cout 是与流插入运算符 << 结合使用的，如下所示：

cout <<

### 标准输入流（cin）

```c++
#include <iostream>
 
using namespace std;
 
int main( )
{
    char name[50];
 
    cout << "请输入您的名称： ";
    cin >> name;
    cout << "您的名称是： " << name << endl;   
} 
```

### 标准错误流（cerr）

cerr << "Error message : " << str << endl; 

### 标准日志流（clog）

clog << "Error message : " << str << endl;

## 数据结构


```c++
struct Books
{
   char  title[50];
   char  author[50];
   char  subject[100];
   int   book_id;
```

给数据结构中成员赋值 strcpy( Book2.title, "Telecom Billing");

### 数据结构 指针

```c++
#include <iostream>
#include <cstring>
 
using namespace std;
void printBook( struct Books *book );

struct Books
{
   char  title[50];
   char  author[50];
   char  subject[100];
   int   book_id;
};
 
int main( )
{
   struct Books Book1;        // 声明 Book1，类型为 Book
   struct Books Book2;        // 声明 Book2，类型为 Book */
 
   // Book1 详述
   strcpy( Book1.title, "Learn C++ Programming");
   strcpy( Book1.author, "Chand Miyan"); 
   strcpy( Book1.subject, "C++ Programming");
   Book1.book_id = 6495407;

   // Book2 详述
   strcpy( Book2.title, "Telecom Billing");
   strcpy( Book2.author, "Yakit Singha");
   strcpy( Book2.subject, "Telecom");
   Book2.book_id = 6495700;
 
   // 通过传 Book1 的地址来输出 Book1 信息
   printBook( &Book1 );

   // 通过传 Book2 的地址来输出 Book2 信息
   printBook( &Book2 );

   return 0;
}
// 该函数以结构指针作为参数
void printBook( struct Books *book )
{
   cout << "Book title : " << book->title <<endl;
   cout << "Book author : " << book->author <<endl;
   cout << "Book subject : " << book->subject <<endl;
   cout << "Book id : " << book->book_id <<endl;
} 
```

### 定义类型 typedef
typedef struct
{
   char  title[50];
   char  author[50];
   char  subject[100];
   int   book_id;
}Books;

Books Book1, Book2;

---

typedef long int *pint32;
 
pint32 x, y, z;