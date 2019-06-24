# Clase día 2

## Controles de formulario: inputs y botones

    ```html
        <input type="" id="" name="">
    ``` 
- Permiten que el usuario interactue con nosotros, estos controles son los mas importantes.
- Sirven para permitir la entrada de datos por parte del usuario que nos visita.
- Existen muchos tipos diferentessegun el tipo de dato: `text`, `emanil`, `date`, `checkbox`, `color`.
- Cuando se define el tipo, añade una pequeña validación en el navegador, que el dato cumpel con los requisitos mínimos, que no permita el ngreso de caracteres no válidos, en este caso se suele poner la propiedad no-validate, porque se suele validar esto en javascript.
- Tipos especiales para botones submit/reset/buttom:
  - submit : para enviar el formulario
  - reset: vaciar el formulario
  - boton generico para capturar comportamiento.

- Los botones tiene su propia etiqueta:
    ```html
    <button type="submit|reset|button">
    ```

## Formularios: etiquetas pasivas
- ```<label for="">```: permite asignar una etiqueta a un control
- ```<fielset>```: agrupar controles, permite
- ```<legend>```: establece la etiqueta para un grupo de controles en un ```<fieldset>```

## Formularios: otros controles de entrada
- textarea
- select y option para seleccion entre un conjutno de opciones
- progress para mostrar el progreso de una tarea.
- meter, medida dentro de un rango conocido.

- En el metodo de envio en la propiedad `enctype` el mas habitual es `text/plain`, pero en caso de tener que enviar archivos se usa otro.
- La validacion en los formularios se deben hacer en todas las capas. En el caso de html5 ya valida formulario antes de enviar el formulario.

- ay otro tipo de campos de formulario
- Existen varios metodos para enviar un formulario
   ```html
   <form action="" method="post"></form>
   ```
- para el tema de contraseñas, hay que usar https.
  https: es la manera en que se envia la información a travez de la red, es decir encripta la información para enviar a travez de la red.

- Cuando usar un post o un get.
  - El `get` es para hacer peticiones, que al principio no hace cambio de datos o modificaciones. El get es limitado
  - El `post` es cuando se hace cambios en el otro lado o se envian.

- Si se va a pasar ficheros, siempre post. Hay que usar el `enctype`, `enctype="multipart/form-data"`, esto codifica el envío de una manera específica, y cambia la manera que se gestiona la información en el backend.
  - Ejem, en texto plano los espacios se convierten en +.

## Elementos interactivos: 

### details / summary
Implementa de forma nativa un texto desplegable.

### dialog;
Crea una ventana modal o popup, aunque la funcionalidad debe agregarse por CSS o JS.

## Metadatos

### Atributos estandar: id, class

###  Microformatos (http://microformats.org): class
  - PErmiten dentro del html, metadatos que nos dan información. por ejemplo la clase específica `h-card`, y lo parsean en json. 
  - Se hacen estas cosas porque ya no solo personas pasan por la web sino, spiders, motores de busqueda, o sistemas para extraer información de forma automática. 
  - Permite que extraiga información de mi página de forma facil
- 
### Microdata (https://schema.org/docs/gs.html): item
    - Esto usa item-algo
  - ```html
    <div itemscope itemtype="https://schema.org/Movie">
        <h1 itemprop="name">Avatar</h1>
        <span>Director: <span itemprop="director">James Cameron</span> (born August)</span>
        <span itemprop="genre">Science fiction</span>
        <a href="../movie/avatar-theatrical-trailer.html" itemprop="trailer">Trailer</a>
    </div>
    ```
    - Ayuda a las paginas que quieren parsear nuestras páginas usando estas tarjetas.
### Atributos personalizados: data-...
    - Tambien extraen metadatos con los atributos `data-...` como bootstrap lo hace

### WAI-ARIA (https://www.w3.org/WAI/standards-guidelines/aria)
    - Web Accessibility Initiative 
    - Accesible Rich Internet Applications
    - Nos da estandares para que nuestra página sea mucho mas accesible.
    - Hay un mundos mas haya del html standar, hay extensiones de html

## Introducción a las hojas de estilo con CSS3

- CSS, cascadins style sheets, hojas de estilo en cascada.
- Lenguaje apra definir la presentacion de un documento estructurado escrito en un lenguaje de marcado.
- Diseñado para permitir la separación entre el contenido del documento y la forma de presentarlo.

### ¿Como usar CSS?

- Estilos en línea, mediante el atributo `style.
- Estilos independientes. Uso de selectores:
  - Embebidos con la etiqueta <style>
  - En ficheros CSS independientes
    ```html
    <link rel="stylesheet" href="./styles.css">
    ```

### Sintaxis: selectores, propiedades y directivas
Las directivas o reglas, permiten importar cosas externas
```css
@import url('https://...');
h1 {

}
```
### herramientas y referencias
- MDN: 
- Can I Use: le puedo preguntar por cualquier propiedad de CSS o HTML5 y nos dará información sobre el soporte en los navegadores de la caracteristica que se consulta.
  - PAra cuando en algun navegador que no tiene soporte existen los `polyfill` que son como hacks para poder usar las propiedades no soportadas.
- Navegador: inspector

### Selectores básicos

- selectores multiples
  ```css
  h1, h2, h3 { } //estilos a multiples selectectores

  div p {} //Descendientes de cualquier nivel, calquier p que este dentro de un div

  div > p {} // "Hijos" directos, solo al hijo directo (hijos inmediatos)

  div + p {} // Hermanos adyacentes (inmediatos)

  div ~ p {} // Hermanis en general
  ```

### Pseudo-elementos y Pseudo-clases

* Pseudoelementos: elementos definidos desde CSS
  -  ::first-letter
  -  ::first-line
  -  ::before {content=""}
  -  ::after {content=""}

* Pseudoclases: clases aplicadas dinámicamente a elementos reales de HTML en funcion de sus estado. 
  -  :link, :visited, :active, :focus, :hove, :target, :lang()
  -  :nth-child(n), :first-child, last-child, only-child
  -  :nth-of-type(n), :first-of-type, :last-of-type,
  -  :only-of-type, :not()

### Aplicación de múltiples estilos

* Herencia
  - Propiedades qe se heredan en los elementos hijos `font-family`, `color...` => afectan al contenido.
  - Propiedades que no se heredan `margin`, `padding`, `border...` => afectan al contenedor  

* Cascada
  - agente de usuario: por dfecto/ definidos por el usuario
  - bloques de CSS: externos / embebidos
  - Estilos en línea

### Especificidad

- Hay un orden de prioridad (menor a mayor especificidad) para aplicar clases o estilos.
  - Selectores de tipo (p, h1) elemento y pseudoelementos (::before, ::after).
  - Selectores de clase (ejempo), selectores de atributo ([type="text"]) y pseudo-clases (:hover)
  - Selectores ID (#ejemplo)
Los estilos inline (style="color: darkorange") tienen prioridad sobre los externos.

Hay una calculadora de especificidad. https://specificity.keegan.st/

### Unidades de medida

- Unidades Absolutas:
- Unidades Relativas: em, ex, vw, vh, %, rem

### Variables. Uso de calc()

- Variables definidas globalmente:

```css
:root {
    --color-principal: #06c;
}
```
- Se usan mediante la funcion var()

```css
#foo h1 {
    color: var(--color-principal);
}
```

- La funcion calc() opera con variables y numeros

```css
.container {
    --separacion: 20;
    margin-top: calc(var(--separacion) * 2px);
}
```

### Propidades básicas

### Tiporafía
- Podemos incluirlas nuevas fuentes de varias formas:
  - MEdiante la propiedad @font-face
```css
@font-face {
    fons-family: mi fuente;s
    src: url();
}

```

- Importandola de webs como Google Fonts

```css
@import url();
<link href='' type='text/css'>
```

### Propiedades para fuentes
- font-style
- font-variant
- font-weight
- font-size
- font-family
- font

### OTras propiedades
- text-decoration, text-tranform
- line-height, letter-spacing, word-spacng
- text

### Colores

* Sistemas de colores
  *   Nombres
  *   rgb() -red, green, blue
  *   hexadecimal (#)
  *   hsl()
  *   hue°(matiz), saturation%
  
### Degradados

### Sombras
- Sombras de caja: box-shadow
- Sombras de texto: text-shadow

## Backgrounds: imágenes y patrones para el fondo

- background-image: url()
- background-repeat: no-repeat;

### Modelo de caja en CSS. Propiedades y usos

- Contenido
- Espaciado interno (padding)
- Borde
- Imagen de fondo
- Color de fondo
- Margen

### Display y posicionamiento

### Display. Opciones básicas

- display: block
- display: inline
- display: inline-block
- display: none


### Posicionamiento
La propiedad `position` nos permite crear estructuras más complejas en nuestros diseños.
Puede tomar los valores:
- static (por defecto): sin posicionamiento específico, el navegador decide.
- relative: se posiciona como static y luego se desplaza, pero reservando el hueco donde estaba.
- absolute: referencia al ancestro más cecarcano (no static), 
- fixed: variante del absoluto. Su posición es inamovible.

### Cambios del flujo estático
- Float: left/right
- Clear: left / right / both

- Overlow: hidden / auto