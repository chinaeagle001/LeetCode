Write a function that takes an unsigned integer and returns the number of ’1' bits it has (also known as the Hamming weight).

For example, the 32-bit integer ’11' has binary representation 00000000000000000000000000001011, so the function should return 3.

##解题思路1
每一位分别和1进行与运算，统计结果不为0的位数。

##实现代码1
```C++
//Runtime:10 ms
#include <iostream>
#include "inttypes.h"
using namespace std;

class Solution {
public:
    int hammingWeight(uint32_t n) {
        int i = 0;
        while (n)
        {
        	i += n & 0x1;
        	n >>= 1;
        }
        
        return i;
    }
};

int main()
{
	Solution s;
	cout<<s.hammingWeight(11)<<endl;
	return 0;
}
```

##解题思路2
每次n&(n-1)可以将n里面的值为1的位数减少一位

##实现代码2
```C++
//Runtime:11 ms
class Solution {
public:
    int hammingWeight(uint32_t n) {
        int i = 0;
        while (n)
        {
        	n &= (n-1);
        	++i;
        }
        
        return i;
    }
};
```