# Inicializar el proyecto

## Repositorio

Inicializamos nuestro _NPM_ y creamos un repositorio git

```sh
mkdir curso-testing
cd curso-testing
npm init #respondemos a las preguntas que nos va haciendo
echo "# Curso de Testing" >> readme.md
git init
git add . #stage de readme.md y package.json
git commit -m "Primer commit"
git remote add origin https://github.com/jseto/curso-testing.git #cambialo por tu repositorio en github
git checkout -b development # creamos un rama para desarrollo y la activamos
git push -u origin --all # enviamos al repositorio remoto
code .gitignore # editalo con tu editor favorito
```

## Instalación de dependencias

Para no despistar, iremos instalando los paquetes a medida que los vayamos necesitando. De momento solo necesitaremos TypeScript como lenguaje de programación principal y Jest para los tests. Como los tests son independientes de las librerías o frameworks que vayamos a usar, no nos hace falta instalar ninguna de ellas por el momento.

```sh
npm i -D typescript jest
npm i -g typescript # para poder usar typescript desde la linea de comandos
```

## Configuración de TypeScript

Para configurar el comportamiento del compilador de TypeScript se usa el fichero [tsconfig.json](./tsconfig.json) que se suele guardar en la raíz del proyecto.

Creamos nuestro primer programa en TypeScript en [./src/index.ts](./src/index.ts) y lo compilamos con `tsc` y ejecutamos con `node` para verificar que TypeScript funciona.

```sh
tsc
node ./out/index.js
```

## Configuración de Jest

Jest es la plataforma que nos permite ejecutar los tests de nuestro proyecto.

Para que Jest use TypeScript debemos instalar el paquete `ts-jest` y para poder trabajar con los tipos que define Jest, el paquete `@types/jest`


```sh
npm i -D ts-jest @types/jest
```

Configuramos con el fichero [jest.config.js](./jest.config.js) en la raíz del proyecto y verificamos que Jest funciona creando nuestro primer test.

Para ello, creamos el fichero [./test/index.spec.ts](./test/index.spec.ts) y ejecutamos

```sh
jest
```

o bien 

```sh
jest --watch
```

Si queremos que los tests se ejecuten cada vez que se actualiza el proyecto.

Para comprobar que todo va bien, creamos un pequeño test en el anterior [fichero](./test/index.spec.ts)

y ejecutamos Jest

```sh
jest

 PASS  test/index.spec.ts
  ✓ al comparar dos números iguales, el test debería pasar (3 ms)

Test Suites: 1 passed, 1 total
Tests:       1 passed, 1 total
Snapshots:   0 total
Time:        1.201 s, estimated 3 s
Ran all test suites.
```
