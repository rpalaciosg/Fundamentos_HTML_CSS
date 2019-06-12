# Clase 1 (10.06.2019)

## Introducción a la Web

Navegador - Peticion (Request) - Servidor Web - Respuesta (Response) - Navegador

![Como funciona la Web](Imagenes_Clase1/Como_funciona_la_web.png)

## Backend

## FrontEnd|
* Tecnoloias Básicas
- Http : Protocolo de transferencia de información.
- HMLT5 : Estrcutura y Contenido
- CSS3 : diseño y animación
- JS: Interactividad


## Herramientas

- Navegadores + developer Tools
- Editores de código: Visual Studio Code
- Git : Control de Versiones
- Browsersync: Probar páinas desde un servidor web local para desarrollo, y permite recargar automaticamente y ver en varios dispotivos, se necesita instalar node.js

## Introducción al lenguaje HTML5 
- HTML: Hyper Text Markup Languaje
  - Historia de HMTL
- MArcado: etqieutas y atributos
  - Etiqueta doble: apertura, contenido y cierre, tiene atributo a los que se le asigana un valor
  - Etiqueta sencilla:
- Comentarios : <!-- Esto es un comentario-->
  
- Estructura Principal

- VisualStudio Code
- Emmet
- Browser-sync
- configuración autoguardado VSCode
###  <head>
-  Metadatos:

Estas 2 primeros meta's debe siempre ser las primeras.
```html
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta http-equiv="Window-Target" content="_value">
```
Estos son los metas mas importantes que deberian ir en el head.

Hay una página [htmlhead](https://htmlhead.dev/) el cual es una guía de todo lo que puede ir en la cabecera o head de html, las cosas mínimas, como generar los links, etc 

Estos metadatos son muy importantes, ya que sirven para el SEO, que usan los spiders de los buscadores para categorizar el sitio.

Ademas en el head pueden ir Inclusion de archivos externos:
```html
<link rel="stylesheet" href="./styles.css">
```
- Estilos embebidos o programación en javascript
- Referencias de etiqueta base, para que todos los enlaces partan de un lugar específico o una página específica.

## HTML5
Lenguaje de etiquetas y teneos una clasificacion de etiquetas, dependiendo de la utilidad que tiene

- Matadatos
- Flujo, es todo
- Secciones, se refieren a bloques semanticos
- Frasin Content, equivalen a los elementos que van en linea o dentro de una linea de texto.
- Incrustación, podemos inscrustar fotos, videos.
- Interactividad, son los elementos que tiene que ver con formularios, o tambien habalr de los controles de audio o video.

## Secciones

Plantear html semántico
- header, cabecera de paina o seccion
- nav, contiene enlaces de navegacion
- main, contenido principal o mas importante del documento
- section, define una seccion independiente
- aside, poca relacion con el resto del contenido.
- footer, pie de pagona o de seccion
- address, información del contacto
- h1..h6, elemento cabecera (título)

## Agrupacion de contenido
- PArrafos: p, pre, blockquote
- Listas:
  - Ordenadas: ol / li
  - No numeradas: ul / li
  - Descriptivas: dl / dt / dd
- Bloques: main, div