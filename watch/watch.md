```java
watch com.niuge.PrizeContext calculatePrize
    '{params,returnObj,throwExp}'
    " ! params[0].prizeRule.contains('rankTo')
        && params[0].settleType != 6
        && params[0].settleType != 4
        && params[1].anticipatedPrize == null " -n 5  -x 3
```
这个例子，说明如下符号可以使用：
- ** ！
- ** contais 函数
- ** &&
- ** 字符串和 null 的比较