<h1 align="center">2.3. Selectores de atributo</h1>

Info en español: [MDN Web Docs](https://developer.mozilla.org/es/docs/Web/CSS/Selectores_atributo).

Se aplica a todos los elementos que tengan el atributo `lang`:
```css
[lang] {
  font-weight: bold;
}
```
## Contiene valor exacto
```css
/*[attr="value"]*/
[type="email"]{ border: 1px solid blue }
[type="submit"]{ border: 1px solid red }
```
Podemos anteponer el tipo de elemento para facilitar la lectura:
```css
input[type="submit"]{ border: 1px solid red }
```

## Empieza con
```css
/*[attr^="value"]*/
a[href^="/"] {
  background-color: gold;
}
```
```html
<a href="/list">List</a>
<a href="/item_detail">Details</a>
```
Tiene el valor value o empieza por value seguido de un guión `-`:
```css
/*[attr|=value]*/
div[lang|="zh"] {
  color: red;
}
```
```html
<div lang="zh-CN">世界您好！</div>
<div lang="zh-TW">世界您好！</div>
```

## Termina con
```css
/*[attr$="value"]*/
a[href$=".org"] {
  color: red;
}
```
```html
<a href="www.fundace.org">Go Fundace!</a>
<a href="www.homely.org">Go Homely!</a>
```

## Contiene
```css
/*[attr*="value"]*/
a[href*="files"] {
  background-color: silver;
}
```
```html
<a href="www.udcs.cl/files/13151235145.pdf">Open file</a>
<a href="www.udcs.cl/files/1321564.docx">Open another file</a>
```

Agregar una `i` antes del corchete de cierre hace que el valor sea comparado sin distinguir entre mayúsculas y minúsculas:
```css
/*[attr operator=value i]*/
a[href*="gooGLE" i] {
  color: cyan;
}
```
```html
<a href="https://www.google.com"></a>
```

Tiene por valor una lista de palabras separadas por espacios, una de las cuales es value:
```css
/*========[attr~=value]========*/
div[lang~="en-us"] {
  color: blue;
}
```
```html
<div lang="en-us en-gb en-au en-nz">Hello World!</div>
```



