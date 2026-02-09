# Guía para la gestión del sitio web de Némesis

El presente repositorio contiene los archivos necesarios para modificar y actualizar la [página web de la Mutual de Los Huemules](https://). La estructura es la siguiente:

En la capa inicial se encuentran los documentos asociados al inicio de la página, es decir, las plantillas .qmd de cada sección dispuesta en la barra de navegación superior. Además, se encuentra el yml que renderiza el archivo html que luego se publica en la página, el archivo css que le da forma a la página y carpetas de trabajo. Cabe mencionar que el archivo _publish.yml está hecho para subir la página a la app netlify, donde se encuentra alojado el link del sitio web.

Las carpetas son las siguientes:

-   `docs` : Contiene los archivos necesarios para diseñar el documento html en el que se basa la página web. Su contenido se hace de manera automática una vez que se manda a renderizar el proyecto.
-   `images`: Contiene todas las imágenes que se publican en la página.
-   `product`: Subsección que contiene las plantillas .qmd que despliegan las listas de las distintas publicaciones que se alojan en la barra lateral de la página. Dentro de la carpeta, cada tipo de producto tiene su propia carpeta en la que se distribuyen los escritos publicados.

Asimismo, en la capa inicial se alojan archivos de soporte de la página como `404.qmd` que muestra la plantilla de error de navegación y `styles.css` que contiene la configuración estética de la web.

### Códigos de .qmd

Los archivos *.qmd* que están en las carpetas `product` están codificados de tal manera de favorecer el orden y la posibilidad de encontrar estos archivos. 

#LINK PAGINA WEB