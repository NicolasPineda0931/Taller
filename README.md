# Taller
taller
mport numpy as np
import matplotlib.pyplot as plt

# Parámetros del grupo (ajustar según corresponda)
frecuencia_portadora = 50  # Frecuencia de la portadora en Hz
frecuencia_informacion = 5  # Frecuencia de la señal de información en Hz
duracion = 1  # Duración total de la simulación en segundos
amplitud_portadora = 1
amplitud_informacion = 0.5

# Vector de tiempo
t = np.linspace(0, duracion, 1000)

# Señal portadora
portadora = amplitud_portadora * np.cos(2 * np.pi * frecuencia_portadora * t)

# Señal de información
informacion = amplitud_informacion * np.sin(2 * np.pi * frecuencia_informacion * t)

# Señal modulada AM
modulada = (1 + informacion) * portadora

# Visualización de las señales
plt.figure(figsize=(12, 8))

# Señal portadora
plt.subplot(3, 1, 1)
plt.plot(t, portadora, label='Señal Portadora')
plt.title('Señal Portadora')
plt.xlabel('Tiempo [s]')
plt.ylabel('Amplitud')
plt.legend()
plt.grid()

# Señal de información
plt.subplot(3, 1, 2)
plt.plot(t, informacion, label='Señal de Información', color='r')
plt.title('Señal de Información')
plt.xlabel('Tiempo [s]')
plt.ylabel('Amplitud')
plt.legend()
plt.grid()

# Señal modulada AM
plt.subplot(3, 1, 3)
plt.plot(t, modulada, label='Señal Modulada AM', color='g')
plt.title('Señal Modulada AM')
plt.xlabel('Tiempo [s]')
plt.ylabel('Amplitud')
plt.legend()
plt.grid()

# Mostrar gráficos
plt.tight_layout()
