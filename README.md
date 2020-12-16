# Jest

Jest es una herramienta que nos permite hacer pruebas en React

# Instalacion

```
mkdir jestnotes
cd jestnotes
git init
npm init -y
```
Instalar Jest

```
npm i jest --save-dev
```

* Crear carpeta **src** y un archivo index.js dentro
* Dentro de **src** crear la carpeta **__test__** 
* Dentro de la carpeta __test__ crear el archivo **global.test.js**

# Test de strings

en el archivo global.test.js escribir 

```js
const text = "Hola mundo";
test("Debe contener un texto",()=>{
  expect(text).toMatch(/Mundo/);
});
```

### configurar el comando test

En la parte de scripts en el package.json colocar:
```
"test": "jest"
```

Ahora podemos correr el test en la terminal
```
npm run test 
```
o 
```
npm test 
```

# Test de arrays

en el archivo global.test.js agregar 

```js
const frutas = ['manzana', 'banana','pera'];

test("Tenemos una manzana",()=>{
  expect(frutas).toContain('manzana');
});
```

# Test de Mayor que..

en el archivo global.test.js agregar 

```js
test("Mayor que",()=>{
  expect(10).toBeGreaterThan(9);
});
```

# Test de Boleanos

en el archivo global.test.js agregar 

```js
test("Verdadero",()=>{
  expect(true).tobeTruthy();
});
```

# Test de callbacks

en el archivo global.test.js agregar 

```js
const reverseString = (str, callback)=>{
  callback(str.split("").reverse().join(""))
}

test("Probar un callback",()=>{
  reverseString('Hola', (str)=>{
    expect(str).ToBe('aloH');
  });
});
```
