## Welcome to PAT analyse


### 1037
输入格式：

输入在 1 行中分别给出 P 和 A，格式为 Galleon.Sickle.Knut，其间用 1 个空格分隔。这里 Galleon 是 [0, 10
^7] 区间内的整数，Sickle 是 [0, 17) 区间内的整数，Knut 是 [0, 29) 区间内的整数。

输出格式：
在一行中用与输入同样的格式输出哈利应该被找的零钱。如果他没带够钱，那么输出的应该是负数。

输入样例1：
10.16.27 14.1.28
输出样例1：
3.2.1
```markdown

#include<stdio.h>


int main(){
	int a1,a2,a3,b1,b2,b3,c1,c2,c3;
	int sum1,sum2,sum3;
	scanf("%d.%d.%d",&a1,&b1,&c1);
	scanf("%d.%d.%d",&a2,&b2,&c2);
	sum1 = a1 * 17 * 29 + b1 * 29 + c1;
	sum2 = a2 * 17 *29 + b2 * 29 + c2;
	sum3 = sum2 - sum1; 
	if(sum3 < 0){
		sum3 = - sum3;
		printf("-");
	}
	a3 = sum3 / (17 * 29);
	b3 = sum3 % (17 * 29) /29;
	c3 = sum3 % (17 * 29) % 29;
	printf("%d.%d.%d",a3,b3,c3);
	return 0;
}


```


### 解析

类似于单位换算，先将其换位最小单位，
即sum1 = a1 * 17 * 29 + b1 * 29 + c1;
	sum2 = a2 * 17 *29 + b2 * 29 + c2;
然后就进行判断，最后再将其换位最小单位。
可注意点：此方法中未将‘.’按照字符来输入，而是直接带过，则省事。

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
