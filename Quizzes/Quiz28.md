# Quiz 028

![Captura de tela 2024-12-10 051758](https://github.com/user-attachments/assets/f5e44e43-810c-4bc6-939f-f4bff22c730c)


## Paper Work

## Code

```py
import requests
from matplotlib import pyplot as plt
import matplotlib
from my_lib import moving_average
import numpy as np

server_ip = "192.168.4.137"
request = requests.get(f"http://{server_ip}/readings") #register is a set of commands that the public can't access
readings = request.json()["readings"][0]

values = []
for r in readings:
    if r["sensor_id"] == 11:
        values.append(r["value"])
print(values)
plt.plot(values)
plt.show()

y = values[600:1600]

def moving_average(windowSize:int, y:list) -> list:
    y_smoothed = []
    for i in range(0,len(y)-windowSize):
        y_section = y[i:i+windowSize]
        y_average = sum(y_section)/windowSize
        y_smoothed.append(y_average)
    return y_smoothed

temp_y = moving_average(50, y)
x = [i for i in range(0,len(temp_y))]

def linear_model (x,m,b):
    return m*x + b

m, b = np.polyfit(x, temp_y, deg = 1)
x_linear = [min(x), max(x)]
y_linear = [linear_model(min(x),m,b), linear_model(max(x),m,b)]

plt.subplot(2,1,1)
plt.plot(temp_y, color ="blue", linewidth = 2)
plt.plot(x_linear, y_linear)
plt.ylabel("Temperature")

model = []
a,b,c = np.polyfit(x,temp_y,deg=2)
for i in x:
    model.append(a*i**2 + b*i + c)
print(a,b,c)
plt.subplot(2,1,2)
plt.plot(temp_y, color ="blue", linewidth = 2)
plt.plot(x, model)
plt.ylabel("Temperature")
plt.show()
```

## Proof of Work

![Captura de tela 2024-12-10 054015](https://github.com/user-attachments/assets/0ce3b056-8054-45c0-af70-57fa838f9677)


