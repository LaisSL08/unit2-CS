# Quiz 027

![Captura de tela 2024-12-10 051738](https://github.com/user-attachments/assets/6802a910-0aae-406a-8462-7fe912820630)

## Code

```py
def sort_dict(in_dict):
  only_num = sorted([x for x in in_dict.values() if isinstance(x, int)])
  new_dict1 = dict()
  new_dict2 = in_dict.copy()
  for i in only_num:
    for k, v in in_dict.items():
      if v == i:
        new_dict1[k]=v
        new_dict2.pop(k)

  return {**new_dict1,**new_dict2}
# Test
d = {'apple': 5, 'banana': 2, 'orange': 8, 'grape': 1}
print(sort_dict(d))

d = {'python': 3, 'java': 8, 'c++': 5, 'javascript': 1 }
print(sort_dict(d))

d = {'apple': 'red', 'banana': 2, 'orange': 'orange', 'grape': 1, 'kiwi': 'brown', 'pear': 8 }
print(sort_dict(d))
```
```.py
import math
from matplotlib import pyplot as plt
x = []
for i in range(100):
  x.append(i/100)
y = [math.sin(2*math.pi*i) for i in x]

plt.plot(x,y)
plt.legend(['$sin(2 \pi x)$'])
plt.xlabel('X-Axis')
plt.ylabel('Y-Axis')
plt.grid()
plt.show()
```
## Proof of Work

![Captura de tela 2024-12-10 052109](https://github.com/user-attachments/assets/b715c4ea-fbea-4d2e-9dde-142471318d05)

![Captura de tela 2024-12-10 052213](https://github.com/user-attachments/assets/b8937476-3626-4a45-8c0a-96b850555c49)






