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
   
- **[2-2 Animaciones](#2-2-animaciones)**
   - [Gradiente](#gradiente)
   - [Transformaciones](#transformaciones)
   - [Keyframes](#keyframes)
   - [PlugIn WOW](#plugin-wow)

- **[2-3 SEO](#2-3-seo)**
   - [Archivos HTML](#archivos-html)
   - [Headers](#headers)
   - [Robots](#robots)
   - [Sitemap](#sitemap)



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

Mixin para dar formato a las imágenes

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

Condicionales que se encuentran dentro de un Mixin para seleccionar el formato de grid a utilizar.

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

### Gradiente

```bash

Se utiliza para dar degrades asl fondo de las recetas.

.gradiente{
    @include gradient-y($bkColor4,$bkColor2);
}
   
```



### Transformaciones


Se presentan esto 4 tipos de transformación:

Se utiliza el efecto **Translate** en las recetas.

```bash

@mixin translate-y($right,$up) {
    transform: translate($right,$up);
    transition: all 1s;
 }

.gradiente:hover{
    @include translate-y($tx,$ty);
}
```

**Rotate** en el logo Superior

```bash

.rotate:hover{
    transform: rotateZ($deg);
    transition: all 1s;
}
```

**Scale** en acciones de recetas para que cuando se acerque el mouse se agrande.

```bash

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

**Skew** en iconos de redes en footer.

```bash

   .miniatura:hover{
    transform: skew($skew);
    transition: all 1s;
}

```


### Keyframes

**Keyframe**  que se utiliza para header tipo 2

```bash
@keyframes gradienDiv{
0%{background-color: $bkColor1};
25%{background-color: $bkColor2};
50%{background-color: $bkColor2};
75%{background-color: $bkColor3};
100%{background-color: $bkColor4};
}
```

**Keyframe** que se utiliza para header tipo 3

```bash

// keyframe para h3
@keyframes textOpacity{
from {opacity: 0.3} to {opacity: 1}
		} 

```

### PlugIn WOW

Instalé el PlugIn para animaciones [WOW.js](https://wowjs.uk/) y para su uso mi guía fué [Animate.css](https://animate.style/)

Para su instalación me guié con el [Readme de Wow](https://github.com/graingert/wow)  

Para poder trabajar en primera instancia se instaló  vía NPM. 


```bash

npm install wow.js
   
```

Se cargó el CSS **animate.css** de Wow y se referenció desde todos los HTML

```bash

<link rel="stylesheet" href="../css/animate.css">
   
```

y se cargo el acceso al JavaScript en todos los HTML

```bash

 <script src="../js/wow.min.js"></script>
    <script> 
    new WOW().init();
    </script>
   
```

Respecto al uso, se utilizo principalmente en la  [Página 404](https://github.com/franciscogelabert/PreEntrega3GelabertFrancisco/blob/master/pages/404.html) en 

```bash

 <div class="card gradiente wow bounceIn">
          <h1>404 Opss... </h1> 
        </div>
        <div class="card gradiente wow bounceInRight">

	<h2>Lo sentimos esta receta no salió bien. 
			  <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-mood-sad-squint miniatura" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                <path d="M12 12m-9 0a9 9 0 1 0 18 0a9 9 0 1 0 -18 0"></path>
                <path d="M14.5 16.05a3.5 3.5 0 0 0 -5 0"></path>
                <path d="M8.5 11.5l1.5 -1.5l-1.5 -1.5"></path>
                <path d="M15.5 11.5l-1.5 -1.5l1.5 -1.5"></path>
             </svg>
	</h2>
 </div>
   
```

### 2-3-SEO

### Archivos HTML

Se agregan nuevas metas en todos los archivos HTML 

```bash

 <meta name="description" content="Te invitamos a compartir y aprender nuevas recetas. Existe un gran Chef en cada casa con ganas de compartir nuevas ideas, sabores, risas y momentos">
   <meta name="author" content="Francisco Gelabert">
   <meta name="keywords" content="red social de recetas, recetas, comida, chef, restaurant, cocinera, cocinero">
   <meta name="copyright" content="Foodier S.A. 2023">
   <meta name="robots" content="index,follow">
   
 ```

### Headers

Se Actualizan los headers (h1), colocando información mas acorde a la info que se quiere transmitir

```bash
Ejemplo de

 <h1>Bienvenido a Foodier</h1>
 
 a 
 
 <h1>Bienvenido a Foodier tu red social de recetas y momentos</h1>
   
 ```

### Robots

Solo a los efectos de probar su utilización se carga el archivo robots.txt

```bash

User-agent: *
Disallow: /docs

Sitemap: https://franciscogelabert.github.io/PreEntrega3GelabertFrancisco/
   
 ```


### Sitemap

Solo a los efectos de probar su utilización se genera y carga el archivo [sitemap.xml](https://github.com/franciscogelabert/PreEntrega3GelabertFrancisco/blob/master/sitemap.xml)

El mismo se genera con la página [www.xml-sitemaps.com](https://www.xml-sitemaps.com)



## 3.Detalles a tener en cuenta en esta entrega.

Al igual que en la entrega anterior se dejan dos versiones de pa pantalla "visitar perfil", una que logra el comportamiento resposive con Boostrap y la otra con Grid.
Para acceder a la versión GRID de visitar perfil utilizar los accesos de la NAV/Header 
y para acceder a la versión Boostrap utilizar el acceso a Visitar perfil que se presenta en el footer en modo mobile.

