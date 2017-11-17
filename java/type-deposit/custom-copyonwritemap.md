## 对于HashMap可能会产生fail-fast机制，参照CopyOnWriteArrayList，自定义实现CopyOnWriteMap

1. CopyOnWriteArrayList的核心概念就是：任何对array在结构上有所改变的操作\(add,remove,clear等\),CopyOnWriteArrayList都会copy现有的数据，







