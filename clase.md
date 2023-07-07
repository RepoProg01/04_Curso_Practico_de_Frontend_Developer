## Variables en CSS

En CSS, llamamos variables a las propiedades personalizadas.
Contienen valores específicos que se pueden reutilizar muchas veces en un documento.

Se establecen mediante la notación de dos guiones
```css
--nombre-variable: valor;
```
Se acceden mediante la función var()
```css
propiedad: var(--nombre-variable);
```
Normalmente las declaramos dentro del selector :root para que su alcance (scope) sea global.

Nuestro proyecto quedaría así:
```css
:root {
            --black:#000000;
            --white: #FFFFFF;
            --very-light-pink: #C7C7C7;
            --text-input-field: #F7F7F7;
            --dark: #232830;
            --hospital-green: #ACD9B2;
        }
```

También puedes nombrar a tus variables según su función.
Ejemplos: --background-color, --primary-color, etcétera.

## Fonts
Buscaremos las fuentes propuestas por diseño en Google fonts
Colocamos los links dentro de la etiqueta head del HTML
```html
<head>
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
   <link href="https://fonts.googleapis.com/css2?family=Quicksand:wght@300;500;700&display=swap" rel="stylesheet">
</head>
```
Dentro de la etiqueta style le decimos a CSS que la implemente
```css
body {
            font-family: 'Quicksand', sans-serif;
        }
```

## Abreviación emmet:
Son muy útiles y rápidas al momento de crear estructuras complejas, por ejemplo la siguiente abreviatura:

>div.login>div.form-container>img+h1+p+form>(label+input#password.input.input-password)*2

El resultado sera: 

```html
<div class="login">
        <div class="form-container">
            <img src="" alt="">
            <h1></h1>
            <p></p>
            <form action="">
                <label for=""></label>
                <input type="text" id="password" class="input input-password">
                <label for=""></label>
                <input type="text" id="password" class="input input-password">
            </form>
        </div>
    </div>
```
## Media query
puede usarse directamente en el css :
```css
@media(max-width:640px){
    .login_logo{
        display: block;
    }
}
```
O en diferentes archivos en el head del HTML :
```css
    <!-- style mobile firts -->
    <link rel="stylesheet" href="./CSS/mobile.css">

    <!-- media querys -->
    <link media="screen and (min-width: 640px)" rel="stylesheet" href="./CSS/tablet.css">
    
    <link media="screen and (min-width: 1080px)" rel="stylesheet" href="./CSS/desktop.css">
```
Notas varias:

## required
Si no se llena esa ventana no se puede continuar
```html
    <div class="container_row container_row-customSearch">
        <label class="container_label container_label-searchByNum" for="number">Numero</label>
        <input name="f_number" class="container_input container_input-searchByNum" id="number" type="number" placeholder="unit num" required>
    </div>
```
## list-style y text-decoration
```css
    .ul{
        list-style: none;
    }
    .li{
        text-decoration: none;
    }
```
## Grid
Diferentes valores para la linea grid-template-columns o rows
```css
.container{
    display: grid;
    grid-template-columns: repeat(2, auto);
    grid-template-columns: repeat(2, 1fr);
    grid-template-columns: 1fr 1fr;
    grid-template-columns: 1fr auto;
    grid-template-columns: repeat(auto-fill,140px);
}
```
## place-content: center
Centra en horizontal y vertical 
```css
.container{
    display: grid;
place-content: center;
}
```