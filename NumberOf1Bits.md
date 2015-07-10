Write a function that takes an unsigned integer and returns the number of ��1' bits it has (also known as the Hamming weight).

For example, the 32-bit integer ��11' has binary representation 00000000000000000000000000001011, so the function should return 3.

##����˼·1
ÿһλ�ֱ��1���������㣬ͳ�ƽ����Ϊ0��λ����

##ʵ�ִ���1
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

##����˼·2
ÿ��n&(n-1)���Խ�n�����ֵΪ1��λ������һλ

##ʵ�ִ���2
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