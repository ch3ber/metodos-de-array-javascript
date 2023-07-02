<p align="center">
  <a href="https://github.com/ch3ber" target="_blank"><img alt="Github" src="https://img.shields.io/badge/GitHub-%2312100E.svg?&style=for-the-badge&logo=Github&logoColor=white" /></a>
  <a href="https://www.linkedin.com/in/eberalejo/" target="_blank"><img alt="LinkedIn" src="https://img.shields.io/badge/linkedin-%230077B5.svg?&style=for-the-badge&logo=linkedin&logoColor=white" /></a>
  <a href="https://dev.to/ch3ber" target="_blank"><img alt="Dev" src="https://img.shields.io/badge/Dev-%2312100E.svg?&style=for-the-badge&logo=dev.to&logoColor=white" /></a>
</p>

# Conoce todos métodos de Array en JavaScript aprobados por el [TC39](https://tc39.es)

**Tabla de contenido**

- [Conoce todos métodos de Array en JavaScript aprobados por el TC39](#conoce-todos-métodos-de-array-en-javascript-aprobados-por-el-tc39)
  - [Definición](#definición)
  - [Sintaxis](#sintaxis)
  - [Métodos aprobados por el TC39](#métodos-aprobados-por-el-tc39)
- [Métodos](#métodos)
  - [Array.prototype.at()](#arrayprototypeat)
  - [Array.prototype.concat()](#arrayprototypeconcat)
  - [Array.prototype.copyWithin()](#arrayprototypecopywithin)
  - [Array.prototype.entries()](#arrayprototypeentries)
  - [Array.prototype.every()](#arrayprototypeevery)
  - [Array.prototype.filter()](#arrayprototypefilter)
  - [Array.prototype.find()](#arrayprototypefind)
  - [Array.prototype.findIndex()](#arrayprototypefindindex)
  - [Array.prototype.flat()](#arrayprototypeflat)
  - [Array.prototype.flatMap()](#arrayprototypeflatmap)
  - [Array.prototype.forEach()](#arrayprototypeforeach)
  - [Array.prototype.includes()](#arrayprototypeincludes)
  - [Array.prototype.indexOf()](#arrayprototypeindexof)

## Definición

**Array**: Arreglo en español, es estructura de datos en la cual a cada dato se le asigna un índice numerico y un valor (booleano, string, numeros, objectos, etc.), se accede al valor mediante el índice.

En JavaScript todos los arrays son dinámicos lo que quiere decir que pueden variar su longitud y el tipo de elementos que almacena en cualquier momento.

## Sintaxis

```js
const nombreArray = [valor, valor]

// ejemplo
const tamaños = ['pequeño', 'mediano', 'chico']
```

## Métodos aprobados por el TC39
En [este link](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-properties-of-the-array-prototype-object) podras encontrar todos los metodos de javascript aprobados por el grupo TC39

# Métodos

Facilitan el uso y la manipulación de los arrays. Permiten modificar y leer valores en los arrays.

## Array.prototype.at()

Retorna el elemento del índice que se recibe como argumento.

**Sintaxis**
```javascript
arrayNombre.at(indice)
```

**Ejemplo**
```javascript
const colores = ['rojo', 'azul', 'amarillo'];

console.log(colores.at(1)); // Retorna "azul"
console.log(colores.at(-1)); // Retorna "amarillo"
console.log(colores.at(5)); // Retorna undefined
```

**Notas**
- Si el índice es negativo, se contará desde el último elemento del array.
- Si el índice está fuera de los límites del array, se devuelve `undefined`.

## Array.prototype.concat()

Combina dos o más arrays y devuelve un nuevo array resultante de la concatenación.

**Sintaxis**
```javascript
array1.concat(array2, array3, ..., arrayN)
```

**Ejemplo**
```javascript
const frutas = ['manzana', 'banana'];
const vegetales = ['zanahoria', 'papa'];

const alimentos = frutas.concat(vegetales);

console.log(alimentos); // Retorna ['manzana', 'banana', 'zanahoria', 'papa']
```

**Notas**
- No modifica los arrays originales, sino que devuelve un nuevo array.
- Se pueden pasar múltiples arrays como argumentos para concatenarlos en el orden en que se proporcionan.

## Array.prototype.copyWithin()

Copia una porción de elementos dentro del array, sobrescribiendo los elementos existentes, sin cambiar la longitud del array.

**Sintaxis**
```javascript
arrayNombre.copyWithin(target, start, end)
```

**Ejemplo**
```javascript
const numeros = [1, 2, 3, 4, 5];

numeros.copyWithin(0, 3, 5);

console.log(numeros); // Retorna [4, 5, 3, 4, 5]
```

**Notas**
- Modifica el array original al copiar los elementos.
- `target` índice de destino donde se copiarán los elementos.
- `start` (opcional) índice de inicio desde donde se copiarán los elementos (por defecto es 0).
- `end` (opcional) índice de finalización hasta donde se copiarán los elementos (por defecto es la longitud del array).

## Array.prototype.entries()

Retorna un nuevo objeto Array Iterator que contiene pares clave/valor para cada índice en el array.

**Sintaxis**
```javascript
arrayNombre.entries()
```

**Ejemplo**
```javascript
const colores = ['rojo', 'azul', 'amarillo'];

const iterator = colores.entries();

console.log(iterator.next().value); // Retorna [0, 'rojo']
console.log(iterator.next().value); // Retorna [1, 'azul']
console.log(iterator.next().value); // Retorna [2, 'amarillo']
```

**Notas**
- Cada elemento del iterador es un array con dos elementos: el índice y el valor correspondiente.

## Array.prototype.every()

Verifica si todos los elementos en el array cumplen con una condición especificada.

**Sintaxis**
```javascript
arrayNombre.every(callback[(currentValue, index, array) => boolean][, thisArg])
```

**Ejemplo**
```javascript
const edades = [25, 30, 18, 20];

const mayoresDeEdad = edades.every((edad) => edad >= 18);

console.log(mayoresDeEdad); // Retorna true
```

**Notas**
- Ejecuta la función de callback una vez por cada elemento del array hasta que se encuentre un elemento que no cumpla la condición.
- Devuelve `true` si todos los elementos cumplen con la condición, de lo contrario, devuelve `false`.

## Array.prototype.filter()

Crea array con todos los elementos que cumplan una condición.

**Sintaxis**
```typescript
arrayNombre.filter(callback[(currentValue, index, array) => boolean][, thisArg])
```

**Ejemplo**
```javascript
const numeros = [1, 2, 3, 4, 5];

const numerosPares = numeros.filter((numero) => numero % 2 === 0);

console.log(numerosPares); // Retorna [2, 4]
```

**Notas**
- Ejecuta la función de callback una vez por cada elemento del array.
- Crea un nuevo array con los elementos que cumplan la condición del callback.
- No modifica el array original.

## Array.prototype.find()

Retorna el primer elemento del array que cumpla con una condición.

**Sintaxis**
```typescript
arrayNombre.find(callback[(element, index, array]) => boolean][, thisArg])
```

**Ejemplo**
```javascript
const frutas = ['manzana', 'banana', 'pera'];

const frutaEncontrada = frutas.find((fruta) => fruta === 'banana');

console.log(frutaEncontrada); // Retorna 'banana'
```

**Notas**
- Retorna `undefined` si no se encuentra ningun elemento que cumpla con la condición.

## Array.prototype.findIndex()

Retorna el índice del primer elemento del array que cumpla con una condición.

**Sintaxis**
```javascript
arrayNombre.findIndex(callback[(element, index, array) => boolean][thisArg])
```

**Ejemplo**
```javascript
const numeros = [10, 20, 30, 40, 50];

const indice = numeros.findIndex((numero) => numero > 30);

console.log(indice); // Retorna 3 porque 40 es mayor que 30
```

**Notas**
- Retorna -1 si no se encuentra ningun elemento que cumpla con la condición.

## Array.prototype.flat()

Crea un array que es una versión aplanada (flatten) del array original, un array con todos los elementos de los subarrays concatenados de manera recursiva hasta la profundidad especificada, elimina la anidación de arrays.

**Sintaxis**
```javascript
arrayNombre.flat([depth])
```

**Ejemplo**
```javascript
const numeros = [1, [2, [3, [4]]]];

const numerosAplanados = numeros.flat();

console.log(numerosAplanados); // Retorna [1, 2, [3, [4]]]
```

**Notas**
- Por defecto, `depth` es 1, lo que significa que solo se aplana un nivel. Se puede especificar un valor mayor para aplanar aún más.

## Array.prototype.flatMap()

Combina los pasos de `map()` y `flat()` en un solo método. Aplica una función a cada elemento y luego aplana el resultado un nivel.

**Sintaxis**
```javascript
arrayNombre.flatMap(callback[(currentValue, index, array) => any][, thisArg])
```

**Ejemplo**
```javascript
const numeros = [1, 2, 3];

const numerosDuplicados = numeros.flatMap((numero) => [numero, numero]);

console.log(numerosDuplicados); // Retorna [1, 1, 2, 2, 3, 3]
```

## Array.prototype.forEach()

Ejecuta un callback por cada elemento del array. No retorna ningún valor y no modifica el array original.

**Sintaxis**
```javascript
arrayNombre.forEach(callback[(currentValue, index, array) => void][, thisArg])
```

**Ejemplo**
```javascript
const frutas = ['manzana', 'banana', 'pera'];

frutas.forEach((fruta) => {
  console.log(fruta);
});

// Imprime:
// manzana
// banana
// pera
```

## Array.prototype.includes()

Determina si el array incluye un elemento, si se encuentra devuelve `true` de lo contrario devolverá `false`.

**Sintaxis**
```javascript
arrayNombre.includes(elemento, indiceInicio)
```

**Ejemplo**
```javascript
const numeros = [1, 2, 3, 4, 5];

console.log(numeros.includes(3)); // Retorna true
console.log(numeros.includes(6)); // Retorna false
```

## Array.prototype.indexOf()

Retorna el primer índice del elemento especificado o -1 si no se encuentra.

**Sintaxis**
```javascript
arrayNombre.indexOf(elemento, indiceInicio)
```

**Ejemplo**
```javascript
const colores = ['rojo', 'azul', 'amarillo'];

console.log(colores.indexOf('azul'));    // Retorna 1
console.log(colores.indexOf('verde'));   // Retorna -1
```
