# Quiz 031

![Captura de tela 2024-12-10 051850](https://github.com/user-attachments/assets/4a21ad22-4abe-49c8-bd23-d2aa62d440dc)

## Paper Work

## Code

```py
import matplotlib.pyplot as plt

plt.xlim(-4, 4)
plt.ylim(-4, 4)

xvalues = [-2+0.04*i for i in range(100)]
yvalues1 = [x**2 for x in xvalues]
yvalues2 = [-x**2 for x in xvalues]
xvalues1 = [y**2 for y in xvalues]
xvalues2 = [-y**2 for y in xvalues]

plt.plot(xvalues, yvalues1, label='Parabola 1 (x-axis)', color='red')
plt.plot(xvalues, yvalues2, label='Parabola 2 (x-axis)', color='blue')
plt.plot(xvalues1, xvalues, label='Parabola 3 (y-axis)', color='green')
plt.plot(xvalues2, xvalues, label='Parabola 4 (y-axis)', color='purple')

plt.legend(loc='center right')
plt.title('Four Parabolas Aligned with Axes')
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.grid()
plt.show()
```

## Proof of Work

![Captura de tela 2024-12-10 052453](https://github.com/user-attachments/assets/932eff8c-3b12-4cfe-95b6-9841f97ab76c)



