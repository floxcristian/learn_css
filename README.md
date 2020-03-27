<h1 align="center">Apuntes de CSS</h2>

Para dominar CSS debemos entender:
+ selectores
+ especifidad
+ herencia
+ cascada

# 1. Introducción 

## 1.1. CSS tiene módulos
+ media queries
+ selectores
+ tranforms
+ etc.

## 1.2. Conectar HTML y CSS

El CSS se específica en el **<head>** para que cargue al inicio.

Forma tradicional:
```html
<head>
  <link rel="stylesheet" src="#">
</head>
```
Si tenemos un par de líneas CSS:
```html
<head>
  <style>
    body { background: red }
  </style>
</head>
```

Si específicamos múltples archivos CSS mediante `<link>` o `@import` se puede producir una demora en la renderización debido a que se debe realizar una petición por cada archivo.

Con **SASS** podemos importar múltiples archivos **.scss** pero finalmente todos son compilados en un único archivo **CSS**.

## 1.3. Sintaxis de CSS

Selectores, reglas, declaraciones y mucho más: [Workflower](http://apps.workflower.fi/vocabs/css/es).

## 1.4. Variables de CSS

```css
:root{
  --primary: blue;
}
body{ 
  background: var(--primary);
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

## 2.2. Selectores compuestos

## 2.3. Selectores de atributo



