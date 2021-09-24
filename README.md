<div align="center">
    <img alt="nestjs-package-starter" width="250" height="auto" src="https://camo.githubusercontent.com/c704e8013883cc3a04c7657e656fe30be5b188145d759a6aaff441658c5ffae0/68747470733a2f2f6e6573746a732e636f6d2f696d672f6c6f676f5f746578742e737667" />
    <h3>NestJS Package Starter</h3>
</div>

<p align="center">
    <img src="https://img.shields.io/static/v1.svg?style=flat&label=Node&message=v14.15.4&labelColor=339933&color=757575&logoColor=FFFFFF&logo=Node.js" alt="Node.js"/>
    <img src="https://img.shields.io/static/v1.svg?style=flat&label=Npm&message=v6.14.10&labelColor=CB3837&logoColor=FFFFFF&color=757575&logo=npm" alt="Npm"/>
    <img src="https://img.shields.io/static/v1.svg?style=flat&label=NestJs&message=v8.0.6&labelColor=E0234E&logoColor=FFFFFF&color=757575&logo=Nestjs" alt="NestJs"/>
    <img alt="GitHub Workflow Status" src="https://github.com/rudemex/nestjs-package-starter/actions/workflows/master.yml/badge.svg?branch=master">
    <img alt="Codecov" src="https://img.shields.io/codecov/c/github/rudemex/nestjs-package-starter?logoColor=FFFFFF&logo=Codecov&labelColor=#F01F7A">
    <img src="https://sonarcloud.io/api/project_badges/measure?project=rudemex_nestjs-package-starter&metric=alert_status" alt="sonarcloud">
    <img alt="GitHub license" src="https://img.shields.io/github/license/rudemex/nestjs-package-starter?style=flat">
    <br/> 
</p>

## Glosario

- [📝 Requerimientos básicos](#basic-requirements)
- [🙌 Let's start](#lets-start)
- [🛠️ Instalar dependencias](#install-dependencies)
- [💻 Scripts](#scripts)
- [🔀 Workflows](#workflows)
- [📤 Commits](#commits)
- [📜 License MIT](license.md)

---

> 💬 Este repositorio cuenta con una configuración base para **GitHub Actions**, **Codecov** y **SonarCloud**, las cuales se pueden remover fácilmente del proyecto o bien, terminar de configurarlas para aprovechar al maximo las buenas prácticas.

<a name="basic-requirements"></a>

## 📝 Requerimientos básicos

- Node.js v14.15.4 or higher ([Download](https://nodejs.org/es/download/))
- NPM v6.14.10 or higher
- NestJS v8 or higher ([Documentación](https://nestjs.com/))

<a name="lets-start"></a>

## 🙌 Let's start

Con el botón **Use this template**, creamos un repositorio nuevo en nuestro **GitHub** copiando todos los archivos del
repositorio original, y luego hacemos un `git clone` del mismo.

También podés ejecutar el siguiente script cambiando el nombre de destino

```bash
git clone https://github.com/rudemex/nestjs-package-starter.git <nombre-de-destino>
```

Example:

```bash
git clone https://github.com/rudemex/nestjs-package-starter.git my-awesome-package
```

Una vez clonado el repositorio, tenemos que cambiar el `name` del archivo `package.json`, ya que este va a ser el nombre
del paquete a generar.

```json
{
  ...,
  -
  "name": "nestjs-package-starter",
  ...
  +
  "name": "my-awesome-package",
  ...
}
```

> 💬 También podés ajustar otras propiedades como el **author**, **description**, **keywords**, etc.

<a name="install-dependencies"></a>

## 🛠️ Instalar dependencias

Estando en la carpeta del proyecto, instalamos sus dependencias con el script.

```
 npm install
```

<a name="scripts"></a>

## 💻 Scripts

### Inicia los test con coverage

```
npm run test
```

### Eslintea el código

```
npm run lint
```

### Realiza el build del paquete

Los builds se hacen con una herramienta llamada `@pika/pack` que por debajo usa `rollup`, una vez que el build se
realizó, vas a encontrar el contenido generado en la carpeta `./pkg` que contiene los diferentes builds, hasta el
`package.json` con las referencias a los módulos generados.

Para probar localmente el paquete antes de publicarlo, podés utilizar el comando `npm link` estando dentro de la
carpeta `./pkg`, y luego linkearlo en tu proyecto para probarlo. [más info](https://medium.com/@AidThompsin/how-to-npm-link-to-a-local-version-of-your-dependency-84e82126667a)

```
npm run build
```

### Realiza el build del paquete y actualiza la version.

```
npm version <tag>
// npm version v1.2.3
```

### Publicar paquete

```
npm publish
```

### Build and Publish

Existen varias maneras para publicar el paquete en **npm**.

##### Sencilla y rápida

La manera más sencilla y rápida de publicar el paquete es ejecutar el siguiente script y luego ir dentro de la carpeta
`./pkg` previamente generada con el script de `build`.

```bash
npm run build
cd ./pkg
npm publish
```

> 💬 Podes reemplazar `npm publish` por `yarn publish`, y publicar el paquete tanto en **npm** como **yarn**

##### La manera más óptima

Consiste en ejecutar el script de `version` con el tag correspondiente a desplegar, siguiendo la
[sintaxis de versionado](https://docs.npmjs.com/about-semantic-versioning). Con esta forma, se actualiza automáticamente
la version del `package.json`, y solo queda pushear al repositorio los cambios generados.

```bash
npm version v1.0.1
cd ./pkg
npm publish
```

-

##### Automatizada

En la carpeta `.github/workflows` se encuentra los procesos automatizados para **GitHub Actions**, en esta se encuentra
el pipeline para el publish, el cual realiza todos los pasos correspondientes de manera automatizada para el buildeado,
publicación y versionado del repositorio con solo correr manualmente el action con la version a desplegar, pero para
poder utilizar este método, es importante configurar los workflows que se detalla a continuación.

<img src="./.readme-static/github-workflow-publish.png" width="350" alt="Workflow to publish" />

<a name="workflows"></a>

## 🔀 Workflows (Github Actions)

<a name="commits"></a>

## 📤 Commits

Para los mensajes de commits se toma como
referencia [`conventional commits`](https://www.conventionalcommits.org/en/v1.0.0-beta.4/#summary).

```
<type>[optional scope]: <description>

[optional body]

[optional footer]
```

- **type:** chore, docs, feat, fix, refactor (más comunes)
- **scope:** indica la página, componente, funcionalidad
- **description:** comienza en minúsculas y no debe superar los 72 caracteres.

---

<div align="center">
    <a href="mailto:mdelgado@tresdoce.com.ar" target="_blank" alt="Send an email">
        <img src="./.readme-static/logo-mex-red.svg" width="120" alt="Mex" />
    </a><br/>
    <p>Made with ❤</p>
</div>
