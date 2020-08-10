# Tutorial para crear un SaaS de 0 a 100

## Inicializar el proyecto

```sh
mkdir guia-saas
cd guia-saas
npm init #respondemos a las preguntas que nos va haciendo
echo "# Tutorial para crear un SaaS de 0 a 100" >> readme.md
git init
git add . #stage de readme.md y package.json
git commit -m "Primer commit"
git remote add origin https://github.com/jseto/guia-saas.git #cambialo por tu repositorio en github
git checkout -b development # creamos un rama para desarrollo y la activamos
git push -u origin --all # enviamos al repositorio remoto
code .gitignore # editalo con tu editor favorito
```

## Instalación de dependencias

Para no despistar, iremos instalando los paquetes a medida que los vayamos necesitando. De momento solo necesitaremos Typescript como lenguaje de programación principal y Jest para los tests. Como empezaremos programando la lógica del negocio, no necesitamos ninguna librería adicional y por lo tanto no instalamos React ni otras librerías como Firebase.

```sh
npm i -D typescript jest
```

## Configuración de Typescript

Para configurar el comportamiento del compilador de Typescript se usa el fichero [tsconfig.json](./tsconfig.json) que se suele guardar en la raíz del proyecto.

Creamos nuestro primer programa en Typescript en [./src/index.ts](./src/index.ts) y lo compilamos con `tsc` y ejecutamos con `node` para verificar que Typescript funciona.

```sh
tsc ./src/index.ts
node ./src/index.js
```

## Configuración de Jest

Jest es la plataforma que nos permite ejecutar los tests de nuestro proyecto.

Para que Jest use Typescript debemos instalar el paquete `ts-jest` y para poder trabajar con los tipos que define Jest, el paquete `@types/jest`


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

si queremos que los tests se ejecuten cada vez que se actualiza el proyecto.

Al ejecutar Jest con un fichero vacío, este nos reportará que el test no ha pasado pero Jest debe ejecutarse sin errores. La respuesta de Jest debería ser parecida a esta:

```
 FAIL  test/index.spec.ts
 ● Test suite failed to run
   Your test suite must contain at least one test.
      at onResult (node_modules/@jest/core/build/TestScheduler.js:175:18)
      at node_modules/@jest/core/build/TestScheduler.js:304:17
      at node_modules/emittery/index.js:260:13
          at Array.map (<anonymous>)
      at Emittery.Typed.emit (node_modules/emittery/index.js:258:23)

Test Suites: 1 failed, 1 total
Tests:       0 total
Snapshots:   0 total
Time:        2.721 s
Ran all test suites.
```

Para comprobar que todo va bien, creamos un pequeño test en el anterior [fichero](./test/index.spec.ts)

## Configuración de Webpack

La configuración de Webpack es muy sencilla, simplemente le indicaremos en que fichero estará el script de arranque del proyecto, le pediremos que genere _source maps_ para poder depurar errores y que use el transpilador de Typescript con _ts-loader_.

Instalamos el paquete `ts-loader`

```sh
npm i -D ts-loader
```

```js
```

