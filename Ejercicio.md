## Ejercicio Anas Bellahcene El Morabet

### 1. ¿Qué sentido puede tener este proyecto y para que lo podrías usar?
> Es una calculadora simple de numeros enteros en java con un metodo para cada operación. Se podria usar en cualquier programa que necesite manipular numeros enteros. Por ejemplo en algun programa de gestión de inventario viene bien tener las funciones de operación de esta manera, ya que es buena práctica tener todos los métodos modularizados.

## 2. Revisa las pruebas de la suma y comenta lo que te parezca de interés
> Todas las pruebas son correctas, menos la de sumarPositivosMal() que da error (ya que el resultado esperado es distinto), haciendo que el test sea marcado como erroneo.

## 3. Realiza un estudio de caja negra de la división e implementa las pruebas en junit: Se realizará en markdown.
#### 1. Determinamos las clases de equivalencia:

##### Para el dividendo:
- Números enteros positivos (Mayores que 0)
- Números enteros negativos (Menores que 0)
- Número cero 

##### Para el divisor:
- Números enteros positivos (Mayores que 0)
- Números enteros negativos (Menores que 0)
- Clase invalida: Número cero, ya que no se puede dividir un número entre cero.

#### 2. Analizamos los valores límite:
- Para el dividendo el valor mas pequeño que se puede poner es la expresion Integer.MIN_VALUE (-2,147,483,648), ya que por memoria es el valor mas pequeño que se puede introducir. Mientras que el valor mas grande que se puede introducir es Integer.MAX_VALUE (2,147,483,647) ya que es el valor mas grande que se puede almacenar en la varible int.

- Para el divisor es exactamente lo mismo. Valor mas pequeño es Integer.MIN_VALUE (-2,147,483,648) y valor mas grande Integer.MAX_VALUE (2,147,483,647).

#### 3. Conjetura de errores.
##### Observamos que obtenemos 5 posibles errores en la división.
- Introducir en el dividendo un valor mas pequeño que -2,147,483,648. Por ejemplo -2,147,483,649.

- Introducir en el dividendo un valor mas grande que 2,147,483,647. Por ejemplo 2,147,483,648.

- Introducir en el divisor un valor mas pequeño que -2,147,483,648. Por ejemplo -2,147,483,649.  

- Introducir en el divisor un valor mas grande que 2,147,483,647. Por ejemplo 2,147,483,648.

- Introducir en el divisor el valor 0.

#### 4. Generar casos de prueba

| Caso de Prueba | Clase equivalencia | Límite (Condición) | Dividendo | Divisor | Salida Esperada |
| :--- | :--- | :--- | :--- | :--- | :--- |
| CP1 | División Válida | divisor > 0 | 10 | 2 | 5 |
| CP2 | | divisor < 0 | 10 | -2 | -5 |
| CP3 | | dividendo = 0, divisor != 0 | 0 | 5 | 0 |
| CP4 | | dividendo < 0, divisor < 0 | -10 | -2 | 5 |
| CP5 | | dividendo < 0, divisor > 0 | -10 | 2| -5 |
| CP6 | División No válida | divisor = 0 | 10 | 0 | ¡Error! |
| CP7 | Valores Límite | dividendo = MAX_VALUE | 2147483647 | 1 | 2147483647 |
| CP8 | | dividendo = MIN_VALUE | -2147483648 | 1 | -2147483648 |

No se han incluido valores fuera de los límites para el divisor ya que los resultados exceden el tamaño máximo de la variable (int) y Java no nos dejaría compilar la prueba.
