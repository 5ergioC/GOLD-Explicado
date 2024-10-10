# Más Ejemplos de Autómatas en Gold

Este repositorio contiene 4 nuevos ejemplos de autómatas en el lenguaje **Gold**. Estos ejemplos están en formato `.java` para facilidad de uso en un entorno de desarrollo como Eclipse. Para correr estos ejemplos, puedes copiar y pegar el código dentro de un proyecto Gold ya existente, como el que tiene Sergio en su repositorio con ejemplos documentados.

## Instrucciones de uso

1. Abre el proyecto de **Gold** en **Eclipse Kepler** (u otra versión de Eclipse) en el que ya tengas ejemplos documentados.
2. Corre los archivos .gold o si quieres copia y pega su codigo dentro de uno que tengas en tu proyecto si te da pereza importarlo en gold Kepler.
3. Ejecuta el código en Eclipse en el icono de correr programa de gold y observa los resultados gráficos del autómata.
<img width="280" alt="Screenshot 2024-10-10 at 4 16 35 PM" src="https://github.com/user-attachments/assets/6fb989d5-93b5-4c5f-9334-3b9e2aad9947">

## Estructura
Tenemos ejemplos para cada uno de los tipos de automatas vistos en el curso, encuentralos en sus respectivas carpetas. Aca mas abajo documentaremos cada uno.

## DFA

### Ejemplo 1: Autómata que alterna entre dos estados (q1 y q2)

Este autómata acepta cadenas sobre el alfabeto `{0, 1}`. Las transiciones permiten alternar entre dos estados según los valores leídos.

<img width="239" alt="Screenshot 2024-10-08 at 5 15 38 PM" src="https://github.com/user-attachments/assets/4946b323-4833-4c35-9b77-9bb10193c9ce">

// Ejemplos de cadenas aceptadas:
// "1": La cadena "1" lleva de q1 a q2.
// "10": La cadena "10" lleva de q1 a q2 y luego regresa a q1.
// "101": La cadena "101" alterna entre q1 y q2, terminando en q2.
// "1001": La cadena "1001" alterna y termina en q2 después de varios cambios.

// Ejemplos de cadenas rechazadas:
// "0": Se queda en q1 y nunca llega a q2.
// "11": La cadena "11" permanece en q2, pero nunca regresa a q1.
// "00": Se queda en q1, sin alcanzar nunca el estado q2.

### Ejemplo 2: Autómata con tres estados y transiciones alternadas
Este autómata trabaja con tres estados (q1, q2, y q3) y reconoce cadenas que alternan entre estos estados en función de las transiciones basadas en 0 y 1.

<img width="266" alt="Screenshot 2024-10-08 at 5 16 16 PM" src="https://github.com/user-attachments/assets/2528e8ff-b50c-45da-831b-9dc8d281832e">

Ejemplos de cadenas aceptadas:
- "1": La cadena "1" lleva de q1 a q2.
- "10": La cadena "10" lleva de q1 a q2 y luego a q3, pero regresa a q2.
- "101": La cadena "101" alterna entre q1 y q2, terminando en q2.
- "1001": La cadena "1001" alterna y termina en q2 después de varios cambios.

Ejemplos de cadenas rechazadas:
- "0": Se queda en q1 y nunca llega a q2.
- "11": La cadena "11" permanece en q2, pero nunca regresa a q1.
- "00": Se queda en q1, sin alcanzar nunca el estado q2.

### Ejemplo 3: Autómata que reconoce cadenas con cantidad impar de 'a's

Este autómata acepta cadenas sobre el alfabeto `{a, b}` que contienen una cantidad **impar** de 'a's. Las 'b's no afectan el conteo.

<img width="357" alt="Screenshot 2024-10-08 at 5 17 55 PM" src="https://github.com/user-attachments/assets/694bc372-dc56-4e30-aea0-875fd42618f2">

Ejemplos de cadenas aceptadas:
- "a": Una 'a' lleva de par a impar, lo que es aceptado.
- "ab": Una 'a' lleva a impar, las 'b' no afectan el estado.
- "aba": Las 'a's alternan el estado, terminando en impar.
- "bbabb": Solo la 'a' central afecta, llevando el estado a impar.
- "baaa": Tres 'a's llevan el estado a impar.

Ejemplos de cadenas rechazadas:
- "": No contiene ninguna 'a', por lo tanto es par.
- "b": Solo contiene 'b', por lo que es par.
- "aa": Dos 'a's llevan el estado de par a impar y luego de vuelta a par.
- "bbaa": Las dos 'a's hacen que el estado final sea par.
- "babbb": Solo hay una 'a', pero termina en par ya que la última transición deja el estado en par.

### Ejemplo 4: Autómata con múltiples estados

<img width="272" alt="Screenshot 2024-10-08 at 5 18 16 PM" src="https://github.com/user-attachments/assets/8912950f-880d-4d40-a4df-146b0d1c86d5">

Este autómata tiene cinco estados (`s`, `q1`, `q2`, `r1`, `r2`) y reconoce cadenas que alternan entre transiciones definidas por los caracteres 'a' y 'b'.

Ejemplos de cadenas aceptadas:
- "a": Lleva de s a q1, que es un estado final.
- "b": Lleva de s a r1, que es un estado final.
- "aa": Permanece en q1, un estado final.
- "bb": Permanece en r1, un estado final.
- "ababa": Alterna entre q1, q2, y r1, terminando en r1.
- "babab": Alterna entre r1, r2 y q1, terminando en q1.

Ejemplos de cadenas rechazadas:
- "aaab": Alterna entre q1 y q2 pero termina en un estado no final.
- "baab": Alterna entre r1 y r2 pero termina en un estado no final.
- "abbbba": Termina en un estado no final después de varias transiciones.

### Ejemplo 5: Autómata que solo reconoce la cadena vacia.
<img width="257" alt="Screenshot 2024-10-10 at 4 08 44 PM" src="https://github.com/user-attachments/assets/05a369bf-325d-4a48-874a-e52f08562dc8">

Aca se introduce un estado de error que seria el Q1 en el que si va ya no vuelve.

### Ejemplo 6: Autómata que reconoce una cadena limitada, solo una A y un B

<img width="339" alt="Screenshot 2024-10-10 at 4 08 20 PM" src="https://github.com/user-attachments/assets/df343808-0356-49d3-9993-5952157037f3">

Aca llamamos al estado de error T como abreviacion de trash.

### Ejemplo 7: Automata de cantidad de a's multiplo de 3 AAA

<img width="323" alt="Screenshot 2024-10-10 at 4 32 55 PM" src="https://github.com/user-attachments/assets/21a0f00d-cc23-45de-aa43-a61269bd7012">

Este autómata tiene tres estados (`q0`, `q1`, `q2`) y reconoce cadenas sobre el alfabeto `{a, b}` donde la cantidad de 'a's es un múltiplo de 3. Las 'b's no afectan el estado y pueden aparecer cualquier cantidad de veces.

Ejemplos de cadenas aceptadas:
- "b": No hay 'a's, por lo tanto es múltiplo de 3 (0 'a's).
- "aaab": Tres 'a's llevan de q0 a q1, luego a q2, y de regreso a q0.
- "bbbaa": Las 'b's no afectan, y la secuencia de 'a' termina en q0.
- "abababab": Alterna entre q0, q1, q2, y regresa a q0 después de cada 3 'a's.

Ejemplos de cadenas rechazadas:
- "a": Un solo 'a' lleva a q1, no es múltiplo de 3.
- "aa": Dos 'a's llevan a q2, no es múltiplo de 3.
- "aab": Dos 'a's llevan a q2, y 'b' no afecta, por lo tanto no es múltiplo de 3.
- "abb": Un 'a' lleva a q1, no es múltiplo de 3.

### Ejemplo 8: Automata que reconoce una b, dos a repetido muchas veces (baa)* 

<img width="467" alt="Screenshot 2024-10-10 at 4 36 04 PM" src="https://github.com/user-attachments/assets/192a790e-b3b5-473e-8b96-3fcf079cc0f7">

Este autómata tiene cuatro estados (`q0`, `q1`, `q2`, `t`) y reconoce cadenas sobre el alfabeto `{a, b}` que sigan el patrón `(baa)*`. Esto significa que la cadena debe consistir en cero o más repeticiones exactas del patrón 'baa'. Si la cadena contiene caracteres adicionales o no sigue el patrón, será rechazada.

Ejemplos de cadenas aceptadas:
- "": No hay ninguna cadena, lo que es aceptado porque (baa)* incluye cero repeticiones.
- "baa": Una repetición completa del patrón 'baa'.
- "baabaa": Dos repeticiones consecutivas del patrón 'baa'.
- "baabaabaa": Tres repeticiones del patrón 'baa'.

Ejemplos de cadenas rechazadas:
- "b": La cadena comienza correctamente, pero falta 'aa'.
- "aab": No sigue el patrón, y comienza con una 'a'.
- "ba": La cadena comienza correctamente, pero le falta una 'a' al final.
- "baab": Comienza correctamente, pero tiene un 'b' extra que rompe el patrón.


### Conclusión

Este conjunto de ejemplos proporciona más casos de autómatas finitos determinísticos (DFA) que pueden ser fácilmente integrados y ejecutados en proyectos Gold existentes dentro de Eclipse. Solo necesitas copiarlos en un proyecto ya abierto para extender el trabajo que ya tienes en curso.

