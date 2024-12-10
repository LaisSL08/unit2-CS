# Quiz 025

![Captura de tela 2024-12-10 050738](https://github.com/user-attachments/assets/29c344e5-cb52-446e-99e2-ca4556ca6978)

## Code

```py
def count_letter(in_dict, string):
  for k in in_dict.keys():
    in_dict[k] = string.lower().count(k)
  return in_dict

# Test
d = {'w':0,'l':0,'c':0}

print(count_letter(d,'Hello World'))

d = {'a':0,'e':0,'i':0,'o':0,'u':0}

print(count_letter(d,'Why did I choose CS?'))
```

![Captura de tela 2024-12-10 051155](https://github.com/user-attachments/assets/ad10775a-6f88-4d81-809c-b54388f810ba)


## Proof of Work

![Captura de tela 2024-12-10 051040](https://github.com/user-attachments/assets/402f3c3b-2349-4bb9-9520-859d96b44037)





