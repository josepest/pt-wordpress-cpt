<img src="https://www.upturnrentals.com/assets/img/logo.png" width="200">

<br />

# Prueba Técnica WordPress para Upturn Rentals


El objetivo de esta prueba técnica no es evaluar tus conocimientos previos, sino la capacidad de aprender, buscar información y documentación en internet sobre un tema. 
Así como la capacidad de comunicar con el equipo, si es el caso, la necesidad de ayuda o dudas para poder avanzar en la tarea.

Por este motivo te animo a contactar conmigo para cualquier duda o si te quedas encallado en cualquiera de los puntos.

<br>

* * *

### OBJETIVO

El objetivo es instalar y configurar un website con el CMS WordPress, instalar el tema Understrap como tema padre y el tema hijo Understrap child. Utilizar este tema hijo activo para generar un shortcode que muestre un listado de Custom Post Types que habremos definido previamente. Generar una página en la web donde se use este shortcode y se muestre estos datos por pantalla de una forma responsive (Visible correctamente en Desktop, tablet y movil).

<br />

### PASOS

1.  Instalar un WordPress en tu entorno local  
    http://localhost
2.  En la carpeta \\wp-content\\themes de tu WordPress local, clonar este repositorio  


```sh
cd \wp-content\themes   
git clone https://github.com/josepest/pt-wordpress-cpt
```

    
3.  Activa el tema understrap-child en tu wordpress.
4.  Crea una nueva rama git en el repositorio git con tu nombre.
5.  Programa las acciones y pasos detallados en los puntos posteriores para tener la solución a esta prueba, siempre realizando los commits en la rama de git creada por ti con tu nombre.
6.  Una vez tengas la solución, realiza un push a este repositorio de github.
7.  Envíame un email para revisar la solución conjuntamente, o realiza una pull request.

<br />

Por favor, si una vez lida toda la documentación tienes cualquier pregunta o te quedas en callado en cualquiera de los puntos, no dudes en contactar. 🙏

<br />


### DETALLES

<br />

**Entorno de desarrollo:**

Lo primero es preparar un entorno local de desarrollo web.

*   Servidor web (Apache) que sea capaz de ejecutar PHP,
*   Servidor de base de datos MySQL
*   IDE para programar (Visual Studio Code, PhpStorm, …)

Tienes en el apartado recursos enlaces de ayuda para preparar esto.

Al final de este punto deberías poder ver una página web local en:  
http://localhost

<br />

**Instalación WordPress:**

Utilizar los recursos de abajo para instalar un WordPress en tu entorno local de desarrollo. Archivos y Base de datos.

Al final de este punto deberías poder ver una página web WordPress local en:  
http://localhost

<br />

**Instalación Tema Understrap y Understrap-child:**

Understrap es un tema base muy utilizado por programadores, ya que permite una fácil personalización, y lleva configurada una estructura base de programación con composer, npm con scripts para optimización para el frontend, así como la librería frontend Bootstrap.

Este repositorio lleva el código del tema padre e hijo Understrap e Understrap-child, deberás clonar este repositorio directamente en la carpeta \\wp-content\\themes de tu instalación de Wordpress.

Una vez clonados, activa la plantilla Understrap-child en tu Wordpress.

Esta Understrap-child será la que utilizaremos para realizar todas las personalizaciones, así en un futuro podremos actualizar la plantilla padre sin perder nuestras personalizaciones creadas en la plantilla hijo. Solo debemos tocar el código de la plantilla Understrap-child.

No es necesario entender y conocer a fondo la plantilla en sí, sino simplemente instalarla. Utilizar los recursos de abajo para saber más sobre los temas.

Al final de este punto deberías poder ver una página web WordPress local con el tema base de Understrap-child activado y funcionando:  
http://localhost

<br />

**Configurar Custom Post Type en WordPress:**

Un CPT o Custom Post Type en WordPress es una entidad de datos personalizada sobre la que podemos definir nuevos campos personalizados, aparte de los standard que lleva por defecto (Título, texto, autor, …)  
Una entrada del blog o una página de WordPress son distintos CPT que vienen por defecto en WordPress.

Para crear nuevos CPT, como todo en WordPress, se puede hacer a través de un Plug-in de terceros, o mediante código PHP en el tema instalado, o mediante un Plug-in propio.

Para esta prueba podéis utilizar cualquiera de las tres opciones.  
La más sencilla es utilizar el Plug-in de terceros ACF que te permite generar estos CPT y generar sus campos personalizados.

Tienes abajo en recursos documentación de como usar este plug-in.

<br />

**Crearemos el siguiente CPT con los siguientes campos:**

**Nombre CPT:**  
platos


**Campos:**  
title: tipo texto, viene por defecto de cualquier CPT, no es necesario crearlo.  
description: tipo textarea  
price: tipo número  
picture: tipo imagen  

Al final de este punto deberías poder introducir platos en el admin de WordPress con los campos creados.

![Screenshoot de wordpress](readme_asset_wp_cpt.jpg)

<br />

**Opcional:**

WordPress tiene lo que llama Taxonomies, que utiliza para que se puedan crear categorías sobre por ejemplo las entradas de los posts del Blog.

Del mismo modo que se puede crear CPT’s también se pueden crear categorías personalizadas, Custom Taxonomies.

Para nuestra prueba podríamos crear categorías de platos como las secciones de una carta.

Puedes utilizar el mismo plug-in ACF para crear este tipo de categoría que serían las secciones de la carta y que sirvan para categorizar estos nuevos CPT’s platos que acabamos de crear.

<br />

**Configurar Shortcode en WordPress:**

Los Shortcode’s en WordPress no son más que funciones PHP que definimos y les asignamos un nombre, pueden realizar cualquier acción y lo que devuelve la función será mostrado en la página en que se usa el Shortcode.

Los Shortcode’s se pueden crear de muchas maneras, abajo encontrarás links con documentación sobre el tema.

<br />

**Un ejemplo:**

Usaremos el archivo functions.php del tema para definir nuestro shortcode:

```php
function menu_carta_sc() {
    return 'Este texto es lo que printara por pantalla el shorcut';
}

add_shortcode('menu_carta', 'menu_carta_sc');
```


Usaremos el código<br>
 \[menu\_carta\] 
 
 Directamente en la edición visual de nuestra página para invocar la ejecución de esta función y mostrar por pantalla lo que devuelve la función.

Para nuestra prueba debemos hacer un shortcut que consulte todos los CPT platos y los devuelva en un formato parecido a este:

![Screenshoot frontend resultado](readme_asset_wp_frontend.jpg)

Recuerda que el formato debe ser responsive, y se visualice correctamente tanto en desktop como en móvil.

Al finalizar este punto deberías tener una página de tu web que utilice el shortcut creado y visualice todos los CPT platos en la página  
http://localhost/platos

<br />

* * *

<br />

### RECURSOS

<br />

**PHP Entornos de desarrollo local:**

WAMP  
https://www.wampserver.com/en/

XAMP  
https://www.apachefriends.org/es/index.html

EasyPHP  
https://www.easyphp.org/es/index.php

Docker:  
https://github.com/kodetop/docker-php-mysql

<br />

**Wordpress**

Ayuda instalación:  
https://developer.wordpress.org/advanced-administration/before-install/howto-install/

Ayuda general:  
https://learn.wordpress.org/

Ayuda para programadores:  
https://developer.wordpress.org/

Temas:  
https://developer.wordpress.org/themes/

ShortCodes:  
https://developer.wordpress.org/plugins/shortcodes/

Custom Post Types:  
https://developer.wordpress.org/plugins/post-types/

<br />

**Plugin ACF:**

https://www.advancedcustomfields.com/resources/  
https://www.advancedcustomfields.com/downloads/  

<br />

**Wordpress Understrap theme:**

https://github.com/understrap/understrap  
https://docs.understrap.com/#/  
https://docs.understrap.com/#/understrap-child/getting-started  
https://github.com/understrap/understrap-child  

<br />

**Cursos PHP:**

https://www.w3schools.com/php/  
https://www.youtube.com/watch?v=OK\_JCtrrv-c  
https://www.youtube.com/watch?v=nPCJAx5c1uE  

<br />

**GIT control de versiones:**

https://rogerdudler.github.io/git-guide/index.es.html  
https://www.freecodecamp.org/espanol/news/guia-para-principiantes-de-git-y-github/