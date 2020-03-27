<h1 align="center">Apuntes de CSS</h2>

# Para dominar CSS debemos entender
+ Selectores
+ Especifidad
+ Herencia
+ Cascada

# 1. Introducción 

## 1.1. CSS tiene módulos
+ media queries
+ selectores
+ tranforms
+ etc.

## 1.2. Conectar HTML y CSS

Los estilos CSS se específican en la etiqueta **head** para que carguen al inicio.

```html
<head>
  <link rel="stylesheet" src="#">
</head>
```


Si específicamos múltples archivos CSS mediante `<link>` o `@import` se puede producir una demora en la renderización debido a que se debe realizar una petición por cada archivo.

Con **SASS** podemos importar múltiples archivos **.scss**. Al pasar a producción todos estos archivos son compilados en un único archivo **CSS**.

## 1.3. Sintaxis de CSS

Selectores, reglas, declaraciones y mucho más: [Workflower](http://apps.workflower.fi/vocabs/css/es).

## 1.4. Variables de CSS

```css
:root{
  --primary: blue;
  --secondary: red;
}
body{ 
  background: var(--primary);
  color: var(--secondary);
}
```

# 2. Selectores

+ Para identificar elementos a los que se le aplicarán los estilos.
+ Todos los selectores: [CCS4 Selectors](https://css4-selectors.com/selectors/).
+ Tipos (agrupación didáctica creada por Álvaro de EDTeam) 
  + Sencillos
  + Compuestos
  + Atributos

## 2.1. Selectores sencillos

## Selector de tipo

```css
body{...}
h1{...}
p{...}
```
## Selector de clase
Es lo que más utilizaremos.
```css
.myclass{...}
```

```html
<p class="myclass"></p>
```

Clases reutilizables que nos permiten disminuir la cantidad de líneas de código css (declaraciones reutilizables).
```css
.bold{
  font-weight: bold;
}
.center{
  text-align: center;
}
```
## Selector de ID

+ No reutilizables.
+ No se recomienda usar en CSS.
```css
#description{...}
```
```html
<div id="description">
  ...
</div>
```

## Selector universal

+ Afecta a todos los elementos del DOM.

```css
*{
  color: red;
}
ul *{
  color: blue;
}
```

## 2.2. Selectores compuestos
Regla aplicada a más de un selector.

### Selectores agrupados 
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


### Selectores descendientes
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


### Selector hijo directo
```css
.padre > .hijo{
  ...
}
```

### Selector hermano siguiente
```css
.hermano1 + .hermano2{
  ...
}
```

### Selector hermanos siguientes
Se aplica a todos los hermanos siguientes.
```css
.hermano-mayor ~ .hermano{
  ...
}
```

## 2.3. Selectores de atributo...
