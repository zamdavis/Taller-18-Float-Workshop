# Taller de Float en CSS

![Resultado](/images/result.png)

Autor: Eduardo Oviedo Blanco

Para usar este taller efectivamente, clone el código en su ambiente local.
```
git clone https://github.com/edWAR6/CSS-Float-Workshop.git
```
Si desea subir el taller en su repositorio personal.
Cree un repositorio en su perfil, luego:
```
git remote set-url origin https://github.com/<su usuario>/CSS-Float-Workshop.git
```

> El nombre del repositorio puede cambiar. Siga las instrucciones y guarde sus cambios.

## Instrucciones

1. Al elemento con la clase `.box` agréguele la siguiente propiedad.
```
.box {
  ...
  float: left;
  margin-right: 15px;
}
```

2. Note y discuta lo que cambió en el resultado.

3. Asigne la clase `.special` al primer párrafo.
```
<p class="special">
  ...
```
```
.special {
  background-color: rgb(79,185,227);
  padding: 10px;
  color: #fff;
}
```

4. Cambie el tipo de margen del `.box` de `margin-rigth` a `margin`.
```
.box {
  ...
  margin: 15px;
}
```

5. Para detener el efecto que *float* causa en los elementos siguientes, puede cancelarlo de la siguiente manera. Agregue la clase `.cleared` al segundo párrafo.
```
<p class="cleared">
  ...
```
```
.cleared {
  clear: left;
}
```

6. Cree un elemento padre que encierre al div y al primer párrafo.
```
<div class="wrapper">
  <div class="box">Float</div>

  <p>Lorem ipsum...</p>
</div>
```
```
.wrapper {
  background-color: rgb(79,185,227);
  padding: 10px;
  color: #fff;
}
```

7. Comente la propiedad `clear`, agregada anteriormente.
```
.cleared {
  /* clear: left; */
}
```

> Note como el problema es la falta de control sobre qué elementos son movidos adyacentes al elemento flotante. Tanto así que hay un *overflow* en el elemento `.wrapper`.
> Esto se puede solucionar de varias maneras.

### clearfix

- Agregue el siguiente selector con la propiedad `clear`.
```
.wrapper::after {
  content: "";
  clear: both;
  display: block;
}
```

### overflow

- Remueva el clearfix anterior y agregue la propiedad `overflow` al `.wrapper`.
```
.wrapper {
  ...
  overflow: auto;
}
```

> Funciona, pero hay que tener cuidado ya que en ocasiones pueden aparecer las barras de *scroll*.

### display: flow-root

- La manera nueva y moderna de solucionar este problema.
```
.wrapper {
  ...
  display: flow-root;
}
```

> No genera efectos secundarios.

## Conclusión

En ocasiones se encuentran trucos como los anteriores que solucionan problemas, pero casi siempre tienen efectos secundarios.

Se recomienda estar al tanto de nuevas actualizaciones de CSS ya que en muchos casos estos problemas son resueltos.

En este caso particular se puede ver la [compatibilidad del `flow-root`](https://developer.mozilla.org/en-US/docs/Web/CSS/display#browser_compatibility) según *Mozilla*.
