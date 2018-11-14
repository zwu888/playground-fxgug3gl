# 
```C++ runnable
#include<iostream>

struct foo
{
    // (a):
    void bar() { std::cout << "gman was here" << std::endl; }

    // (b):
    void baz() { x = 5; }

    int x;
};
int main()
{
    static_cast<foo*>(NULL)->bar(); //works
    foo* f = new foo();
         f = nullptr;
    f->bar(); // (a)
    f->baz(); // (b) // use this pointer, will coredump
}
