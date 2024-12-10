# Quiz 026

![Captura de tela 2024-12-10 051310](https://github.com/user-attachments/assets/f37abb97-cd7c-4456-99b3-564dd4809cd3)

## Paper Work

## Code

```py
def flip(in_dict):
  new_dict= dict()
  for k,v in in_dict.items():
    if v in new_dict:
      if isinstance(new_dict[v], list):
        new_dict[v]= [*new_dict[v],k]
      else:
        new_dict[v]= [new_dict[v],k]
    else:
      new_dict[v]=k

  return new_dict
# test
d = {'a':1,'b':2,'c':3}
print(flip(d))

d = {'bob':26,'alice':30,'carl':40}
print(flip(d))

d = {'q1':True,'q2':False,'q3':True}
print(flip(d))

d = {'q1':True,'q2':False,'q3':True, 'q4':True}
print(flip(d))
```
![Captura de tela 2024-12-10 051532](https://github.com/user-attachments/assets/e780e5a1-6e67-431f-82a3-86331d205519)

![Captura de tela 2024-12-10 051548](https://github.com/user-attachments/assets/3e579302-f9df-43ab-a53e-2a32f49af7b7)


## Proof of Work

![Captura de tela 2024-12-10 051451](https://github.com/user-attachments/assets/a702beef-158b-4ff8-9a37-4a837fc68c1c)



