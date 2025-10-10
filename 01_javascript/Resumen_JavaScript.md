# 📘 Resumen de JavaScript

> [!NOTE]
> Esta guía resume todos los temas de JavaScript desde nivel básico hasta avanzado,
> basándose en ejercicios prácticos. Incluye ejemplos, notas y consejos útiles.

---

## 🧭 Índice

- [📘 Resumen de JavaScript](#-resumen-de-javascript)
  - [🧭 Índice](#-índice)
  - [🧱 Fundamentos](#-fundamentos)
    - [Hola Mundo y Variables](#hola-mundo-y-variables)
    - [Tipos de Datos y Operadores](#tipos-de-datos-y-operadores)
  - [🔁 Estructuras de Control](#-estructuras-de-control)
    - [Condicionales](#condicionales)
    - [Switch](#switch)
    - [Ciclos](#ciclos)
  - [⚙️ Funciones](#️-funciones)
  - [🧮 Arreglos y Métodos](#-arreglos-y-métodos)
  - [🧩 Objetos y Operadores](#-objetos-y-operadores)
    - [Operador Spread y Ternario](#operador-spread-y-ternario)
  - [🧱 Programación Orientada a Objetos (POO)](#-programación-orientada-a-objetos-poo)
    - [Métodos Estáticos](#métodos-estáticos)
  - [⚡ Asincronía en JavaScript](#-asincronía-en-javascript)
    - [Callbacks](#callbacks)
    - [Promesas](#promesas)
    - [Async / Await](#async--await)
  - [🧰 Snippets y Comandos Útiles](#-snippets-y-comandos-útiles)
    - [Manipulación de Arrays](#manipulación-de-arrays)
    - [Validaciones rápidas](#validaciones-rápidas)
    - [Fechas y Tiempos](#fechas-y-tiempos)

---

## 🧱 Fundamentos

### Hola Mundo y Variables

```js
console.log("Hola Mundo");
let nombre = "Sebastián";
const PI = 3.1416;
var edad = 25;
```

> [!TIP]
> Usa `let` para variables que cambian y `const` para constantes. Evita `var` en código moderno.

---

### Tipos de Datos y Operadores

```js
let numero = 10;
let texto = "Hola";
let booleano = true;
let indefinido;
let nulo = null;
```

> [!NOTE]
> Los operadores aritméticos incluyen `+`, `-`, `*`, `/`, `%`.
> Los operadores lógicos son `&&`, `||`, `!`.

---

## 🔁 Estructuras de Control

### Condicionales

```js
if (edad >= 18) {
  console.log("Eres mayor de edad");
} else {
  console.log("Eres menor de edad");
}
```

### Switch

```js
let dia = "lunes";
switch (dia) {
  case "lunes":
    console.log("Inicio de semana");
    break;
  case "viernes":
    console.log("Fin de semana");
    break;
  default:
    console.log("Día normal");
}
```

> [!TIP]
> Usa `switch` cuando tengas múltiples condiciones basadas en el mismo valor.

---

### Ciclos

```js
for (let i = 0; i < 5; i++) console.log(i);

let i = 0;
while (i < 5) {
  console.log(i);
  i++;
}
```

> [!NOTE]
> `break` interrumpe un bucle, `continue` salta a la siguiente iteración.

---

## ⚙️ Funciones

```js
function saludar(nombre) {
  return `Hola ${nombre}`;
}

const despedir = (nombre) => `Adiós ${nombre}`;
```

> [!TIP]
> Usa funciones flecha (`=>`) para callbacks o funciones cortas.
> Las funciones tradicionales son mejores cuando se requiere `this`.

---

## 🧮 Arreglos y Métodos

```js
let frutas = ["manzana", "pera", "mango"];
frutas.push("uva");
frutas.forEach((f) => console.log(f));
```

> [!IMPORTANT]
> Métodos útiles: `map`, `filter`, `reduce`, `find`, `some`, `every`.

---

```js
let numeros = [1, 2, 3, 4, 5];
let dobles = numeros.map((n) => n * 2);
let pares = numeros.filter((n) => n % 2 === 0);
let suma = numeros.reduce((a, b) => a + b, 0);
```

> [!TIP]
> `map` transforma, `filter` selecciona y `reduce` acumula valores.

---

## 🧩 Objetos y Operadores

```js
const persona = {
  nombre: "Carlos",
  edad: 30,
  saludar() {
    console.log(`Hola, soy ${this.nombre}`);
  },
};
persona.saludar();
```

> [!NOTE]
> Los objetos pueden tener propiedades y métodos.
> Se accede con `obj.prop` o `obj["prop"]`.

### Operador Spread y Ternario

```js
const numeros1 = [1, 2, 3];
const numeros2 = [...numeros1, 4, 5];

let edadUsuario = 20;
let mensaje = edadUsuario >= 18 ? "Adulto" : "Menor";
```

> [!TIP]
> El operador spread (`...`) copia o combina objetos y arrays.
> El operador ternario simplifica decisiones cortas.

---

## 🧱 Programación Orientada a Objetos (POO)

```js
class Persona {
  constructor(nombre, edad) {
    this.nombre = nombre;
    this.edad = edad;
  }

  saludar() {
    console.log(`Hola, soy ${this.nombre}`);
  }
}

class Estudiante extends Persona {
  constructor(nombre, edad, carrera) {
    super(nombre, edad);
    this.carrera = carrera;
  }
}

const alumno = new Estudiante("Ana", 22, "Ingeniería");
alumno.saludar();
```

> [!IMPORTANT]
> La herencia se implementa con `extends` y `super()` para llamar al constructor padre.

---

### Métodos Estáticos

```js
class Calculadora {
  static sumar(a, b) {
    return a + b;
  }
}

console.log(Calculadora.sumar(3, 4));
```

> [!NOTE]
> Los métodos estáticos se usan sin crear una instancia de la clase.

---

## ⚡ Asincronía en JavaScript

### Callbacks

```js
function obtenerDatos(callback) {
  setTimeout(() => {
    callback("Datos recibidos");
  }, 2000);
}

obtenerDatos((mensaje) => console.log(mensaje));
```

### Promesas

```js
const promesa = new Promise((resolve, reject) => {
  let exito = true;
  exito ? resolve("Operación exitosa") : reject("Error");
});

promesa.then(console.log).catch(console.error);
```

### Async / Await

```js
async function cargarDatos() {
  try {
    let respuesta = await promesa;
    console.log(respuesta);
  } catch (error) {
    console.error(error);
  }
}
```

> [!TIP]
> `async/await` simplifica el manejo de promesas de forma legible y secuencial.

---

## 🧰 Snippets y Comandos Útiles

### Manipulación de Arrays

```js
// Quitar duplicados
const unicos = [...new Set([1, 2, 2, 3])];

// Ordenar
const ordenados = [3, 1, 2].sort((a, b) => a - b);

// Mezclar
const mezclados = [1, 2, 3].sort(() => Math.random() - 0.5);
```

### Validaciones rápidas

```js
if (!variable) console.warn("Variable no definida o vacía");
if (Array.isArray(variable)) console.log("Es un array");
```

### Fechas y Tiempos

```js
const ahora = new Date();
console.log(ahora.toLocaleDateString());
```

> [!NOTE]
> JavaScript maneja las fechas con el objeto `Date`.
> También puedes usar librerías como **Day.js** o **Moment.js** para mayor control.