```cpp
int a = 5, b = 10;

a = a ^ b;
b = a ^ b; // (a^b)^b = a;
a = a ^ b; // (a^b)^(a) = b;

```