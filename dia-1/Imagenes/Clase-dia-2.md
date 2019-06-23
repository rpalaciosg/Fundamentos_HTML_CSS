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
