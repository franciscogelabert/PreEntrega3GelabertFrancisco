# Foodier

*Preentrega 3 - Gelabert Francisco - Comisión 52150 Coderhouse*

## 01- Deploy 

https://franciscogelabert.github.io/PreEntrega3GelabertFrancisco/index.html


## 02- Descripción de la entrega 

En esta tercera entrega se pone el eje sobre los siguientes 3 temas, que se detallan a continuación:

- **[2-1 SASS](#2-1-sass)**

   - [Archivos](#archivos)
   - [Variables Globales](#variables-globales)
   - [Nesting](#nesting)
   - [Extend](#extend)
   - [Iteradores](#iteradores)
   - [Mixin](#mixin)
   - [Condicionales](#condicionales)
   
- [2-2 Animaciones](#2-2-animaciones)

- [2-3 SEO](#2-3-seo)



### 2-1-SASS

Para poder trabajar en primera instancia se instaló [Node.js y NPM](https://nodejs.org/es) y SASS


```bash
npm install sass
   
```

### Archivos 

```bash

Para trabajar con SASS se crearon 8 archivos SCSS:

_animate: para cargar todo lo relacionado a las animaciones
_commons: para todo el código común a todas las páginas
_footer: para todo lo relacionado al footer
_media: codigo para todo lo relacionado a los media query y Grid 
_mixin: código para la reutilización de las clases.
_nav:  para todo lo relacionado a la nav.
_vars: para administrar las variables globales que se van a utilizar.
boost: para ordenar e incluir todos los SCSS
   
```

A continuación se detallan algunos ejemplos del uso de SASS:

### Variables Globales 

```bash

Colores de los íconos

$colorLike:red;
$colorShare:green;
$colorEdit:black;
$colorDelete:black;
$colorView:black;
$colorComment:black;
   
```

### Nesting

```bash

Se utiliza para dar formato al menú footer.

ul{
    li{
        a{
            font-size: $fontSizeXL;
            color: $bkColor4;
            text-decoration: none;
            font-family: $mainFont;
            font-weight: 400;
            left: 150px;
            &:hover{
               @include nResalta($fontSizeXXL,$bkColor4,$bkColor0);
              }
        }
    }
}
   
```


### Extend

```bash

footOne se utiliza para dar formato al footer en mobile y extiende footTwo 
que es el footer que se utiliza en los demás dispositivos.

.footTwo {
    width: $maxwidth;
    text-align: center;
    background-color: $bkColor1;
    }

.footOne {
@extend .footTwo;
        background-color: $bkColor0;
        padding: 10px 10px;
        height: auto;
        top: 0;
        left: 0;
        display: flex;
        flex-direction: column;
        align-items: center;
    }
   
```
### Map

```bash

Se arma una tupla para darle color a las acciones de las recetas:

$iconColor:(
    'Like':$colorLike,
    'Share':$colorShare,
    'Edit':$colorEdit,
    'Delete':$colorDelete,
    'View':$colorView,
    'Comment':$colorComment,
);

```


### Iteradores

```bash

Se itera la tupla del punto anterior para dar formato a las clases de color.

@each $icon,$color in $iconColor {
    .color#{$icon} {
       color:$color;
       margin-left: 10px;
    }
    .color#{$icon}:hover {
        transform:scale($scale);
        transition: all 1s;
     }
  }

   
```

### Mixin

```bash

Mixin para dar formato a als imágenes

@mixin imagenes ($width,$height,$bRadius,$margin,$padding,$oFit,$tAlign){
    width: $width;
    height: $height;
    border-radius: $bRadius;
    margin: $margin;
    padding: $padding;
    object-fit: $oFit;
    align-items: $tAlign; 
}
   
```

### Condicionales

```bash

Condicionales que se encuentran dentro de in Mixin para seleccionar el formato de grid a utilizar.

@mixin mixGrid ($g,$fr){
    grid-template-columns: repeat($g,$fr);
    @if $g == 1 {
        grid-template-areas: $grid1;
      } @if $g == 2 {
        grid-template-areas: $grid2;
      }  @if $g == 4 {
        grid-template-areas: $grid4;
      } 
    }
   
```

### 2-2-Animaciones


### 2-3-SEO



## 3.Detalles a tener en cuenta en esta entrega.

Al igual que en la entrega anterior se dejan dos versiones de pa pantalla "visitar perfil", una que logra el comportamiento resposive con Boostrap y la otra con Grid.
Para acceder a la versión GRID de visitar perfil utilizar los accesos de la NAV/Header 
y para acceder a la versión Boostrap utilizar el acceso a Visitar perfil que se presenta en el footer en modo mobile.



