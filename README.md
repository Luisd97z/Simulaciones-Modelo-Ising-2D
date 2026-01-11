# Simulaciones-Modelo-Ising-2D
Se simulan redes de Ising 2D hexagonales y cuadradas de varios tamaños. En ambos casos se calculan los observables termodinámicos (energía, magnetización, calor específico) y determinación numérica de la temperatura crítica.
En el presente repositorio se encuentra la implementación y el análisis numérico del **Modelo de Ising** en 2D aplicada a redes **cuadradas** Y **hexagonales** de tamaños variables. Dicho proyecto fue desarrollado como parte de la formación acádemica en la Facultad de Ciencias Exactas y Naturales (UBA).

### Resumen:

El objetivo es estudiar las transiciones de fase ferromagnéticas, el comportamiento crítico del sistema y comparar los resultados obtenidos con los resultados teóricos de Onsager.Para ello se implementó el **Algoritmo de metrópolis** para simular la dinámica de espines y calcular los observables termodinámicos fundamentales.

### Características principales:
* **Geometrías:** Soporte para red cuadrada y red hexagonal (este último utilizando geometría "Brick wall")}
* **Optimización:** Uso de **Numba (`@njit`)** para compilación *Just-In-Time*, permitiendo simulaciones de gran escala en tiempos de ejecución competitivos.
* **Análisis Crítico:** Cálculo de la temperatura de Curie ($T_c$) mediante la búsqueda de picos en la susceptibilidad magnética y el calor específico, mediante ajustes lineales.

### Física y Observables

La energía del sistema está dada por el Hamiltoniano:

$$H = -J \sum_{\langle i,j \rangle} s_i s_j$$

Donde $J$ es la constante de intercambio (asumida $J=1$ para ferromagnetismo). El código permite calcular y graficar:
* **Energía Media** $\langle E \rangle$
* **Magnetización Media** $\langle |M| \rangle$
* **Calor Específico** $C_v$
* **Susceptibilidad Magnética** $\chi$

### Requisitos e Instalación:

Para ejecutar las simulaciones, necesitás Python 3.x y las siguientes librerías:

```bash
pip install numpy pandas matplotlib scipy numba scikit-learn tqdm
```
### Resultados:
* Redes cuadradas: Simulación de la red cuadrada de tamaños $L**2$, se obtuvieron los resultados vistos en la siguiente imagen
<img width="1164" height="972" alt="image" src="https://github.com/user-attachments/assets/96456e92-2ce7-40be-899a-c99c0e93ee34" />

Se observan los gráficos de susceptibilidad, energía, magnetización y calor específico de redes cuadradas de tamaños L= 16, 32 y 64. En el mismo se observa la temperatura crítica entorno a $T \approx 2.3$. También se observan los efectos del **Finite Size Scaling** denotado en el comportamiento de las curvas dependiendo del valor de $L$.

En la siguiente imagen se comparan las curvas teóricas de Onsager respectos de los datos obtenidos en las simulaciones
<img width="1335" height="956" alt="image" src="https://github.com/user-attachments/assets/0f82cb9a-8d58-46f8-bbd4-ce2fa39e3614" />

Al utilizar un ajuste con la fórmula $ax**2 + bx + c$, como se observa en la siguiente imágen: 

<img width="889" height="590" alt="image" src="https://github.com/user-attachments/assets/f9e85f45-24a0-4fe5-a86f-dd854404ad3f" />

Se obtiene una temperatura crítica $T_c = 2.2710 \pm 0.0031$, valor que presenta un error relativo del $0.08%$ respecto del valor de Onsager $T_{Onsager} = 2.2692 $

* Redes hexagonales: Análogamente, para las redes hexagonales se obtuvieron los gráficos de energía, capacidad calorífica, magneticación y susceptibilidad en transiciones de fase:
<img width="1189" height="495" alt="image" src="https://github.com/user-attachments/assets/23a42f9d-3649-43aa-9802-02721845d100" />
<img width="1189" height="495" alt="image" src="https://github.com/user-attachments/assets/49daa911-f972-4945-9b1e-ed8ff55f5a67" />

En la siguiente imágen se observa la comparación respecto de las curvas de Onsager:
<img width="1389" height="593" alt="image" src="https://github.com/user-attachments/assets/186c8a44-71f9-4dc3-8dfa-81893f209496" />

Con el ajuste, utilizando la ecuación ($ax + b$) se obtuvo una temperatura crítica $T_c = 1.5211 \pm 0.0013$ tal como se observa en la siguiente imágen

<img width="889" height="590" alt="image" src="https://github.com/user-attachments/assets/0b647c6f-5764-42f4-b9c9-e7ee6695de17" />

con un error relativo del $0.14%$ respecto del valor teórico de Onsager $T_{Onsager} = 1.51866$.

### Autores:

* Luis Diaz - Estudiante de Licenciatura en Ciencias Físicas, UBA
* Sergio Stedile - Estudiante de Licenciatura en Ciencias Físicas, UBA
* Julieta Perez Lanzillotta - Estudiante de Licenciatura en Ciencias Físicas, UBA
