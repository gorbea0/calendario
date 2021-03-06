## Welcome to GitHub Pages by Oskar Unzueta



Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.




### Proyecto de Calendario laboral de oficinas del Ayuntamiento de Vitoria



[Link](url) and ![Image](src)


For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Instrucciones de uso


Para llevar el control de los fichajes

En Herramientas--Opciones--Seguridad--Seguridad de macros hay que permitir la ejecución de macros poniendo **nivel de seguridad bajo** para que se pueda ejecutar el código de VBA


Lo primero que hay que definir en la hoja **CONFIGURACION** los datos de usuario a modificar si no nos valen los que hay por defecto (columna J). Este calendario no está pensado para los que trabajen a turnos de mañana/tarde/noche.


```
Jornada anual genérica en  horas
Jornada diaria
Entrada mínima
Entrada máxima
Salida mínima
Salida máxima
Días de vacaciones a pasar al año que viene
```

---


A continuación ponemos los días de vacaciones, puentes, canosos etc que nos corresponden en el año (columna G): Si tienes otro tipo que no se corresponde lo asocias al más parecido

```
* Vacaciones
* Asuntos propios SS
* Asuntos particulares
* Canosos
* Puentes
* Vacaciones año anterior
```

Ahora vamos a la hoja `DIARIO` y ponemos todos los días que tenemos vacaciones, cursos, bajas, puentes etc en la columna B, llamada categoría


En la columna **COMENTARIO** podemos poner observaciones. Es importante que esté correcta la columna categorías con nuestros festivos, vacaciones, bajas etc para que calcule bien

Las categorías hay que elegirlas de la lista desplegable o bien escribirlo exactamente igual ej. Vacaciones, Puentes etc empezando por mayúscula.


Ya sólo queda ir anotando cada día en la hoja DIARIO la hora de entrada y salida correspondiente (columnas D y E)o bien usar el botón fichar hoy.

---


También he añadido la posibilidad de capturar los datos del reporte de `Control Horario` para ello:
Vamos a la web del Ayunta: Minfoweb 


Y solicitamos con nuestras credenciales el informe horario especificando la fecha inicial y final (mejor no complicarse y pedir desde el 1 de enero hasta ayer)


Ir a "Informes Personales" / "Listado de Fichajes" y pinchar en el radiobuttom "Excel" y dar a Aceptar.
Darle a `ABRIR` y nos saldrá una hoja de Excel con nuestros fichajes. Ya sólo tenemos que seleccionar las 5 columnas de los fichajes (fecha, columna vacía, entrada, salida y horas trabajadas) 


Una vez seleccionado el rango con las 5 columnas dar a `COPIAR` y pegarlo en la hoja "ControlHorario" de este libro de Excel.
La primera fila son los títulos de las columnas puedes sobreescribirlos si quieres ya que el scrip ignora la primera fila.
Dar al botón "Procesar datos" y al cabo de poco tiempo los datos de fichaje se habrán transcrito a la hoja `Diario` y se habrán analizado los códigos.
Ya puedes ver la información en el *dashboard*.


---


He añadido un botón para establecer automáticamente los dias festivos y los fines de semana en la hoja diario, sólo están los festivos fijos, faltarían los variables como semana santa, puentes obligados, San José, San Mateo etc. Gracias a esto cada año se genera automáticamente los días festivos aunque los variables habría que anotarlos manualmente en la hoja diario, segunda columna. Si el usuario vuelve a generar los festivos por segunda vez no pasaría nada ya que lo reescribe, se puede hacer si sospechamos que se haya borrado algún festivo. Si definimos los festivos manualmente es importante hacerlo seleccionando desde la lista desplegable ya que cada categoría *"Festivo"*, *"Weekend"* etc debe escribirse exactamente igual es decir empezando con mayúscula etc. Si no escribimos la categoría de forma excata no podrá hacer los recuentos correctamente. En próximas versiones se podría mejorar este aspecto.


En configuración podemos asignar colores a los distintos tipos de permisos o festivos y verlo reflejado en las hojas diario y año. Podemos modificar los colores tantas veces como queramos.

Nota importante:
Esta aplicación es un mash up de código VBA y fórmulas convencionales de Excel insertadas en las celdas. Si se borra alguna celda con fórmulas podría dejar de funcionar algunos cálculos y no daría error.
No borrar por error las fórmulas de las celdas. **No están protegidas!**
El usuario puede borrar sin problema las columnas de fichaje de entrada y salida de la hoja `diario` y las de la hoja `ControlHorario`.


Si tienes alguna sugerencia o ves algún fallo puedes contactarme en  [contacto](mailto:ounzueta@vitoria-gasteiz.org)

Este software me funciona perfectamente en mi caso, pero habría que adaptarlo a otros casos particulares cuya problemática desconozco, a lo mejor no vaya bien con medias-jornadas, trabajos a turnos o en festivos etc: No conozco toda la normativa de jornadas laborales!.


Ten cuidado en no borrar fórmulas cuando borres celdas.

### Características para nuevas versiones

1. Poder elegir el color de la tinta no sólo del fondo para cada tipo de categoría.
2. Mejoras en la representación de la información.
3. Convertir las categorías etc en no-case-sensitive.


Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/gorbea0/calendario/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

[link](https://gorbea0.github.io/calendario/)

### Support or Contact

Having trouble with my Excel calendar? Check out this documentation or [contact me](mailto:gorbea0@gmail.com) and I’ll help you sort it out.
