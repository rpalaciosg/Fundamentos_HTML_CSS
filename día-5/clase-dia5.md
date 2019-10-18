# Clase Día 5

## Transiciones, transformaciones y animaciones

### Trasnformaciones
Tenemos trasnformaicones que nos permiten permiten modificar las coordenadas en las que se encuentra un elemento. Y podemos trasladarlos en el eje x y el eje y.
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
}
```

Esto me sirve para centrarlo horizontalmente, Pero debo recordar que para centrarlo verticalmente debe tener una altura. 
Necesito que tenga una altura para poder centrar en algun sitio, sino el div el container se autoajusta para ocupar el alto que le quepa al contenido, en este caso deberia establecer un alto para que nuestro contenedor este centrado.

El flex nos ha mejorado bastante la forma de centrar elementos segùn el padre.