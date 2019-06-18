####  diff算法简析

-  组件、列表、元素

-  DIFF算法在执行时有三个维度，分别是Tree DIFF、Component DIFF和Element DIFF，执行时按顺序依次执行，它们的差异仅仅因为DIFF粒度不同、执行先后顺序不同。

-  Tree DIFF是对树的每一层进行遍历，如果某组件不存在了，则会直接销毁

-  如果有左右两个