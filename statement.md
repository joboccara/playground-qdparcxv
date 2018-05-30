```C++ runnable
#include <iostream>

template<typename T>
class Wrapper
{
public:
    Wrapper(T const& value) : value_(value) {}
    
    T const& get() const { return value_; }
    
private:
    T value_;
};

int main()
{
    using IntRefWrapper = Wrapper<int&>;
    int a = 42;
    IntRefWrapper intRefWrapper(a);
    
    intRefWrapper.get() = 43;

    std::cout << "a is now " << a << '\n';
}```
