# Soluciones - Correctitud de Algoritmos

En este documento se presentan las soluciones de los ejercicios de:

- **Contraejemplo**
- **Inducción matemática**

---

# Soluciones de Contraejemplo

## Ejercicio 1: Verificar si todos los elementos -son positivos

Algoritmo propuesto:

```cpp
bool todosPositivos(int A[], int n) {
    for (int i = 0; i < n; i++) {
        if (A[i] >= 0) return true;
    }
    return false;
}
```

### Solución

**Entrada:**  
`A = [5, -2, 3]`, `n = 3`

**Salida esperada:**  
`Falso`, porque **no todos** los elementos del arreglo son positivos.

**Salida del algoritmo:**  
`Verdadero`

**Explicación del error:**  
- El algoritmo devuelve `true` apenas encuentra **un solo elemento** mayor o igual que 0.
- En este caso, en la primera posición se tiene `A[0] = 5`, que cumple `A[i] >= 0`.
- Por ello, el algoritmo retorna `true` inmediatamente.
- Sin embargo, el arreglo también contiene `-2`, que no es positivo.
- Por lo tanto, el algoritmo **no verifica que todos los elementos sean positivos**, sino solo que exista al menos uno que no sea negativo.

---

## Ejercicio 2: Verificar si un número es múltiplo de 3

Algoritmo propuesto:

```cpp
bool esMultiploDe3(int n) {
    if (n % 2 == 0) return false;
    if (n % 3 == 0) return true;
    return false;
}
```

### Solución

**Entrada:**  
`n = 6`

**Salida esperada:**  
`Verdadero`, porque 6 es múltiplo de 3.

**Salida del algoritmo:**  
`Falso`

**Explicación del error:**  
- El algoritmo primero verifica si `n` es par.
- Como `6 % 2 == 0`, retorna `false` de inmediato.
- Sin embargo, ser par **no impide** que un número sea múltiplo de 3.
- De hecho, 6 sí es múltiplo de 3, porque:

$$
6 = 3 \cdot 2
$$

- Por lo tanto, el algoritmo falla al descartar automáticamente todos los números pares.

---

# Soluciones de Inducción Matemática

## Ejercicio 1: Suma de los primeros n números pares

Algoritmo:

```cpp
int sumaPares(int n) {
    if (n == 1) return 2;
    return 2 * n + sumaPares(n - 1);
}
```

Se desea demostrar que:

$$
\sum_{i=1}^{n} 2i = n(n+1)
$$

---

### 1) Definimos la función

Sea:

$$
f(n) = n(n+1)
$$

Queremos demostrar que, para todo $n \geq 1$:

$$
\text{sumaPares}(n) = f(n) = n(n+1)
$$

---

### 2) Caso base

Para $n = 1$:

$$
f(1) = 1(1+1) = 2
$$

Y además:

$$
\text{sumaPares}(1) = 2
$$

Entonces:

$$
\text{sumaPares}(1) = f(1)
$$

Por lo tanto, el caso base es verdadero.

---

### 3) Hipótesis inductiva

Suponemos que para algún $k \geq 1$ se cumple:

$$
f(k) = k(k+1)
$$

Es decir, suponemos que:

$$
2 + 4 + 6 + \cdots + 2k = k(k+1)
$$

---

### 4) Paso inductivo

Queremos demostrar que:

$$
f(k+1) = (k+1)(k+2)
$$

Es decir, queremos probar que:

$$
2 + 4 + 6 + \cdots + 2k + 2(k+1) = (k+1)(k+2)
$$

Partimos del lado izquierdo:

$$
2 + 4 + 6 + \cdots + 2k + 2(k+1)
$$

Agrupamos los primeros términos:

$$
= (2 + 4 + 6 + \cdots + 2k) + 2(k+1)
$$

Por hipótesis inductiva:

$$
= k(k+1) + 2(k+1)
$$

Factorizamos $(k+1)$:

$$
= (k+1)(k+2)
$$

Y eso es justamente lo que queríamos demostrar.

Por lo tanto, se cumple el paso inductivo.

---

### Conclusión

Como:

- el caso base es verdadero,
- la hipótesis inductiva se cumple,
- y el paso inductivo ha sido demostrado,

entonces, por inducción matemática:

$$
\text{sumaPares}(n) = n(n+1)
$$

para todo $n \geq 1$.

---

## Ejercicio 2: Suma de los primeros n cubos

Algoritmo:

```cpp
int sumaCubos(int n) {
    if (n == 1) return 1;
    return n * n * n + sumaCubos(n - 1);
}
```

Se desea demostrar que:

$$
\sum_{i=1}^{n} i^3 = \left(\frac{n(n+1)}{2}\right)^2
$$

---

### 1) Definimos la función

Sea:

$$
f(n) = \left(\frac{n(n+1)}{2}\right)^2
$$

Queremos demostrar que, para todo $n \geq 1$:

$$
\text{sumaCubos}(n) = f(n)
$$

---

### 2) Caso base

Para $n = 1$:

$$
f(1) = \left(\frac{1(1+1)}{2}\right)^2
= \left(\frac{2}{2}\right)^2
= 1
$$

Y además:

$$
\text{sumaCubos}(1) = 1
$$

Entonces:

$$
\text{sumaCubos}(1) = f(1)
$$

Por lo tanto, el caso base es verdadero.

---

### 3) Hipótesis inductiva

Suponemos que para algún $k \geq 1$ se cumple:

$$
f(k) = \left(\frac{k(k+1)}{2}\right)^2
$$

Es decir, suponemos que:

$$
1^3 + 2^3 + 3^3 + \cdots + k^3 = \left(\frac{k(k+1)}{2}\right)^2
$$

---

### 4) Paso inductivo

Queremos demostrar que:

$$
f(k+1) = \left(\frac{(k+1)(k+2)}{2}\right)^2
$$

Es decir, queremos probar que:

$$
1^3 + 2^3 + 3^3 + \cdots + k^3 + (k+1)^3
=
\left(\frac{(k+1)(k+2)}{2}\right)^2
$$

Partimos del lado izquierdo:

$$
1^3 + 2^3 + 3^3 + \cdots + k^3 + (k+1)^3
$$

Agrupamos los primeros términos:

$$
= (1^3 + 2^3 + 3^3 + \cdots + k^3) + (k+1)^3
$$

Por hipótesis inductiva:

$$
= \left(\frac{k(k+1)}{2}\right)^2 + (k+1)^3
$$

Factorizamos $(k+1)^2$:

$$
= (k+1)^2\left(\frac{k^2}{4} + (k+1)\right)
$$

Llevamos a un mismo denominador:

$$
= (k+1)^2\left(\frac{k^2 + 4k + 4}{4}\right)
$$

Reconocemos el cuadrado perfecto:

$$
= (k+1)^2\left(\frac{(k+2)^2}{4}\right)
$$

Entonces:

$$
= \frac{(k+1)^2 (k+2)^2}{4}
$$

$$
= \left(\frac{(k+1)(k+2)}{2}\right)^2
$$

Y eso es justamente lo que queríamos demostrar.

Por lo tanto, se cumple el paso inductivo.

---

### Conclusión

Como:

- el caso base es verdadero,
- la hipótesis inductiva se cumple,
- y el paso inductivo ha sido demostrado,

entonces, por inducción matemática:

$$
\text{sumaCubos}(n) = \left(\frac{n(n+1)}{2}\right)^2
$$

para todo $n \geq 1$.

---

# Soluciones de Invariante de Bucle

## Ejercicio 1: Suma de elementos positivos de un arreglo

Algoritmo:

```cpp
int sumaPositivos(int A[], int n) {
    int suma = 0;
    for (int i = 0; i < n; i++) {
        if (A[i] > 0) suma += A[i];
    }
    return suma;
}
```

### Solución

**Invariante:**  
Antes de cada iteración del bucle, la variable `suma` representa la suma de los elementos positivos entre `A[0]` y `A[i - 1]`.

---

**Inicialización:**  
Antes de la primera iteración, `i = 0` y `suma = 0`.  
En ese momento todavía no se ha revisado ningún elemento del arreglo, por lo que la suma de los elementos positivos entre `A[0]` y `A[i - 1]` es 0.  
Por lo tanto, el invariante se cumple al inicio.

---

**Mantenimiento:**  
Supongamos que al inicio de una iteración el invariante es verdadero, es decir, `suma` contiene correctamente la suma de los elementos positivos entre `A[0]` y `A[i - 1]`.

Ahora se analiza el elemento `A[i]`:

- Si `A[i] > 0`, entonces se ejecuta `suma += A[i]`.  
  En ese caso, `suma` pasa a representar la suma de los elementos positivos entre `A[0]` y `A[i]`.

- Si `A[i] <= 0`, entonces `suma` no cambia.  
  En ese caso, `suma` sigue representando correctamente la suma de los elementos positivos entre `A[0]` y `A[i]`.

En ambos casos, al finalizar la iteración e incrementarse `i`, el invariante vuelve a cumplirse para la siguiente iteración.

---

**Terminación:**  
El bucle termina cuando `i = n`.  
En ese momento, por el invariante, `suma` representa la suma de los elementos positivos entre `A[0]` y `A[n - 1]`, es decir, en todo el arreglo.  
Como el algoritmo retorna `suma`, devuelve el resultado correcto.

---

**Conclusión:**  
El algoritmo es correcto por invariante de bucle.

---

## Ejercicio 2: Contador de elementos mayores que x

Algoritmo:

```cpp
int contarMayores(int A[], int n, int x) {
    int contador = 0;
    for (int i = 0; i < n; i++) {
        if (A[i] > x) contador++;
    }
    return contador;
}
```

### Solución

**Invariante:**  
Antes de cada iteración del bucle, la variable `contador` representa la cantidad de elementos mayores que `x` entre `A[0]` y `A[i - 1]`.

---

**Inicialización:**  
Antes de la primera iteración, `i = 0` y `contador = 0`.  
En ese momento todavía no se ha revisado ningún elemento del arreglo, por lo que la cantidad de elementos mayores que `x` entre `A[0]` y `A[i - 1]` es 0.  
Por lo tanto, el invariante se cumple al inicio.

---

**Mantenimiento:**  
Supongamos que al inicio de una iteración el invariante es verdadero, es decir, `contador` contiene correctamente la cantidad de elementos mayores que `x` entre `A[0]` y `A[i - 1]`.

Ahora se analiza el elemento `A[i]`:

- Si `A[i] > x`, entonces se ejecuta `contador++`.  
  En ese caso, `contador` pasa a representar la cantidad de elementos mayores que `x` entre `A[0]` y `A[i]`.

- Si `A[i] <= x`, entonces `contador` no cambia.  
  En ese caso, `contador` sigue representando correctamente la cantidad de elementos mayores que `x` entre `A[0]` y `A[i]`.

En ambos casos, al finalizar la iteración e incrementarse `i`, el invariante vuelve a cumplirse para la siguiente iteración.

---

**Terminación:**  
El bucle termina cuando `i = n`.  
En ese momento, por el invariante, `contador` representa la cantidad de elementos mayores que `x` entre `A[0]` y `A[n - 1]`, es decir, en todo el arreglo.  
Como el algoritmo retorna `contador`, devuelve el resultado correcto.

---

**Conclusión:**  
El algoritmo es correcto por invariante de bucle.

---