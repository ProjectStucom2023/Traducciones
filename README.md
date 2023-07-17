# Traducciones

El método `generarCalendario` es responsable de generar un calendario en formato HTML con los datos proporcionados. Toma tres parámetros: `year` (año), `month` (mes) y `calendario` (una matriz de cadenas que representa los datos del calendario). El método devuelve una cadena que contiene el calendario en formato HTML.

El método comienza creando dos objetos `LocalDate` utilizando el año y el mes proporcionados. `firstDateOfMonth` representa el primer día del mes y `lastDateOfMonth` representa el último día del mes.

A continuación, se crea un objeto `DateTimeFormatter` llamado `dayFormatter` que se utilizará más adelante para formatear los días del calendario.

El método lee el idioma de entrada y salida desde un archivo de configuración llamado "config.txt". Utiliza un `BufferedReader` para leer el archivo línea por línea. Las primeras dos líneas del archivo contienen información sobre el idioma de entrada y salida. Estas líneas se dividen en partes utilizando espacios en blanco como separadores, y se guarda la segunda parte de cada línea en las variables `inputLanguage` y `outputLanguage`, respectivamente.

A continuación, se intenta obtener las traducciones necesarias para el calendario desde archivos de traducción externos. Estos archivos contienen traducciones para los días de la semana, las horas y otras etiquetas relevantes. El método `obtenerTraduccionesDesdeArchivoInternacional` se utiliza para leer las traducciones necesarias para los días de la semana, mientras que el método `obtenerTraduccionDesdeArchivoInternacional` se utiliza para obtener las traducciones para las horas y otras etiquetas.

Luego, se crea un `StringBuilder` llamado `htmlBuilder` para construir la cadena HTML del calendario. Se agregan etiquetas HTML iniciales, como `<h2>` para el título del calendario y `<table>` para la estructura de la tabla del calendario.

El método procede a generar el contenido del calendario. Utiliza un bucle `while` que itera sobre las semanas del mes. Dentro del bucle, se obtiene la fecha de inicio de cada semana, que se establece en el primer día de la semana (lunes). A partir de esta fecha, se calcula el número de semana utilizando el método `ChronoUnit.WEEKS.between`.

Dentro del bucle, se agregan etiquetas HTML para representar cada semana del calendario. Se incluyen etiquetas `<th>` para los días de la semana y etiquetas `<td>` para las horas y las peticiones de reserva. Dependiendo de los datos en la matriz `calendario`, se aplican diferentes estilos y colores a las celdas del calendario.

Al final de cada iteración del bucle, se incrementa la fecha de inicio de la semana en una semana utilizando el método `plusWeeks(1)`.

Finalmente, se cierran las etiquetas HTML y se devuelve la cadena HTML completa como resultado.

En resumen, el método `generarCalendario` toma los datos de un calendario y genera una representación en formato HTML. Utiliza las traducciones adecuadas según el idioma especificado en el archivo de configuración y aplica estilos y colores apropiados a las celdas del calendario.
