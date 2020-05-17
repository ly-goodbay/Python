```python
# sort相关的方法
# 有几个内置函数和内置类，用到了匿名函数

nums = [4,8,9,6,2,5]

# 列表的sort方法，会直接对列表排序

nums.sort()
print(nums)

# sorted 内置函数，不会改变原有的数据，而是生成一个新的有序的列表

sorted(nums) # x = sorted(nums)
print(nums)  # print(x)

students = [
    {'name': 'zhangsan','age': 18,'score': 98,'height':180},
    {'name': 'lisi','age': 21,'score': 97,'height':185},
    {'name': 'jack','age': 22,'score': 100,'height':175},
    {'name': 'tony','age': 17,'score': 90,'height':176},
    {'name': 'henry','age': 20,'score': 95,'height':172},
]
# 字典和字典之间不能使用比较运算
# students.sort()

# 需要传递参数key 指定规则
# key的参数类型是函数
def foo(elc):
    return elc['age'] # 按照返回值告诉sort方法，按照那个元素的属性进行排序

students.sort(key = foo)
print(students)

students.sort(key=lamba elc: elc['score'])
print(students)
```

