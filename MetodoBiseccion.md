# Tarea 4 — Método de la Bisección

## Nombre: Ariel Burgos
---

---

##  EJERCICIO 1

Use el método de bisección para encontrar soluciones con precisión \(10^{-2}\) para


\[
f(x)=x^3-7x^2+14x-6=0
\]


en los intervalos **(a)** \([0,1]\), **(b)** \([1,3.2]\), **(c)** \([3.2,4]\).

**Observación previa (factorización y raíces exactas).**
El polinomio tiene tres raíces reales:


\[
x_1=2-\sqrt{2}\approx 0.585786,\quad x_2=3,\quad x_3=2+\sqrt{2}\approx 3.414214.
\]


Cada intervalo contiene una de esas raíces.

**Criterio de parada.** Se aplica bisección hasta que el ancho del intervalo sea menor que \(0.01\).

**Resultados (redondeados a 2 decimales):**

- **(a) \([0,1]\)** → **\(x\approx 0.59\)**.
  (Raíz exacta \(2-\sqrt2\approx0.585786\); error \(<0.01\).)

- **(b) \([1,3.2]\)** → **\(x\approx 3.00\)**.
  (Raíz exacta \(x=3\); error \(<0.01\).)

- **(c) \([3.2,4]\)** → **\(x\approx 3.41\)**.
  (Raíz exacta \(2+\sqrt2\approx3.414214\); error \(<0.01\).)

---

###  Ejercicio 2

Dibuje \(y=x\) y \(y=\sin x\). Use el método de bisección para encontrar, con precisión \(10^{-5}\), el primer valor positivo de \(x\) que satisface \(x=2\sin x\).

 Definir


\[
g(x)=x-2\sin x.
\]


Buscamos la primera raíz positiva distinta de 0. Observamos:
- \(g(1)=1-2\sin1\approx -0.68294 < 0\).
- \(g(2)=2-2\sin2\approx 0.1814 > 0\).

Por tanto existe una raíz en \([1,2]\). Aplicando bisección hasta ancho \(<10^{-5}\):

**Resultado (5 decimales):**


\[
\boxed{x\approx 1.89549}
\]



---

###  Ejercicio 3

Dibuje \(y=x\) y \(y=\tan x\). Use bisección para encontrar, con precisión \(10^{-5}\), el primer valor positivo de \(x\) que satisface \(x=\tan x\).

 Definir


\[
h(x)=x-\tan x.
\]


La primera intersección positiva no trivial ocurre después de la primera asíntota de \(\tan x\). Localizando el intervalo adecuado (por ejemplo \([4.4,4.6]\)) y aplicando bisección hasta \(10^{-5}\):

**Resultado (5 decimales):**


\[
\boxed{x\approx 4.49341}
\]



---

### Ejercicio 4

**Enunciado.** Dibuje \(y=x^2-1\) y \(y=e^{1-x^2}\). Use bisección para encontrar una aproximación dentro de \(10^{-3}\) para una solución en \([-2,0]\).

**Planteamiento.** Definir


\[
p(x)=x^2-1 - e^{1-x^2}.
\]


Evaluaciones:
- \(p(-2)=3 - e^{-3}\approx 2.950213 > 0\).
- \(p(0)=-1 - e^{1}\approx -3.71828 < 0\).

Existe al menos una raíz en \([-2,0]\). Aplicando bisección hasta ancho \(<10^{-3}\):

**Resultado (3 decimales):**


\[
\boxed{x\approx -1.252}
\]



---

### Ejercicio 5

**Enunciado.** Sea


\[
f(x)=(x+3)(x+1)^2 x (x-1)^3 (x-3).
\]


¿A qué cero converge la bisección en los intervalos:
a) \([-1.5,2.5]\), b) \([-0.5,2.4]\), c) \([-0.5,3]\), d) \([-3,-0.5]\)?

**Análisis.** Raíces y multiplicidades:
- \(x=-3\) (simple)
- \(x=-1\) (multiplicidad 2)
- \(x=0\) (simple)
- \(x=1\) (multiplicidad 3)
- \(x=3\) (simple)

La bisección requiere \(f(a)\cdot f(b)<0\) para garantizar convergencia a una raíz interior. Si \(f(a)f(b)>0\), no se puede aplicar directamente.

**Conclusiones por intervalo:**

- **(a) \([-1.5,2.5]\)**: \(f(-1.5)\) y \(f(2.5)\) tienen el mismo signo → **bisección estándar no se aplica** sin elegir subintervalo con cambio de signo.
- **(b) \([-0.5,2.4]\)**: extremos con mismo signo → **bisección estándar no se aplica**.
- **(c) \([-0.5,3]\)**: \(f(3)=0\) → extremo derecho es raíz; si se acepta extremo, la raíz es **\(x=3\)**.
- **(d) \([-3,-0.5]\)**: \(f(-3)=0\) → extremo izquierdo es raíz; la raíz es **\(x=-3\)**.

---

## 2. Ejercicios aplicados

### 2.1 Abrevadero — hallar \(h\) con \(L=10,\ r=1,\ V=12.4\) (precisión \(0.01\) cm)

Para un abrevadero con sección semicircular de radio \(r\) y longitud \(L\), el volumen cuando el agua llega a distancia \(h\) desde la parte superior es:


\[
V = L\Big[0.5\pi r^2 - r^2\arcsin\!\big(\tfrac{h}{r}\big) - h\sqrt{r^2-h^2}\Big].
\]


Con \(L=10\), \(r=1\), \(V=12.4\), encontrar \(h\) con precisión \(0.01\) cm.

**Planteamiento.** Con \(r=1,\ L=10\):


\[
\frac{V}{10}=0.5\pi - \arcsin(h) - h\sqrt{1-h^2}.
\]


Definir


\[
F(h)=0.5\pi - \arcsin(h) - h\sqrt{1-h^2} - \frac{V}{10}.
\]


Sustituyendo \(V/10=1.24\) y \(0.5\pi\approx1.5707963\):


\[
F(h)\approx 0.3307963 - \arcsin(h) - h\sqrt{1-h^2}.
\]


Dominio físico: \(h\in[0,1]\).

**Bisección (resumen).**
- \(F(0)>0\), \(F(0.5)<0\) → raíz en \([0,0.5]\).
- Refinando por bisección hasta ancho \(<0.01\).

**Resultado (2 decimales):**


\[
\boxed{h\approx 0.17\ \text{cm}}
\]



---

### EJERCICIO 2

Un objeto que cae verticalmente a través del aire está sujeto a una resistencia viscosa, así como a la fuerza
de gravedad. Suponga que un objeto con masa 𝑚 cae desde una altura 𝑠଴ y que la altura del objeto después
de 𝑡 segundos es



\[
s(t)=s_0 - \frac{mg}{k}t + \frac{m^2 g}{k^2}\big(1-e^{-kt/m}\big).
\]


Con \(g=9.81\ \text{m/s}^2\), \(s_0=300\ \text{m}\), \(m=0.25\ \text{kg}\), \(k=0.1\ \text{N·s/m}\). Encontrar \(t\) tal que \(s(t)=0\) con precisión \(0.01\) s.

**Planteamiento.** Definir


\[
S(t)=s_0 - \frac{mg}{k}t + \frac{m^2 g}{k^2}\big(1-e^{-kt/m}\big).
\]


Buscar \(t>0\) con \(S(t)=0\). Evaluaciones iniciales muestran un cambio de signo en un intervalo razonable (por ejemplo entre 50 s y 200 s). Aplicar bisección hasta ancho \(<0.01\) s.

**Resultado (2 decimales):**


\[
\boxed{t\approx 78.45\ \text{s}}
\]



---

## 3. Ejercicios teóricos

### 1
Use el teorema 2.1 para encontrar una cota para el número de iteraciones necesarias para lograr una
aproximación con precisión de \(10^{-3}\) para la solución de 𝑥3 − 𝑥 − 1 = 0 que se encuentra dentro del intervalo
[1, 2]. Encuentre una aproximación para la raíz con este grado de precisión.


**Cota.** Tras \(n\) iteraciones el ancho es \(\dfrac{b-a}{2^n}\). Se requiere


\[
\frac{b-a}{2^n}\le \varepsilon \quad\Rightarrow\quad n\ge \log_2\!\Big(\frac{b-a}{\varepsilon}\Big).
\]


Con \(b-a=1\) y \(\varepsilon=10^{-4}\):


\[
n\ge \log_2(10^4)\approx 13.2877 \Rightarrow n=14\ \text{iteraciones}.
\]



**Aproximación (tras 14 iteraciones):**


\[
\boxed{x\approx 1.32472}\quad(\text{precisión }10^{-4}).
\]



---

### 2

 La función \(f(x)=\sin(\pi x)\) tiene ceros en cada entero. Muestre cuando \(-1<a<0\) y \(2<b<3\), el método de bisección aplicado a \([a,b]\) converge a:
- \(0\) si \(a+b<2\),
- \(2\) si \(a+b>2\),
- \(1\) si \(a+b=2\).


- \(f\) es continua y cambia de signo entre enteros consecutivos.
- La bisección divide el intervalo y selecciona la mitad que contiene el cambio de signo; la suma \(a+b\) determina si la media inicial está a la izquierda o derecha de 1, lo que conduce, tras suficientes divisiones, a aislar el entero correspondiente (0, 1 o 2) según el caso.

---


