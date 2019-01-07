# Safeget

A library for sage get nested attributes of JavaScript.

这是一个用于安全获取javascrpt对象/数组中深层次的属性/元素的库。

这个库的特色就是将表达式解析成抽象语法树，再来求值。
主要是为了学习和好玩，性能待测试。

## 使用方式

```
npm install --save @wukaikailive/safeget
```

```

import safeGet from '@wukaikailive/safeget'

import {safeGets} from '@wukaikailive/safeget'

let obj = {
        a: 2,
        b: {
          c: 1,
          d: [
            {
              f: [1, [2, 3]],
              g: {
                h: 2
              }
            }
          ]
        }
      }

safeGet(obj,"b.d[0]f[1][0]") // 2

safeGets(obj,"b.c","b.d[0]f[1][0]","b.d[0].g.h") // [1,2,2]
```
## 特性

1. 支持d[0]f[1]这种情形，即两个调用在不影响语义的情况下可以省略"."。
2. 多个连续的"."会被当作一个，如 b..c 等价于 b.c 。

## 性能对比
