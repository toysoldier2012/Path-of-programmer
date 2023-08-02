#hashset

# 特点

- `HashSet` (无序，唯一): 基于 `HashMap` 实现的，底层采用 `HashMap` 来保存元素
- 按照添加内容的 hash 值排序
- 先通过 `hashCode()` 确定保存位置，再通过 equals 确定数值是否一致，再保存，全部一致就不保存
- 可以储存 null 值
- 初始长度为 16
- 线程不安全
- 底层为 HashMap
