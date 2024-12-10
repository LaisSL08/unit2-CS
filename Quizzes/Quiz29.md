# Quiz 029

![Captura de tela 2024-12-10 051816](https://github.com/user-attachments/assets/092411a5-e98d-4d99-933b-72b572c5e85d)

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

temp = []
pressure = []
for r in readings:
    if r["sensor_id"] == 11:
        temp.append(r["value"])
    if r["sensor_id"] == 12:
        pressure.append(r["value"])

new_temp = []
for i in pressure:
    new_temp.append(((i/1010)**5.25)*15)

average = []
for q in range(len(new_temp)):
    average.append((new_temp[q]+temp[q])/2)



plt.subplot(3,1,1)
plt.plot(temp, color ="blue", linewidth = 2)
plt.ylabel("Temperature")
plt.subplot(3,1,2)
plt.plot(new_temp, color ="blue", linewidth = 2)
plt.ylabel("Pressure")
plt.subplot(3,1,3)
plt.plot(average, color ="blue", linewidth = 2)
plt.ylabel("Average")
plt.show()
```

## Proof of Work

![Captura de tela 2024-12-10 054227](https://github.com/user-attachments/assets/7d22a2f2-67d6-4100-89e5-d6f3a062218a)



