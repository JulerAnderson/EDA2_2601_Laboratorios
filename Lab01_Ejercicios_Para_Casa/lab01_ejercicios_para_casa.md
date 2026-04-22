# Laboratorio para Casa – Correctitud de Algoritmos y Análisis de Recurrencia

En esta guía trabajaremos los siguientes temas vistos en clase:

- **Contraejemplo**
- **Inducción matemática**
- **Invariante de bucle**
- **Teorema Maestro**

---

## Ejercicios de Contraejemplo

### Ejercicio 1: Verificar si todos los elementos son pares

Se propone el siguiente algoritmo:

```cpp
bool todosPares(int A[], int n) {
    for (int i = 0; i < n; i++) {
        if (A[i] % 2 == 0) return true;
    }
    return false;
}
```

#### Tarea

- Probar si el algoritmo es correcto.
- Si no lo es, encontrar un contraejemplo.

---

### Ejercicio 2: Verificar si un arreglo está ordenado de forma descendente

Se propone el siguiente algoritmo:

```cpp
bool estaOrdenadoDesc(int A[], int n) {
    for (int i = 1; i < n; i++) {
        if (A[i] <= A[i - 1]) return false;
    }
    return true;
}
```

#### Tarea

- Analizar si el algoritmo devuelve el resultado correcto.
- Si no lo hace, proporcionar un contraejemplo.

---

### Ejercicio 3: Verificar si un número es mayor que todos los elementos del arreglo

Se propone el siguiente algoritmo:

```cpp
bool esMayorQueTodos(int A[], int n, int x) {
    for (int i = 0; i < n; i++) {
        if (x > A[i]) return true;
    }
    return false;
}
```

#### Tarea

- Determinar si el algoritmo es correcto.
- Si no lo es, encontrar un contraejemplo.

---

## Pruebas de Correctitud de Algoritmos por Inducción Matemática

### Ejercicio 1: Suma de los primeros n múltiplos de 3

```cpp
int sumaMultiplos3(int n) {
    if (n == 1) return 3;
    return 3 * n + sumaMultiplos3(n - 1);
}
```

Demostrar por inducción matemática que:

$$
\sum_{i=1}^{n} 3i = \frac{3n(n+1)}{2}
$$

#### Estructura sugerida

- Definimos la función
- Caso base
- Hipótesis inductiva
- Paso inductivo

---

### Ejercicio 2: Suma de los primeros n números triangulares

```cpp
int sumaTriangulares(int n) {
    if (n == 1) return 1;
    return (n * (n + 1)) / 2 + sumaTriangulares(n - 1);
}
```

Demostrar por inducción matemática que:

$$
\sum_{i=1}^{n} \frac{i(i+1)}{2} = \frac{n(n+1)(n+2)}{6}
$$

#### Estructura sugerida

- Definimos la función
- Caso base
- Hipótesis inductiva
- Paso inductivo

---

### Ejercicio 3: Producto de números consecutivos dividido entre 2

```cpp
double productoMitades(int n) {
    if (n == 1) return 1.0;
    return ((n + 1.0) / n) * productoMitades(n - 1);
}
```

Demostrar por inducción matemática que:

$$
\prod_{i=1}^{n} \frac{i+1}{i} = n+1
$$

#### Estructura sugerida

- Definimos la función
- Caso base
- Hipótesis inductiva
- Paso inductivo

---

## Correctitud por Invariante de Bucle

### Ejercicio 1: Suma de elementos negativos de un arreglo

```cpp
int sumaNegativos(int A[], int n) {
    int suma = 0;
    for (int i = 0; i < n; i++) {
        if (A[i] < 0) suma += A[i];
    }
    return suma;
}
```

#### Objetivo

Identificar el invariante que representa la suma de los elementos negativos entre `A[0]` y `A[i - 1]`.

#### Estructura sugerida

- Invariante
- Inicialización
- Mantenimiento
- Terminación

---

### Ejercicio 2: Contador de números pares en un arreglo

```cpp
int contarPares(int A[], int n) {
    int contador = 0;
    for (int i = 0; i < n; i++) {
        if (A[i] % 2 == 0) contador++;
    }
    return contador;
}
```

#### Objetivo

Determinar el invariante que expresa la cantidad de números pares entre `A[0]` y `A[i - 1]`.

#### Estructura sugerida

- Invariante
- Inicialización
- Mantenimiento
- Terminación

---

### Ejercicio 3: Hallar el menor elemento de un arreglo

```cpp
int minimo(int A[], int n) {
    int menor = A[0];
    int i = 1;

    while (i < n) {
        if (A[i] < menor)
            menor = A[i];
        i++;
    }

    return menor;
}
```

#### Objetivo

Identificar el invariante que permite demostrar que `menor` contiene el menor valor entre los elementos ya revisados.

#### Estructura sugerida

- Invariante
- Inicialización
- Mantenimiento
- Terminación

---

## Teorema Maestro

Para cada recurrencia, determinar la complejidad temporal usando el **Teorema Maestro**.

### Ejercicio 1

$$
T(n) = 3T\left(\frac{n}{2}\right) + \Theta(n)
$$

#### Tarea

- Identificar los valores de $a$, $b$ y $d$.
- Comparar $a$ con $b^d$.
- Indicar qué caso del Teorema Maestro se aplica.
- Determinar la complejidad final.

---

### Ejercicio 2

$$
T(n) = 9T\left(\frac{n}{3}\right) + \Theta(n^2)
$$

#### Tarea

- Identificar los valores de $a$, $b$ y $d$.
- Comparar $a$ con $b^d$.
- Indicar qué caso del Teorema Maestro se aplica.
- Determinar la complejidad final.

---

### Ejercicio 3

$$
T(n) = 2T\left(\frac{n}{4}\right) + \Theta(n)
$$

#### Tarea

- Identificar los valores de $a$, $b$ y $d$.
- Comparar $a$ con $b^d$.
- Indicar qué caso del Teorema Maestro se aplica.
- Determinar la complejidad final.

---