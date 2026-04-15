# Correctitud de Algoritmos

En esta guía trabajaremos dos técnicas de prueba de correctitud:

- **Contraejemplo**
- **Inducción matemática**

---

## Ejercicios de Contraejemplo

### Ejercicio 1: Verificar si todos los elementos son positivos

Se propone el siguiente algoritmo:

```cpp
bool todosPositivos(int A[], int n) {
    for (int i = 0; i < n; i++) {
        if (A[i] >= 0) return true;
    }
    return false;
}
```

#### Tarea

- Probar si el algoritmo es correcto.
- Si no lo es, encontrar un contraejemplo.

---

### Ejercicio 2: Verificar si un número es múltiplo de 3

Se propone el siguiente algoritmo:

```cpp
bool esMultiploDe3(int n) {
    if (n % 2 == 0) return false;
    if (n % 3 == 0) return true;
    return false;
}
```

#### Tarea

- Analizar si el algoritmo devuelve el resultado correcto.
- Si no lo hace, proporcionar un contraejemplo.

---

## Pruebas de Correctitud de Algoritmos por Inducción Matemática

### Ejercicio 1: Suma de los primeros n números pares

```cpp
int sumaPares(int n) {
    if (n == 1) return 2;
    return 2 * n + sumaPares(n - 1);
}
```

Demostrar por inducción matemática que:

$$
\sum_{i=1}^{n} 2i = n(n+1)
$$

#### Estructura sugerida

- Proposición
- Caso base
- Hipótesis inductiva
- Lo que debemos probar
- Por definición de la función
- Demostración paso a paso

---

### Ejercicio 2: Suma de los primeros n cubos

```cpp
int sumaCubos(int n) {
    if (n == 1) return 1;
    return n * n * n + sumaCubos(n - 1);
}
```

Demostrar por inducción matemática que:

$$
\sum_{i=1}^{n} i^3 = \left(\frac{n(n+1)}{2}\right)^2
$$

#### Estructura sugerida

- Proposición
- Caso base
- Hipótesis inductiva
- Lo que debemos probar
- Por definición de la función
- Demostración paso a paso