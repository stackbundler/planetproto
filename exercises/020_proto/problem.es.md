El objeto \_\_proto\_\_
------------------

Para entender las cadenas de prototipos, no hay nada más simple que la propiedad
`__proto__`. Desgraciadamente `__proto__` todavía no es parte de la interfaz
estándar de JavaScript, por lo menos no hasta ES6. Así que probablemente no
deberías usarlo en el mundo real. No obstante, ayuda mucho a explicar los
prototipos de una forma sencilla.

```js
// creémos un objeto alien
var alien = {
  kind: 'alien'
};

// y un objeto robot
var robot = {
  kind: 'robot'
};

// y un objeto llamado 'zippy'
var zippy = {};

// asignamos alien como el prototipo de zippy
zippy.__proto__ = alien;

// zippy ahora está vinculado a alien
// 'hereda' las propiedades de alien
console.log(zippy.kind); //=> 'alien'

// asignamos robot como el prototipo de zippy
zippy.__proto__ = robot;

// y ahora zippy está vinculado a robot
console.log(zippy.kind); //=> 'robot'
```

Como puedes ver, la propiedad `__proto__` es bastante clara y fácil de usar.
Incluso si no deberíamos usar `__proto__` en producción, creo que estos ejemplos
nos dan una buena base para entender la modelo de objetos de JavaScript.

Puedes comprobar si un objeto es el prototipo de otro objeto así:

```js
console.log(alien.isPrototypeOf(zippy));
//=> true
```

Desafío
-------

Un archivo llamado `020.js` se ha creado automáticamente en el directorio
actual. Este archivo contiene el 'boilerplate' con las instrucciones y los
lugares donde añadir tu código debidamente señalados.