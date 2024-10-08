# Más Ejemplos de Autómatas en Gold

Este repositorio contiene 4 nuevos ejemplos de autómatas en el lenguaje **Gold**. Estos ejemplos están en formato `.java` para facilidad de uso en un entorno de desarrollo como Eclipse. Para correr estos ejemplos, puedes copiar y pegar el código dentro de un proyecto Gold ya existente, como el que tiene Sergio en su repositorio con ejemplos documentados.

## Instrucciones de uso

1. Abre el proyecto de **Gold** en **Eclipse Kepler** (u otra versión de Eclipse) en el que ya tengas ejemplos documentados.
2. Crea una nueva clase Java en tu proyecto existente.
3. Copia y pega el código de los ejemplos provistos en este archivo dentro de la nueva clase Java.
4. Ejecuta el código en Eclipse y observa los resultados gráficos del autómata.

### Ejemplo 1: Autómata que alterna entre dos estados (q1 y q2)

Este autómata acepta cadenas sobre el alfabeto `{0, 1}`. Las transiciones permiten alternar entre dos estados según los valores leídos.

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

### Conclusión

Este conjunto de ejemplos proporciona más casos de autómatas finitos determinísticos (DFA) que pueden ser fácilmente integrados y ejecutados en proyectos Gold existentes dentro de Eclipse. Solo necesitas copiarlos en un proyecto ya abierto para extender el trabajo que ya tienes en curso.

