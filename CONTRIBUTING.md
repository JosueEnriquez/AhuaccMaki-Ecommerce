# Contribuyendo a Ahuacc Maki Ecommerce

El siguiente es un conjunto de pautas para contribuir a Ahuacc Maki Ecommerce. Use su mejor juicio y siéntase libre de proponer cambios a este documento en un pull request.

#### Tabla de contenido

[Guía de estilos](#guía-de-estilos)
  * [Indentación y formato del código](#indentación-y-formato-del-código)
  * [Nombramiento de las ramas](#nombramiento-de-las-ramas)
  * [Mensajes de Commits](#mensajes-de-commits)
  * [Guía de estilo de Css](#guía-de-estilo-de-css)
  * [Guía de estilo de JavaScript](#guía-de-estilo-de-javascript)

[Notas adicionales](#notas-adicionales)
  * [Recomendaciones](#recomendaciones)

## Guía de estilos

### Indentación y formato del código

* Usar dos espacios como tabulación
* Todo el código JavaScript está alineado con [Prettier](https://prettier.io)

### Nombramiento de las ramas

Nombrar las ramas de forma corta y descriptiva, permite a sus colaboradores ver el trabajo en curso de un vistazo. 
Por ejemplo :
* `increase-test-timeout`
* `add-code-of-conduct`

### Mensajes de Commits

* Use el tiempo presente ("Agregar función" no "Función agregada")
* Use el estado de ánimo imperativo ("Mover el cursor a..." no "Mueve el cursor a...")
* Considera comenzar el mensaje del commit con un emoji aplicable:
  * 🎨 `:art:` al agregar html o css al código
  * ⭐ `:star:` al agregar funcionalidades código
  * 🚀 `:rocket:` al hacer merge
  * 📝 `:memo:` al escribir documentación
  * 🐛 `:bug:` al corregir un error
  * 🔥 `:fire:` al eliminar código o archivos

### Guía de estilo de Css

* La única hoja de estilo que se agrega al html es `index.html`

* Dentro de index.css no se agregan los estilos, solo las  `variables` y los  `@import` de otras hojas de estilos

* Por cada página del WebSite, se crea un solo archivo `.css` que sé importa a `index.css`

* Los archivos `.css` se nombran siguiendo la siguiente estructura:
  ```
    St = Store
    Db = Dashboard
  ```
  * `St-nombredelapagina.css`
  * `Db-nombredelapagina.css`

* Se utiliza [BEM](https://en.bem.info/methodology/quick-start/) para el nombramiento de las clases

* Dentro de los archivos `.css` se separa los estilos de cada parte
    de la página utilizando la siguiente estructura:
    ```
      /*!---------------Área---------------*/
      /*!---------------Área-Sección---------------*/

      Ejemplos:

      /*!---------------Main---------------*/
      /*!---------------Main-Hero---------------*/ 
      /*!---------------Footer----------------*/
      /*!---------------Footer-Contact----------------*/
      /*!---------------Footer-Adress----------------*/

### Guía de estilo de JavaScript

* El archivo `index.js` es el único script que se agrega al `html`

* Dentro de `index.js` solo se agrega los import de las `funciones`, las variables que les pasaremos como `parámetros` y las `ejecuciones de las funciones`. Ejemplo :
  ```js
    import { toogleMenu } from "./togle-menu.js";

    cosnt menu = document.getElementById(menuId);
    cosnt buttonMenu = document.getElementById(buttonMenuId);
    toogleMenu( menu, buttonMenu );
  ```
* Para evitar que los `scripts de otras páginas` se ejecuten dentro de la página de carga y nos provoque errores, se crea `validaciones` dentro de `index.js` por cada página, las cuales verifican la `ruta de la página`. Ejemplo :
  ```js
    if (
      window.location.pathname === "/index.html" ||
      window.location.pathname === "AhuaccMaki-Ecommerce"
    ) {
      import { toogleMenu } from "./togle-menu.js";
        
      cosnt menu = document.getElementById(menuId);
      cosnt buttonMenu = document.getElementById(buttonMenuId);

      toogleMenu( menu, buttonMenu );
    };
  ```
* El nombre de los `archivos.js` especifica su función.
Ejemplo:

  *  `toogle-menu.js`
  *  `slide.js`
  *  `change-title.js`

## Notas adicionales

### Recomendaciones
Puede usar [Better Comments](https://marketplace.visualstudio.com/items?itemName=aaron-bond.better-comments) para obtener una mejor vista de los separadores de sección