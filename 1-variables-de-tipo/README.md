# 📚 Variables y Tipos de Datos en JavaScript

## 1. Introducción
En JavaScript, los datos se manejan mediante **variables** que almacenan valores de distintos **tipos**.  
**Importancia**:  
- Base para operaciones, funciones y estructuras complejas.  
- Comprenderlos evita errores comunes (ej: `NaN`, `undefined`).

---

## 2. Declaración de Variables
### 2.1 `var`, `let` y `const`
```javascript
var antigua = "no recomendada"; // Hoisting, scope de función
let mutable = "puede cambiar"; // Scope de bloque
const constante = "inmutable"; // Debe inicializarse
```

#### Diferencias Clave:
| Característica   | `var`      | `let`      | `const`    |
|------------------|------------|------------|------------|
| Scope            | Función    | Bloque     | Bloque     |
| Reasignación     | Sí         | Sí         | No         |
| Hoisting         | Sí         | No*        | No*        |

> **Nota**: `let`/`const` tienen "hoisting" pero no se pueden acceder antes de su declaración (Temporal Dead Zone).

---

## 3. Tipos de Datos
### 3.1 Primitivos
```javascript
typeof "Hola";       // "string"
typeof 42;           // "number"
typeof true;         // "boolean"
typeof undefined;    // "undefined"
typeof null;         // "object" (¡error histórico!)
typeof Symbol("id"); // "symbol"
typeof 42n;          // "bigint"
```

### 3.2 Objetos
```javascript
typeof { nombre: "Luisa" }; // "object"
typeof [1, 2, 3];           // "object"
typeof function() {};       // "function"
```

#### Comparación de Tipos:
```javascript
null == undefined;  // true
null === undefined; // false
"5" == 5;           // true (coerción)
"5" === 5;          // false
```

---

## 4. Conversión de Tipos (Coerción)
### 4.1 Explícita
```javascript
Number("123");    // 123
String(123);      // "123"
Boolean("hola");  // true
```

### 4.2 Implícita
```javascript
"5" + 2;    // "52" (concatena)
"5" - 2;    // 3 (resta numérica)
+"123";     // 123 (unary plus)
!!0;        // false (doble negación)
```

---

## 5. Casos Especiales y Errores Comunes
### 5.1 `NaN` (Not a Number)
```javascript
isNaN("hola"); // true
Number.isNaN("hola"); // false (más seguro)
```

### 5.2 Valores Falsy
```javascript
if ("") { /* No se ejecuta */ }
if (0) { /* No se ejecuta */ }
if (null) { /* No se ejecuta */ }
```

---

## 🧪 Ejemplos Avanzados
```javascript
// BigInt para números grandes
const bigNum = 9007199254740991n + 2n; // 9007199254740993n

// Symbol para identificadores únicos
const id = Symbol("id");
```

---

## 🏋️ Ejercicios Prácticos
1. **Conversión Segura**:  
   Escribe una función que convierta cualquier valor a número sin errores.  
   ```javascript
   function aNumero(valor) { /* ... */ }
   ```

2. **Comparación Profunda**:  
   Crea una función que compare dos valores considerando `NaN`, `null`, etc.  
   ```javascript
   function esIgual(a, b) { /* ... */ }
   ```

🔍 **[Ver ejercicios.js](./ejercicios.js)**  
💡 **[Soluciones explicadas](./soluciones.md)**

---

## 📚 Recursos Adicionales
- [MDN - Variables](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Grammar_and_types#declaraciones)
- [JavaScript.info - Types](https://javascript.info/types)