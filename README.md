import numpy as np
import matplotlib.pyplot as plt

# Definir la matriz M
M = np.array([[1, 2], [2, 4]])

# Definir una función para la ecuación de la elipse
def ellipse(x, y):
    return x * M[0, 0] * x + (M[0, 1] + M[1, 0]) * x * y + M[1, 1] * y * y

# Definir los límites del eje x e y
x_lim = (-2, 2)
y_lim = (-2, 2)

# Crear un arreglo de puntos
x_vals = np.linspace(x_lim[0], x_lim[1], 100)
y_vals = np.linspace(y_lim[0], y_lim[1], 100)
x, y = np.meshgrid(x_vals, y_vals)

# Evaluar la función de la elipse en los puntos
z = ellipse(x, y)

# Graficar la elipse
plt.contour(x, y, z, levels=[1], colors='black')
plt.xlabel('x')
plt.ylabel('y')
plt.xlim(x_lim)
plt.ylim(y_lim)
plt.gca().set_aspect('equal')
plt.show()
