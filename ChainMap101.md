
두 개의 딕셔너리를 이어준다.

도식도

a --- b

{'a': 'A', 'c': 'C'} ---  {'b': 'B', 'c': 'D'}


```
import collections

a = {'a': 'A', 'c': 'C'}
b = {'b': 'B', 'c': 'D'}

m = collections.ChainMap(a, b)

print(m)
print('Individual Values')
print('a = {}'.format(m['a'])) #값을 a딕셔너리에서 가져옴
print('b = {}'.format(m['b']))
print('c = {}'.format(m['c']))
print()

print('Keys = {}'.format(list(m.keys())))
print('Values = {}'.format(list(m.values())))
print()

print('Items:')
for k, v in m.items():
    print('{} = {}'.format(k, v))
print()

print('"d" in m: {}'.format(('d' in m)))
```


결과
```
ChainMap({'a': 'A', 'c': 'C'}, {'b': 'B', 'c': 'D'})

Individual Values
a = A
b = B
c = C

Keys = ['a', 'b', 'c']
Values = ['A', 'B', 'C']

Items:
a = A
b = B
c = C
```
