#### filter （过滤）

```python
# filter 对可迭代对象进行过滤，的得到的是一个filter
# python2的时候是内置函数，python3 修改成了一个内置类

ages = [12,23,30,17,16,22,19]
# filter可以给定两个参数，第一个参数是函数， 第二个参数是可迭代对象
# filter结果是一个filter类型的对象，filter对象也是一个可迭代对象
x = filter(lambda ele: ele > 18,ages)
# print(x)  # <filter object at 0x0000019B8B4B4408>
for a in x:
    print(a)
    
adult = list(x)
print(adult)
```

#### map

```python
ages = [12, 23, 30, 17, 16, 22, 19]
m = map(lamba ele: ele + 2, ages) # 每一个元素执行函数内容
print(list(m))
```

#### reduce

```python
# 以前是内置函数
# 内置函数和内置类都在builtins.py文件里
form functools import reduce
scores = [100, 89, 76, 87]
reduce(lamba ele1, ele2: ele1 + ele2, sores)
print(reduce) 
```

 