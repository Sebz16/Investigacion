# Relación entre malware y las imagénes

### Malware Images: Visualization and Automatic Classification
> En este artículo, adoptamos un enfoque completamente diferente y novedoso para caracterizar y analizar el malware. 
En un nivel más amplio, un ejecutable de malware se puede representar como una cadena binaria de ceros y unos. Este vector
puede transformarse en una matriz y verse como una imagen. Observamos similitudes visuales significativas en la textura de la
imagen del malware que pertenece a la misma familia.
[link] (https://www.researchgate.net/publication/228811247_Malware_Images_Visualization_and_Automatic_Classification)
***
## ¿Cómo funciona?

Un binario de malware determinado se lee como un vector de enteros sin signo de 8 bits y luego se organiza en una matriz 2D. 
Esto se puede visualizar como una imagen en escala de grises en el rango [0,255] (0: negro, 255: blanco). El ancho de la imagen 
es fijo y se permite que la altura varíe según el tamaño del archivo.

<img src="https://bbs.kanxue.com/upload/attach/202202/835440_NFBZ6TBM3993Z36.jpg" width="600" height="200" />
<img src="https://bbs.kanxue.com/upload/attach/202202/835440_UYUB8CGVDBBNCJC.jpg" width="300" height="400" />

Abajo se muestra una imagen de ejemplo de un *Trojan downloader*, *Dontovo A*, que descarga y ejecuta archivos arbitrarios. 
Es interesante observar que en muchos casos, diferentes secciones (fragmentos binarios) del malware exhiben texturas
de imagen distintivas. Se puede encontrar una taxonomía detallada de varios fragmentos binarios primitivos y su visualización como imágenes
en escala de grises.

<img src="https://bbs.kanxue.com/upload/attach/202202/835440_W2AXHCUQJDXDWAN.jpg" width="400" height="500" />

La sección .text contiene el código ejecutable. En la figura, podemos ver que la primera parte de la sección .text contiene el código cuya textura
es de grano fino. El resto se rellena con ceros (negros) que indican un relleno de ceros al final de esta sección. La siguiente sección .data contiene 
código no inicializado (parche negro) y datos inicializados (textura de grano fino). La sección final es la sección .rsrc que contiene todos los
recursos del módulo. Estos también pueden incluir íconos que puede usar una aplicación.
