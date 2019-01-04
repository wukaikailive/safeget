# safeget
This a lib for safe get javascrpt's object.
这是一个用于安全获取对象/数组的属性/元素的库。

## 使用方式

```import safeGet from '你放置库的目录'```

或

```import {safeGetByArray} from '你放置库的目录'```
## 测试
```
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
```

```
safeGet(obj,"b.d[0]f[1][0]") // 2

safeGetByArray(obj,"b.c","b.d[0]f[1][0]","b.d[0].g.h") // [1,2,2]
```
## 支持

1. 支持d[0]f[1]这种情形，即两个调用直接在不影响语义的情况下省略"."。

## 性能对比
