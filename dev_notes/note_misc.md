...menustart

 - [Misc note](#545ef86f8085bb191435d59c503f1a74)
     - [二进制](#6168fb08fe64663a502a132c5589b73d)
     - [Respond to an unknown method call](#eb0862d2232fd2d27e0bf79a231e8841)

...menuend


<h2 id="545ef86f8085bb191435d59c503f1a74"></h2>

-----
-----

# Misc note

<h2 id="6168fb08fe64663a502a132c5589b73d"></h2>

-----

## 二进制

 - 对于一个整数 x 
    - x-1,x+1 都是 **有限制的，局部的，各位求反** 操作
    - x-1 
        - 受影响的pattern: 最右侧 10000的形式
        - 减去1 后的结果:  pattern 变成 01111 的形式
    - x+1
        - 受影响的pattern: 最右侧 01111 的形式
        - 加1 后的结果:  pattern 变成 10000 的形式
    - 所以
        - x & (x-1) : x 最右侧的bit 1 置0. (判断是否是2的幂, 以及统计bit 1的个数)
        - x & (x+1) : x 最右侧的bit 1 全部置0 (包含最低位)
        - x | (x-1) : x 最右侧的bit 0 全部置1 (包含最低位)
        - x | (x+1) : x 最后侧的bit 0 置1
        - 上述运算，其实就是把 受影响的pattern 全部置0 或 置1
    - 因为 ~x 是全部求反, x-1/x+1 是局部求反,   所以
        - ~x & (x+1) : 把 x 最右侧的 0 置为1， 其他位全部置0 
        - ~x & (x-1) : 把 x 最右侧的 0 全置为1 (包含最低位), 其他位(剩余高位)全部置位0 
    - 因为  -x=~x+1 , 所以
        - x & (-x) : 把 x 最右侧的 bit 1 以外的 位全部置0  (不考虑0的情况,结果一定是2的幂) 
 - 判断两个整数是否异号
    - 
    ```
    bool f = ((x ^ y) < 0); // true iff x and y have opposite signs
    ```
 - 判断一个数是否为2的n次幂：
    - 
    ```
    (v & (v - 1)) == 0;
    ``` 
 - 计算一个数含有多少个比特1:
    - 
    ```
    unsigned int v; // count the number of bits set in v
    unsigned int c; // c accumulates the total bits set in v
    for (c = 0; v; c++)
    {
      v &= v - 1; // clear the least significant bit set
    }
    ```


<h2 id="eb0862d2232fd2d27e0bf79a231e8841"></h2>

-----

## Respond to an unknown method call

[Respond to an unknown method call](https://rosettacode.org/wiki/Respond_to_an_unknown_method_call#Python)

