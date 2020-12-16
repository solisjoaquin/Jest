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
