## 题目描述
练习 1.6： 修改Lissajous程序，修改其调色板来生成更丰富的颜色，然后修改SetColorIndex的第三个参数，看看显示结果吧。
## 分析及注释
- 首先书中`time.Now().UTC().UnixNano()`处的`UTC()`多余，根据描述`UnixNano()`返回的是自1970年1月1日 UTC以来的纳秒数，与 time 的时区无关，所以此处等价于`time.Now().UnixNano()`
- 自 go 1.20 以来 rand.Seed 方法被废弃，程序启动时会自动随机种子，此处可删除
- 颜色渐变通常可以采用 HSL 或者 HSV 色彩空间，通过调整色相实现。这里采用 HSV。
