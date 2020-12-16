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

# Test de promesas

en el archivo global.test.js agregar 

```js
const reverseString2 = str =>{
  return new Promise((resolve, reject)=>{
    if (!str){
      reject(Error('Error'))
    }
    resolve(str.split("").reverse().join(""))
  });
};

test("Probar una promesa",()=>{
  return reverseString2('Hola').then(str)=>{
    expect(str).ToBe('aloH');
  });
});
```

# Test de async await

en el archivo global.test.js agregar 

```js
const reverseString2 = str =>{
  return new Promise((resolve, reject)=>{
    if (!str){
      reject(Error('Error'))
    }
    resolve(str.split("").reverse().join(""))
  });
};

test("Probar async/await", async ()=>{
  const string = await reverseString2('Hola');
  expect(string).ToBe('aloH');
});
```

# Usar afterEach y afterAll

afterEach --> despues de cada prueba

afterAll --> despues de todas las pruebas

beforeEach  --> antes de cada prueba

```js
afterEach(() => console.log('despues de cada prueba'));
afterAll(() => console.log('despues de todas las pruebas'));

beforeEach(() => console.log('antes de cada prueba'));
beforeAll(() => console.log('antes de todas las pruebas'));
```

