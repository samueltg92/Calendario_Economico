# Calendario Económico

Este script de Python se centra en enviar información actualizada del calendario económico a través de un bot de Telegram. A continuación, se describe el código:

Importar las bibliotecas necesarias:

pandas: para trabajar con datos en forma de DataFrame.
requests: para realizar solicitudes HTTP para obtener datos del calendario económico.
pytz: para manejar zonas horarias y realizar conversiones de fechas y horas.
time: para realizar pausas en el código.
datetime de datetime: para trabajar con fechas y horas.
Bot de telegram: para interactuar con el bot de Telegram y enviar mensajes.
Definir una función country_to_emoji(country_code) que toma un código de país y devuelve su respectiva bandera en emoji. Esto se logra mediante una simple transformación de los caracteres Unicode de las banderas.

Definir una función principal send_info(), que se encarga de obtener información actualizada del calendario económico y enviarla a través del bot de Telegram.

En la función send_info(), se construye la URL del calendario económico y se establecen los filtros para obtener eventos desde el día actual hasta una semana después. También se especifican los códigos de países de interés (EE. UU., Suiza, Europa, Australia, Japón, Reino Unido, Canadá y Nueva Zelanda).

Se realiza una solicitud HTTP GET para obtener los datos del calendario económico en formato JSON.

Los datos se convierten a un DataFrame de pandas para facilitar su manipulación.

Se filtran los eventos del calendario que tienen una importancia alta (1).

Se formatea el mensaje que se enviará a través del bot de Telegram, incluyendo la fecha, país, título del evento, importancia, dato previo y pronóstico para cada evento relevante.

Se crea una instancia del bot de Telegram con el token proporcionado.

Se calculan las fechas de inicio y fin de la semana actual.

Se recorre el DataFrame filtrado y se agrega la información relevante al mensaje.

Finalmente, se envía el mensaje completo al grupo de Telegram con el chat ID "-1001621135988" (el chat de "The Quant Company").

El código incluye un bloque comentado que contiene un bucle infinito. Originalmente, este bucle se diseñó para ejecutar la función send_info() automáticamente cada lunes a las 6 a.m. (horario de Nueva York) mediante la comparación de la fecha y hora actual con el día y hora objetivo. Sin embargo, el bucle está comentado, por lo que actualmente el bot solo enviará la información una vez cuando se ejecute el script.
