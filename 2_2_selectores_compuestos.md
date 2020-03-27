<h1 align="center">Selectores compuestos</h1>

Regla aplicada a más de un selector.

# Selectores agrupados 
Se aplica a todos.
```css
a, b{
  ...
}
```
Para facilitar la lectura:
```css
a,
b {
  ...
}
```


# Selectores descendientes
Espacio o salto de línea indica descendiente
```css
.list
.list-item{
    color: red;
}
```
```html
<ul class="list">
  <li class="list-item">item 1</li>
  <li class="list-item">item 2</li>
</ul>
```
+ La mayoría de las veces no son necesarios los selectores descendientes. En el caso anterior `.list` no es necesario para aplicar los estilos a los items.
+ Se recomienda no tener mas de 2 niveles de descendencia.


# Selector hijo directo
```css
.padre > .hijo{
  ...
}
```

# Selector hermano siguiente
```css
.hermano1 + .hermano2{
  ...
}
```

# Selector hermanos siguientes
Se aplica a todos los hermanos siguientes.
```css
.hermano-mayor ~ .hermano{
  ...
}
```

# Ejercicios

Cómo hacemos que los subtítulos tengan el mismo color que los títulos sin crear una clase diferente para cada subtítulo.
```html
<h1 class="title-1">Título 1</h1>
<p class="subtitle">subtítulo<p>

<h1 class="title-2">Título 2</h1>
<p class="subtitle">subtítulo<p>
```

```css
.title-1{ color: red }
.title-2{ color: blue }
```
## Respuesta

Aplicando `selector hermano directo` creamos nuevos conjuntos de reglas (no creamos nuevas clases).
```css
.title-1 + .subtitle{ color: red }
.title-2 + .subtitle { color: blue }
```
Podríamos mejorar el código usando variables:
```css
:root{
  --primary: red;
  --secondary: blue;
}
.title-1 + .subtitle{ color: var(--primary) }
.title-2 + .subtitle { color: var(--secondary) }
```