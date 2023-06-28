# Conoce todos métodos de Array en JavaScript aprobados por el [TC39](https://tc39.es)

<p align="center">
  <a href="https://github.com/ch3ber" target="_blank"><img alt="Github" src="https://img.shields.io/badge/GitHub-%2312100E.svg?&style=for-the-badge&logo=Github&logoColor=white" /></a>
  <a href="https://www.linkedin.com/in/eberalejo/" target="_blank"><img alt="LinkedIn" src="https://img.shields.io/badge/linkedin-%230077B5.svg?&style=for-the-badge&logo=linkedin&logoColor=white" /></a>
  <a href="https://dev.to/ch3ber" target="_blank"><img alt="Dev" src="https://img.shields.io/badge/Dev-%2312100E.svg?&style=for-the-badge&logo=dev.to&logoColor=white" /></a>
</p>

**Array**: estructura de datos en la cual a cada dato se le asigna un índice numerico y un valor (booleano, string, numeros, objectos, etc.), se accede al valor mediante el índice.

## Sintaxis

`const colores = ['rojo', 'azul', 'amarillo']`

En JavaScript todos los arrays son dinámicos lo que quiere decir que pueden variar su longitud y el tipo de elementos que almacena en cualquier momento.

# Array.prototype.at()

Retorna el elemento del índice que recibe como argumento. [Ver ejemplo en código.](./ejemplos/at.js)

![Ilustración en código del método](img/at.svg)

| Parámetros | Tipo   | Descripción                    |
| ---------- | ------ | ------------------------------ |
| índice     | number | Índice del elemento a retornar |

-  si el índice es negativo se contará desde el último elemento del array.

-  si el índice esta fuera de los límites se devuelve `undefined`.
