---
title: "Intalación de dependencias para creación de una API con Node"
date: 2022-05-13
description: 'Para el Code Challenge de la semana 4 de Launch X'
---

Las APIs sirven para comunicar distintas partes de una aplicación de software. El code
challenge de la semana 4 de la misión backend de Launch X consistió en crear una API
muy sencilla que despliega en un servidor local la información contenida en un archivo json.
El challenge fue resuelto mediante TDD: Test Driven Development. Aquí explico paso a paso
cómo instalar las dependencias necesarias desde la terminal.

### Instalar dependencias

Si no tienes instalado NODE, visita la [documentación](https://nodejs.org/en/docs/) y continúa con las instrucciones.

Una vez creada la carpeta que guardará nuestro proyecto, correr los siguiente comandos uno
detrás de otro:

| Comando | Qué hace | Para qué |
|---|---|---|
| `npm init` | Indica que la carpeta contendrá un proyecto de NODE | Para poder tener un proyecto de NODE |
| `npm install--save-dev jest` | Instala Jest | Realizar pruebas de unidad |
| `npm install eslint --save-dev` | Instala Eslint | Lintern para corregir el estilo del código |
| `npm install express --save` | Instala Express | Montar el servidor |

Es MUY importante NO versionar el directorio `node_modules`. Crea un archivo `.gitignore` y agrégale la línea
`**/node_modules`. Ya puedes hacer commit.

Para automatizar los comandos, hay que modificar el archivo `package.json` para que la parte de los
scripts quede algo así:

```
"scripts": {
    "test": "node ./node_modules/.bin/jest",
    "linter": "node ./node_modules/eslint/bin/eslint.js .",
    "linter-fix": "node ./node_modules/eslint/bin/eslint.js . --fix",
    "server": "node ./app/lib/server.js"
  },
```

Ahora puedes usar las dependencias con los siguientes comandos:

| Comando | Qué corre |
|---|---|
| `npm test <ruta/del/archivo.test.js>` | Correr las pruebas |
| `npm run server` | Correr el servidor |
| `npm init @eslint/config` | Indicarle a Eslint qué tipo de código va a corregir |
| `npm run linter` | Para que Eslint identifique los errores del código |
| `npm run linter-fix` | Para que Eslint corrija los errores identificados con el comando anterior |
