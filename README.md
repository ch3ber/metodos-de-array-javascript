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
  - [Array.prototype.fill()](#arrayprototypefill)
  - [Array.prototype.filter()](#arrayprototypefilter)
  - [Array.prototype.find()](#arrayprototypefind)
  - [Array.prototype.findIndex()](#arrayprototypefindindex)
  - [Array.prototype.findLast()](#arrayprototypefindlast)
  - [Array.prototype.findLastIndex()](#arrayprototypefindlastindex)
  - [Array.prototype.flat()](#arrayprototypeflat)
  - [Array.prototype.flatMap()](#arrayprototypeflatmap)
  - [Array.prototype.forEach()](#arrayprototypeforeach)
  - [Array.from()](#arrayfrom)
  - [Array.prototype.includes()](#arrayprototypeincludes)
  - [Array.prototype.indexOf()](#arrayprototypeindexof)
  - [Array.prototype.join()](#arrayprototypejoin)
  - [Array.prototype.keys()](#arrayprototypekeys)
  - [Array.prototype.lastIndexOf()](#arrayprototypelastindexof)
  - [Array.prototype.map()](#arrayprototypemap)
  - [Array.prototype.pop()](#arrayprototypepop)
  - [Array.prototype.push()](#arrayprototypepush)
  - [Array.prototype.reduce()](#arrayprototypereduce)
  - [Array.prototype.reduceRight()](#arrayprototypereduceright)
  - [Array.prototype.reverse()](#arrayprototypereverse)
  - [Array.prototype.shift()](#arrayprototypeshift)
  - [Array.prototype.slice()](#arrayprototypeslice)
  - [Array.prototype.some()](#arrayprototypesome)
  - [Array.prototype.sort()](#arrayprototypesort)
  - [Array.prototype.splice()](#arrayprototypesplice)
  - [Array.prototype.toLocaleString()](#arrayprototypetolocalestring)
  - [Array.prototype.toReversed()](#arrayprototypetoreversed)
  - [Array.prototype.toSorted()](#arrayprototypetosorted)
  - [Array.prototype.toSpliced()](#arrayprototypetospliced)
  - [Array.prototype.toString()](#arrayprototypetostring)
  - [Array.prototype.unshift()](#arrayprototypeunshift)
  - [Array.prototype.values()](#arrayprototypevalues)
  - [Array.prototype.with()](#arrayprototypewith)

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
```typescript
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
```typescript
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
```typescript
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
```typescript
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
- Puede ser utilizado en un bucle `for...of` para iterar sobre los valores del array.

## Array.prototype.every()

Verifica si todos los elementos en el array cumplen con una condición especificada.

**Sintaxis**
```typescript
arrayNombre.every(function callback(currentValue, index, array): boolean {
  // condición para retornar
}, [, thisArg])
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

## Array.prototype.fill()

Rellena todos los elementos del array con un solo valor, desde un índice de inicio hasta un índice de fin.

**Sintaxis**
```javascript
arrayNombre.fill(valor, indiceInicio, indiceFin)
```

**Ejemplo**
```javascript
const numeros = [1, 2, 3, 4, 5];

numeros.fill(0, 2, 4);

console.log(numeros); // Retorna [1, 2, 0, 0, 5]
```

**Notas**
- Si no se especifica el índice de inicio, se utiliza 0 como valor por defecto.
- Si no se especifica el índice de fin, se utiliza la longitud del array como valor por defecto.

## Array.prototype.filter()

Crea array con todos los elementos que cumplan una condición.

**Sintaxis**
```typescript
arrayNombre.filter(function callback(currentValue, index, array): boolean {
  // retornar condición para filtrar
}, [, thisArg])
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
arrayNombre.find(function callback(element, index, array): boolean {
  // retornar condición para encontrar elemento
}, [, thisArg])
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
```typescript
arrayNombre.findIndex(function callback(element, index, array): boolean {
  // retornar condición para encontrar elemento
}, [thisArg])
```

**Ejemplo**
```javascript
const numeros = [10, 20, 30, 40, 50];

const indice = numeros.findIndex((numero) => numero > 30);

console.log(indice); // Retorna 3 porque 40 es mayor que 30
```

**Notas**
- Retorna -1 si no se encuentra ningun elemento que cumpla con la condición.

## Array.prototype.findLast()

Retorna el último elemento del array que cumpla con la condición escrita en la función de prueba.

**Sintaxis**
```typescript
arrayNombre.findLast(function funcionPrueba (element, index, array): boolean {
  // devuelve un valor verdadero para indicar que se ha encontrado un elemento coincidente y un valor falso en caso contrario.
},[, thisArg])
```

**Ejemplo**
```javascript
const numeros = [1, 2, 3, 4, 5];

const ultimoPar = numeros.findLast((numero) => numero % 2 === 0);

console.log(ultimoPar); // Retorna 4
```

**Notas**
- Retorna `undefined` si ningún elemento cumple con la condición.

## Array.prototype.findLastIndex()

Retorna el índice del último elemento del array que cumpla con la condición escrita en la función de prueba.

**Sintaxis**
```javascript
arrayNombre.findLastIndex(function funcionPrueba (element, index, array): boolean {
  // devuelve un valor verdadero para indicar que se ha encontrado un elemento coincidente y un valor falso en caso contrario.
},[, thisArg])
```

**Ejemplo**
```javascript
const numeros = [1, 2, 3, 4, 5];

const ultimoIndicePar = numeros.findLastIndex((numero) => numero % 2 === 0);

console.log(ultimoIndicePar); // Retorna 3
```

**Notas**
- Retorna -1 si ningún elemento cumple con la condición.

## Array.prototype.flat()

Crea un array que es una versión aplanada (flatten) del array original, un array con todos los elementos de los subarrays concatenados de manera recursiva hasta la profundidad especificada, elimina la anidación de arrays.

**Sintaxis**
```typescript
arrayNombre.flat(depth: number)
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
```typescript
arrayNombre.flatMap(function callback(currentValue, index, array): any {
  // elemento para retornar
},[, thisArg])
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
```typescript
arrayNombre.forEach(function callback(currentValue, index, array): void {
  // lógica para ejecutar por cada elemento
}, [, thisArg])
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

## Array.from()

Crea un nuevo array a partir de un objeto iterable como un `NodeList`, un string o de un objeto similar a un array.

**Sintaxis**
```typescript
Array.from(objetoIterable, function mapeo(element, index) {
  // función que se aplica a cada elemento del objeto iterable antes de agregarlo al nuevo array.
}, thisArg)
```

**Ejemplo**
```javascript
const cadena = 'Hola';

const arrayCadena = Array.from(cadena);

console.log(arrayCadena); // Retorna ['H', 'o', 'l', 'a']
```

## Array.prototype.includes()

Determina si el array incluye un elemento, si se encuentra devuelve `true` de lo contrario devolverá `false`.

**Sintaxis**
```typescript
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
```typescript
arrayNombre.indexOf(elemento, indiceInicio)
```

**Ejemplo**
```javascript
const colores = ['rojo', 'azul', 'amarillo'];

console.log(colores.indexOf('azul'));    // Retorna 1
console.log(colores.indexOf('verde'));   // Retorna -1
```

## Array.prototype.join()

Convierte todos los elementos de un array a string y los une utilizando el separador que recibe como argumento.

**Sintaxis**
```typescript
arrayNombre.join(separador)
```

**Ejemplo**
```javascript
const frutas = ['manzana', 'banana', 'pera'];

const cadena = frutas.join(', ');

console.log(cadena); // Retorna "manzana, banana, pera"
```

**Notas**
- Si no se proporciona un separador, se utiliza una coma por defecto.

## Array.prototype.keys()

Retorna un objeto Array Iterator que contiene los índices de los elementos del array.

**Sintaxis**
```typescript
arrayNombre.keys()
```

**Ejemplo**
```javascript
const colores = ['rojo', 'azul', 'amarillo'];

const iterator = colores.keys();

console.log(iterator.next().value); // Retorna 0
console.log(iterator.next().value); // Retorna 1
console.log(iterator.next().value); // Retorna 2
```

**Notas**
- Cada llamada al método `next()` del iterador retorna el siguiente índice.

## Array.prototype.lastIndexOf()

Retorna el último índice en el que se encuentra un determinado elemento en un array, retorna -1 si no se encuentra.

**Sintaxis**
```typescript
arrayNombre.lastIndexOf(elemento, indiceInicio)
```

**Ejemplo**
```javascript
const colores = ['rojo', 'azul', 'amarillo', 'rojo'];

console.log(colores.lastIndexOf('rojo')); // Retorna 3
console.log(colores.lastIndexOf('verde')); // Retorna -1
console.log(colores.lastIndexOf('amarillo', 2)); // Retorna 2
```

**Notas**
- La busqueda se hace de derecha a izquierda o desde el último elemento hasta el primero.
- Se puede pasar un segundo argumento para indicar donde se comienza a realizar la busqueda.

## Array.prototype.map()

Crea un nuevo array con los resultados de aplicar una función de callback a cada elemento del array.

**Sintaxis**
```typescript
arrayNombre.map(function callback(currentValue: any, index: number, array: any[]): any {
  // elemento para retornar
}[, thisArg])
```

**Ejemplo**
```javascript
const numeros = [1, 2, 3];

const numerosDoble = numeros.map((numero) => numero * 2);

console.log(numerosDoble); // Retorna [2, 4, 6]
```

## Array.prototype.pop()

Elimina el último elemento del array y lo retorna.

**Sintaxis**
```javascript
arrayNombre.pop()
```

**Ejemplo**
```javascript
const frutas = ['manzana', 'banana', 'pera'];

const ultimaFruta = frutas.pop();

console.log(ultimaFruta); // Retorna "pera"
console.log(frutas);      // Retorna ['manzana', 'banana']
```

**Notas**
- Modifica el array original.

## Array.prototype.push()

Agrega uno o más elementos al final del array y retorna la longitud del array.

**Sintaxis**
```javascript
arrayNombre.push(elemento1, elemento2, ..., elementoN)
```

**Ejemplo**
```javascript
const colores = ['rojo', 'azul'];

const nuevaLongitud = colores.push('amarillo', 'verde');

console.log(nuevaLongitud);    // Retorna 4
console.log(colores);          // Retorna ['rojo', 'azul', 'amarillo', 'verde']
```

**Notas**
- Modifica el array original.

## Array.prototype.reduce()

Aplica un callback a un acumulador y a cada elemento del array (de izquierda a derecha) para reducirlo a un único valor, que al final es retornado.

**Sintaxis**
```typescript
arrayNombre.reduce(function callback(acumulador, currentValue, index, array): any {
  // retornar acumulador
}, [, valorInicial])
```

**Ejemplo**
```javascript
const numeros = [1, 2, 3, 4, 5];

const suma = numeros.reduce((acumulador, numero) => acumulador + numero);

console.log(suma); // Retorna 15
```

**Notas**
- El acumulador se actualiza en cada iteración.

## Array.prototype.reduceRight()

Aplica un callback a un acumulador y a cada elemento del array (de derecha a izquierda) para reducirlo a un único valor, que al final es retornado.

**Sintaxis**
```typescript
arrayNombre.reduceRight(function callback(acumulador, currentValue, index, array): any {
  // retornar acumulador
}, [, valorInicial])
```

**Ejemplo**
```javascript
const numeros = [1, 2, 3, 4, 5];

const resta = numeros.reduceRight((acumulador, numero) => acumulador - numero);

console.log(resta); // Retorna -5
```

**Notas**
- El acumulador se actualiza en cada iteración.

## Array.prototype.reverse()

Invierte el orden de los elementos del array.

**Sintaxis**
```javascript
arrayNombre.reverse()
```

**Ejemplo**
```javascript
const colores = ['rojo', 'azul', 'amarillo'];

colores.reverse();

console.log(colores); // Retorna ['amarillo', 'azul', 'rojo']
```

**Notas**
- Modifica el array original.

## Array.prototype.shift()

Elimina el primer elemento del array y lo retorna.

**Sintaxis**
```javascript
arrayNombre.shift()
```

**Ejemplo**
```javascript
const frutas = ['manzana', 'banana', 'pera'];

const primeraFruta = frutas.shift();

console.log(primeraFruta); // Retorna "manzana"
console.log(frutas);       // Retorna ['banana', 'pera']
```

**Notas**
- Modifica el array original.

## Array.prototype.slice()

Crea una copia de una porción del array original en un nuevo array.

**Sintaxis**
```javascript
arrayNombre.slice(inicio, fin)
```

**Ejemplo**
```javascript
const numeros = [1, 2, 3, 4, 5];

const subArray = numeros.slice(2, 4);

console.log(subArray); // Retorna [3, 4]
```

**Notas**
- Si no se proporciona el índice de fin, se copian todos los elementos a partir del índice de inicio hasta el final del array.
- No modifica el array original.

## Array.prototype.some()

Verifica si al algún un elemento del array cumple con una condición.

**Sintaxis**
```typescript
arrayNombre.some(function callback(item): boolean {
  // condicion para retornar
}, [, thisArg])
```

**Ejemplo**
```javascript
const numeros = [1, 2, 3, 4, 5];

const tienePares = numeros.some((numero) => numero % 2 === 0);

console.log(tienePares); // Retorna true
```

**Notas**
- Retorna `true` si al menos un elemento cumple con la condición, de lo contrario, retorna `false`.

## Array.prototype.sort()

Ordena los elementos del array de acuerdo a la función de ordenamiento especificada.

**Sintaxis**
```typescript
arrayNombre.sort(function funcionOrdenamiento (aElement, bElement): number {
  // condicion de ordenamiento
})
```

**Ejemplo**
```javascript
const frutas = ['manzana', 'banana', 'pera'];

frutas.sort();

console.log(frutas); // Retorna ['banana', 'manzana', 'pera']
```

**Notas**
- Ordena los elementos del array de forma lexicográfica (orden alfabético) por defecto.
- Modifica el array original.

## Array.prototype.splice()

Cambia el contenido de un array eliminando, reemplazando o agregando elementos. Retorna un array que contiene los elementos eliminados.

**Sintaxis**
```javascript
arrayNombre.splice(indiceInicio, cantidadEliminar, elemento1: any, ..., elementoN)
```

**Ejemplo**
```javascript
const colores = ['rojo', 'azul', 'amarillo'];

const valorEliminado = colores.splice(1, 1, 'verde', 'naranja');

console.log(valorEliminado) // Retorna ['azul']
console.log(colores); // Retorna ['rojo', 'verde', 'naranja', 'amarillo']
```

**Notas**
- Modifica el array original.

## Array.prototype.toLocaleString()

Retorna un string que representa los elementos del array en el formato del lenguaje local.

**Sintaxis**
```javascript
arrayNombre.toLocaleString(locales, opciones)
```

**Ejemplo**
```javascript
const fechas = [1, 'enero 2023', new  Date('21 Dec 1997 14:12:00 UTC')]

const fechasLocales = fechas.toLocaleString('en', { timeZone: 'UTC' })

console.log(fechasLocales) // retorna '1,enero 2023,12/21/1997, 2:12:00 PM'
```

**Notas**
- Los locales y opciones pueden ser especificados para controlar el formato de la cadena resultante.

## Array.prototype.toReversed()

Es la copia del método reverse(). Devuelve una nueva matriz con los elementos en orden inverso.

**Sintaxis**
```javascript
toReversed()
```

**Ejemplo**
```javascript
const items = [1, 2, 3];

const reversedItems = items.toReversed();

console.log(reversedItems); // [3, 2, 1]
console.log(items); // [1, 2, 3]
```

## Array.prototype.toSorted()

Es la versión de copia del método sort(). Devuelve un nuevo array con los elementos ordenados en orden ascendente por defecto.

**Sintaxis**
```javascript
toSorted(function compareFn(a, b) { /* … */ })
```

**Ejemplo**
```javascript
const months = ["Mar", "Jan", "Feb", "Dec"];
const sortedMonths = months.toSorted();

console.log(sortedMonths); // ['Dec', 'Feb', 'Jan', 'Mar']
console.log(months); // ['Mar', 'Jan', 'Feb', 'Dec']
```

## Array.prototype.toSpliced()

Es la versión de copia del método splice(). Devuelve un nuevo array con algunos elementos eliminados y/o reemplazados en un índice dado.

**Sintaxis**
```javascript
toSpliced(start, deleteCount, item1, ..., itemN)
```

**Ejemplo**
```javascript
const meses = ["Jan", "Mar", "Apr", "May"];

// insertar elemento en el indice 1
const meses2 = meses.toSpliced(1, 0, "Feb");
console.log(meses2); // ["Jan", "Feb", "Mar", "Apr", "May"]

// el array original no es modificado
console.log(meses); // ["Jan", "Mar", "Apr", "May"]
```

## Array.prototype.toString()

Retorna un string con los elementos del array.

**Sintaxis**
```javascript
arrayNombre.toString()
```

**Ejemplo**
```javascript
const frutas = ['manzana', 'banana', 'pera'];

const cadena = frutas.toString();

console.log(cadena); // Retorna "manzana,banana,pera"
```

**Notas**
- Los elementos son separados por comas sin espacios.

## Array.prototype.unshift()

Agrega uno o más elementos al inicio del array y retorna la nueva longitud del array.

**Sintaxis**
```javascript
arrayNombre.unshift(elemento1, elemento2, ..., elementoN)
```

**Ejemplo**
```javascript
const colores = ['rojo', 'azul'];

const nuevaLongitud = colores.unshift('amarillo', 'verde');

console.log(nuevaLongitud); // Retorna 4
console.log(colores);       // Retorna ['amarillo', 'verde', 'rojo', 'azul']
```

**Notas**
- Modifica el array original.

## Array.prototype.values()

Retorna un nuevo objeto iterador que contiene los valores de los elementos del array.

**Sintaxis**
```javascript
arrayNombre.values()
```

**Ejemplo**
```javascript
const colores = ['rojo', 'azul', 'amarillo'];

const iterador = colores.values();

console.log(iterador.next().value); // Retorna 'rojo'
console.log(iterador.next().value); // Retorna 'azul'
console.log(iterador.next().value); // Retorna 'amarillo'
```

**Notas**
- Puede ser utilizado en un bucle `for...of` para iterar sobre los valores del array.

## Array.prototype.with()

Recibe un índice y un valor/elemento. Retorna un nuevo array remplazando el elemento en el índice especificado por el nuevo elemento.

**Sintaxis**
```javascript
arrayObject.with(index, value)
```

**Ejemplo**
```javascript
const arr = [1, 2, 3, 4, 5];

console.log(arr.with(2, 6)); // [1, 2, 6, 4, 5]
console.log(arr); // [1, 2, 3, 4, 5]
```

**Notas**
- Crea y retona un nuevo array.
