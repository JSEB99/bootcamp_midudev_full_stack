# JavaScript Notes

## Contenido
- [JavaScript Notes](#javascript-notes)
  - [Contenido](#contenido)
  - [Fuentes](#fuentes)
  - [¿Qué es JavaScript?](#qué-es-javascript)
  - [Consola del navegador](#consola-del-navegador)
  - [Tipos de datos](#tipos-de-datos)
  - [Primitivos](#primitivos)
  - [Operadores aritméticos](#operadores-aritméticos)
  - [Operadores comparación](#operadores-comparación)
  - [Operadores lógicos](#operadores-lógicos)
  - [Variables](#variables)
  - [Comentarios](#comentarios)
  - [console.log()](#consolelog)
  - [Operador `typeof`](#operador-typeof)
    - [Uso en operadores de comparación](#uso-en-operadores-de-comparación)
  - [`null` y `underfined`](#null-y-underfined)

## Fuentes
- [Aprende JavaScript](https://www.aprendejavascript.dev)

## ¿Qué es JavaScript?

**JavaScript** es uno de los lenguajes de programación más usados y populares del mundo. **Nació en 1995** para darle interactividad a las páginas web y desde entonces ha evolucionado hasta convertirse en un lenguaje de programación de propósito general. Dicho de otra forma: se puede usar casi **para cualquier cosa**.

> Enfocado en **desarrollo web**, pero es de **proposito general**

- [Regresar](#contenido)

## Consola del navegador

> Recomendados Chrome, Firefox y Brave

Ejecutar código JavaScript y ver la salida del programa. ¿Cómo podemos abrirla?
1. Vamos a `about:blank` en el navegador *(Evitar distracciones)*
2. `Clic derecho > Inspeccionar`
3. En la nueva ventana, buscamos la pestaña `consola`
   1. Podemos separar la ventana dando clic en los **3 puntos**

En esta ventana podemos poner código JavaScript y nos mostrará la salida del mismo.

> [!NOTE]
> Limpiar la consola con la función `clear()` o con el atajo `Ctrl+K`

- [Regresar](#contenido)

## Tipos de datos

Existen:
- Primitivos
- Objetos y funciones

## Primitivos

> Más atómatico, mas sencillo, mas puro.

Donde tenemos:
- `Number`: abarca enteros, decimales, la palabra reservada `Infinity` y si el número es muy grande podemos usar el *exponencial* `2.99e8`. Tenemos [operaciones aritmeticas](operadores-aritmeticos)
- `String`: podemos usar comillas simples, acento invertido y comillas dobles. *(Con `shift+Enter` damos salto de línea en la consola con textos largos)*. Para concatenar podemos usar el `+`.
- `Booleanos`
- `Null`
- `Undefined`
- `BigInt`
- `Symbol`

- [Regresar](#contenido)

## Operadores aritméticos

- `+`: suma
- `-`: resta
- `*`: multiplicación
- `/`: división
- `%`: módulo (resto de la división)
- `**`: exponente

- [Regresar](#contenido)

## Operadores comparación

- `>`: mayor que
- `>=`: mayor o igual que
- `>`: menor que
- `>=`: menor o igual que
- `==`: igual que *(solo valor)*
- `===`: igual que *(valor y tipo de dato)*
- `!=`: diferente *(solo valor)*
- `!==`: diferente *(valor y tipo de dato)*

- [Regresar](#contenido)

## Operadores lógicos

- `&&`: and
- `||`: or
- `!`: not *(!true = false)*

- [Regresar](#contenido)

## Variables

Para crear una variable usamos `let` seguido del nombre de la variable. Es un lenguaje de `tipado dinámico` por lo que podemos reasignarle el valor de la variable al tipo de dato y valor que queramos. Ademas **podemos declarar la variable sin asignarle un valor** `let varX` y mas adelante le podriamos dar su valor `varX = 'variable x'`.

> [!NOTE]
> En JavaScript la convención que se utiliza para nombrar variables es `camelCase`, **minuscula la primer palabra y la siguientes con la primera letra en mayuscula, sin espacios.**

Tenemos otro tipo `const` y esta manera asignamos valores a variables que **no pueden ser reasignadas**. Se mantendran **constantes** todo el tiempo. 

> [!NOTE]
> Las variables `const` o **constantes** usan la convención de `SCREAMING_CASE` y es escribir su nombre **todo en mayusculas y separando palabras con `_`**

Otro tipo son las variables `var`, es la forma *mas antigua* y actualmente no es recomendable. Es **similar a let**, pero su diferencia radica en el **scope**, donde `var` es **global**.

- [Regresar](#contenido)

## Comentarios

- `//`: de una sola línea
- `/* ... */`: de más de una linea

- [Regresar](#contenido)

## console.log()

Es una **función integrada en JavaScript** que se utiliza para **imprimir mensajes en la consola** del navegador o del editor de código. Se utiliza principalmente para **depurar el código y para imprimir valores** de variables y mensajes para ayudar en el proceso de desarrollo.

```js
console.log('Hola, JavaScript') // Hola, JavaScript
let lenguaje = 'JavaScript'
console.log('Hola' +  lenguaje) // Hola JavaScript
const pi = 3.1416
console.log('Numero pi:',pi) // Numero pi: 3.1416
```

Tenemos más métodos con console:

- `console.error()`: Imprime un error en la consola
- `console.warn()`: Imprime  una advertencia en la consola
- `console.info()`: Imprime información en la consola

```js
console.error('Error')
// ❌ Error
console.warn('Advertencia')
// ⚠️ Advertencia
console.info('Información')
// ℹ️ Información
```

- [Regresar](#contenido)

## Operador `typeof`

El operador `typeof` devuelve una cadena de texto que indica el **tipo de un operando**. Puede ser usado con cualquier tipo de operando, incluyendo variables y literales.

```js
typeof undefined // "undefined"
typeof true // "boolean"
typeof 42 // "number"
typeof 'Hola mundo' // "string"
```

Existe, sin embargo, un valor especial en JavaScript, `null`, que es considerado un **bug en el lenguaje**. El operador typeof devuelve "object" cuando se usa con null:

```js
typeof null // "object"
```

> Lo correcto sería que `typeof null` devolviera **"null"**, pero es un [error histórico que no se puede corregir sin romper el código existente](https://2ality.com/2013/10/typeof-null.html).

Por eso, si quieres comprobar si una variable es null, debes usar la comparación estricta `===`:

```js
const foo = null
foo === null // true
```

### Uso en operadores de comparación

```js
const age = 42
typeof age === 'number' // true
// o
typeof age === 'number' && age > 18 // true
```

- [Regresar](#contenido)

## `null` y `underfined`

La particularidad de estos dos tipos de datos es que **cada uno sólo tiene un valor**. El tipo null sólo puede tener el valor null y el tipo undefined sólo puede tener el valor undefined.

Si creamos una variable **sin valor**, esta será automáticamente `underfined`, ademas tambien podemos asignarselo directamenre

```js
let rolloDePapel // -> undefined
let rolloDePapel = undefined // -> undefined
```

En cambio, con `null` solo podemos conseguirlo asignandole el valor `null`

```js
let rolloDePapel = null
```