# Clase Día 5

Es recomendable, que todos los colores y tipos de letras en css ponerlas en variables

## Transiciones, transformaciones y animaciones

### Trasnformaciones

Tenemos transformaciones que nos permiten permiten modificar las coordenadas en las que se encuentra un elemento. Y podemos trasladarlos en el eje x y el eje y.

Los elementos pueden ser:

- Trasladados: translate, translateX, translateY.
- Rotados: rotate, rotateX, rotateY.
- Escalados: scale, scaleX, scaleY.
- Distorsionados: skew, skewX, skewY.

**Ejemplo:** Podemos ver este ejemplo en `día-5\transformaciones.html`

En principio en este cuadrado una de las cosas que podemos hacer es usar la propiedad `trasnform`
El movimiento se hace desde la esquina superior isquierda.

#### Translate
Tenemos tambien el translateX y el translateY.

Ademas de trasladarlo otra cosa que podemos hacer es rotarlo.

#### Rotate
Podemos tambien rotarlo
```css
 transform: rotate(30deg);
```

#### scale
Ademas de rotarlo podemos cambiale el tamaño.

#### Skew
Ademas tambien lo podemos deformar en grados


>No podemos poner trasnform en diferentes lineas con todas estas funciones ya que la ultima linea estaria pisando a la anterior.

#### Aplicar mas de una funcione de trasnformaciòn
Si se quiere aplicar mas de una lo que se debe hacer es aplicar una detras de otra en paralelo:
```css
transform: translate(100px, 150px) rotate(30deg) scale(1.2,1.3) skew(-10deg);
```

Porque se cuenta esto del trasnform.

### Intentar centrado vertical

El centrado vertical es un poco complicado. Una soluciòn que se puede usar es el transform directamente.

Antes para poder centrar verticalmente era:
Se usaba una poiciòn absoluta, 
```css
position: absolute;
```
Lo que hace al ponerlo en uan posicion absoluta es sacarlo del flujo de renderizado y automaticamente como el unico padre que tiene. Luego le damos top y left al 50%. Pero vemos que no es lo que queremos porque lo que queremos es que estè en el centro de la pantalla.

Bueno ahora lo que sabes donde y cual es el centro de la pantalla. Sabiendo que este el el centro de la pantalla ahora puedo usar trasnform. 

```css
.container{
    ...
    position: absolute;
    left: 50%;
    top: 50%;

    transform: translate(-50%, -50%);
}
```

Pero la forma de hacerlo ahora es mas facil usando flexbox. 
Lo que quiero o debo hacer es que se mueva o se centre solo el formulario y que el contenedor ocupe todo el espacio.

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}
```

Esto me sirve para centrarlo horizontalmente, Pero debo recordar que para centrarlo verticalmente debe tener una altura. 
Necesito que tenga una altura para poder centrar en algun sitio, sino el div el container se autoajusta para ocupar el alto que le quepa al contenido, en este caso deberia establecer un alto para que nuestro contenedor este centrado.

El flex nos ha mejorado bastante la forma de centrar elementos segùn el padre.


### Cambiar el color de las secciones en el CV.

Si queremos dar un background a secciones de forma intercalada, nos encontramos con el problema que a la seccion al darle un ancho fijo o predefinido, no se va a pintar toda la pagina sino que le pondra margenes.

Como podemos solucionar esto? Bueno esto no lo voy a poder arreglar con un solo div. Podria usar 2 divs, uno externo que se extienda por todo el ancho de la pagina, y el interno para el contenido.

Lo que tengo que hacer es saltarme el ancho predefinido o establecido:

```css
section.inverted {
    background-color: var(--text-color);
    color: var(--bg-color);
    margin-right: calc(50% - 50vw);
    margin-left: calc(50% - 50vw); 
}
```

Pero luego necesito recuperar el ancho maximo del contenido de mi seccion y esto lo puedo hacer con un segundo div.

Lo que hago es crear un nuevo div con clase .centered que englobe el contenido de la seccion y aplicar un centrado horizontal partiendo de mi ancho maximo.

```css
section .centered {
    max-width: var(--max-width);
    margin: 0 auto;
}
```

Despues de hacer esto nos damos cuenta que tenemos un desfase por el ancho de la barra de scroll. Tenemos que de alguna manera encontrar el ancho de la barra y agragarselo, en este caso le sumamos .6rems

```css
section.inverted {
    background-color: var(--text-color);
    color: var(--bg-color);
    margin-right: calc(50% - 50vw + .6rem);
    margin-left: calc(50% - 50vw + .6rem); 
}
```

## CSS Grid

ME quede en dia 5 , tiempo 1:38:15