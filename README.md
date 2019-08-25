# Constant-Pointer-vs-Pointer-to-Constant

# 指针常量：Constant Pointer
指针本身为一个常量，指向的可以是变量，但它指向的地址是不可以变动的。
 
⚠️第二句，"可以"这个词，指向的也可以是常量，即常量指针常量，Constant Pointer to Constant, 写作：const * const int a
 
# 常量指针：Pointer to Constant
常量的指针，指针只能指向常量，不能指向变量，但是它指向的地址是可以改变的。
 
# Tips
看写法，const * 就是指针常量，* const 就是常量指针。
 
 
 
例子1:
``` cpp
void main()
{
  char *str1 = {"Hello"};
  char *str2 = {"Hi"};
  char * const ptr1 = s``` tr1;   //指针常量，地址不变，地址内容可变
  
  ptr1 = str2; //错误，因为ptr1是个不能变的指针
  
  printf("%s n",*ptr1);
}
//编译错误
```  
 
例子2:
``` cpp
void main()
{
  char *str1 = {"Hello"};
  char *str2 = {"Hi"};
  char * const ptr1 = str1;   //指针常量，地址不变，地址内容可变
  
  *ptr1 = "A"; //正确，因为*ptr1是指向的地址的内容，可以变化
  
  printf("%c n",*ptr1);
}

//输出A
``` 
例子3:
``` cpp
void main()
{
  char *str1 = {"Hello"};
  char *str2 = {"Hi"};
  const char *ptr = str1;   //常量指针，地址可变，内容不可变
  
  ptr1 = str2;  //正确，因为ptr1是个能变的指针，可以指到其他位置
  
  printf("%s n",*ptr1);
}
``` 
