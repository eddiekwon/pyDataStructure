
```python

import copy

a = [1, [1, 2, 3]]
b = copy.copy(a)    # shallow copy 발생     
print(b)    # [1, [1, 2, 3]] 출력
b[0] = 100  

print('b는 ',b)    # [100, [1, 2, 3]] 출력, 
print('a는 ',a)    # [1, [1, 2, 3]] 출력, shallow copy 가 발생해 복사된 리스트는 별도의 객체이므로 item을 수정하면 복사본만 수정된다. (immutable 객체의 경우)

print()

c = copy.copy(a)
c[1].append(4)    # 리스트의 두번째 item(내부리스트)에 4를 추가
print(c)    # [1, [1, 2, 3, 4]] 출력
print(a)    # [1, [1, 2, 3, 4]] 출력, a가 c와 똑같이 수정된 이유는 리스트의 item 내부의 객체는 동일한 객체이므로 mutable한 리스트를 수정할때는 둘다 값이 변경됨


# 추가로 해보는 시험.

d = copy.copy(a)
d[1][0] = 123
print('d는 ', d)
print('a는 ',a)  
# 요렇게 해도 마찬가지로 두개 모두 바뀌게 됨.
# 아하 알았다...맨 밖에 있는 자료가 아니라, 그 속에 있는 자료라면 바뀌는구나.
# 속 데이터만 변경됨.

x = [10,20,30,40]

whatThe = copy.copy(x)

whatThe[1] = 999
print('whatThe는 ',whatThe)    # [1, [1, 2, 3, 4]] 출력
print('x는 ',x)
 
# 요놈은 맨 밖의 데이터를 바꾸므로 두 객체가 다르게 됨.

```

결과는
```
Python 3.6.1 (default, Dec 2015, 13:05:11)
[GCC 4.8.2] on linux
   
[1, [1, 2, 3]]
b는  [100, [1, 2, 3]]
a는  [1, [1, 2, 3]]

[1, [1, 2, 3, 4]]
[1, [1, 2, 3, 4]]
d는  [1, [123, 2, 3, 4]]
a는  [1, [123, 2, 3, 4]]
whatThe는  [10, 999, 30, 40]
x는  [10, 20, 30, 40]
   
```

참고: https://blueshw.github.io/2016/01/20/2016-01-20-shallow-copy-deep-copy/
뒤쪽 소스는 추가로 코딩한 내용

