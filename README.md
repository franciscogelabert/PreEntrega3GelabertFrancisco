# Foodier

*Preentrega 3 - Gelabert Francisco - Comisión 52150 Coderhouse*

## 01- Deploy 

https://franciscogelabert.github.io/PreEntrega3GelabertFrancisco/index.html


## 02- Descripción de la entrega 

En esta tercera entrega se pone el eje sobre los siguientes 3 temas, que se detallan a continuación:

### 02-1 SASS

Para poder trabajar en primera instancia se instaló [Node.js y NPM](https://nodejs.org/es) y SASS


```bash
npm install sass
   
```
Para trabajar con SASS se crearon 8 archivos SCSS:

```bash

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
// colores de las acciones
$colorLike:red;
$colorShare:green;
$colorEdit:black;
$colorDelete:black;
$colorView:black;
$colorComment:black;
   
```

### Nesting

```bash

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
ToDo
   
```

### Mixin

```bash
ToDo
   
```
### Iteradores (for & each)

```bash
ToDo
   
```
### Condicionales

```bash
ToDo
   
```

### 02-2 Animaciones


## 02-3 SEO



## 3.Detalles a tener en cuenta en esta entrega.

Al igual que en la entrega anterior se dejan dos versiones de pa pantalla "visitar perfil", una que logra el comportamiento resposive con Boostrap y la otra con Grid.
Para acceder a la versión GRID de visitar perfil utilizar los accesos de la NAV/Header 
y para acceder a la versión Boostrap utilizar el acceso a Visitar perfil que se presenta en el footer en modo mobile.



