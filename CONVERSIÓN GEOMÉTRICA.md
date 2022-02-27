Sensores: preprocesado, corrección y fusión de imágenes (IV)
# CONVERSIÓN GEOMÉTRICA

Jessica Bernal Borrego
27/02/22

##### El concepto de corrección geométrica incluye cualquier cambio en la posición que ocupan los píxeles en la imagen. Algunas de las funciones de transformación que se aplican son las siguientes: 
> ![](https://codimd.s3.shivering-isles.com/demo/uploads/55c84c826662ee144f2d26f43.png)


##### En la práctica, se trata de identificar puntos en la imagen a corregir que coinciden con puntos de otra imagen o cartografía que se adopte como referencia, por lo que esencialmente se trata de una nueva georreferenciación de la imagen. Para nuestro ejemplo se va a utilizar una imagen carente de SRC. 

![](https://codimd.s3.shivering-isles.com/demo/uploads/55c84c826662ee144f2d26f44.png)


### 1. Localización de los puntos de control comunes a la imagen y mapa.
##### Abrimos el georreferenciador de QGIS (*Ráster --> Georreferenciador*) y cargamos el ráster a georreferenciar o corregir.
 
![](https://codimd.s3.shivering-isles.com/demo/uploads/55c84c826662ee144f2d26f45.png)



### 2. Cálculo de las funciones de transformación entre coordenadas imagen y mapa, comprobando que RMS< tamaño píxel.

##### Antes de comenzar a marcar los puntos, es conveniente establecer los parámetros de configuración:
 
 ![](https://codimd.s3.shivering-isles.com/demo/uploads/55c84c826662ee144f2d26f46.png)


##### Empezaremos con el tipo de transformación Polinomial. Establecemos el directorio de salida e indicamos que se guarden los puntos tras la ejecución del proceso. Si queremos generar un informe, también podemos indicarlo aquí.




### 3. Transferencia de los ND originales a la nueva posición.

##### Procedemos a la introducción de los nuevos puntos, uno a uno, primero marcando este en nuestra imagen a georreferenciar y después en el lienzo del mapa (salvo que las coordenadas de cada punto que se va a muestrear ya se conozcan en cuyo caso se indican directamente).

![](https://codimd.s3.shivering-isles.com/demo/uploads/55c84c826662ee144f2d26f47.png)
 
![](https://codimd.s3.shivering-isles.com/demo/uploads/55c84c826662ee144f2d26f48.png)
###### Lienzo mapa (arriba), georrefenciador (abajo). Vemos los puntos marcados en rojo.
 
![](https://codimd.s3.shivering-isles.com/demo/uploads/55c84c826662ee144f2d26f49.png)



##### Vemos, en la parte inferior derecha, que la transformación Polinomial 1 arroja un error medio muy alto (> 1m), por lo que entramos en la configuración para probar si encontramos una ecuación de mejor ajuste. 

![](https://codimd.s3.shivering-isles.com/demo/uploads/55c84c826662ee144f2d26f4a.png)




 

##### La Polinomial 2 arroja un error medio de 0 desactivando uno de los puntos, lo cual es aceptable. Antes de proseguir, podemos guardar los puntos para el caso de que la georreferenciación no se ejecute correctamente (*Archivo --> Save GCP Point as…*) 

![](https://codimd.s3.shivering-isles.com/demo/uploads/55c84c826662ee144f2d26f4b.png)





### 4. Resultado 

##### Se ha dado color a la imagen para mejor visualización:

![](https://codimd.s3.shivering-isles.com/demo/uploads/55c84c826662ee144f2d26f4c.png)



 


