![ref1]**Departamento Académico de Ingeniería**

**C8280 -Comunicación de Datos y Redes**

**Actividad 5: Identificación de direcciones MAC y direcciones IP**
# ` `**Objetivos**
**Parte 1: Recopilar información de PDU para la comunicación de red local**

**Parte 2: Recopilar información de PDU para la comunicación de red remota**
# ` `**Aspectos básicos**
Esta actividad está optimizada para la visualización de PDU<sup>[^1]</sup>. Los dispositivos ya están configurados. Reunirá información de PDU en el modo de simulación y responderá una serie de preguntas sobre los datos que obtenga.

` `**Instrucciones**
# **Recopila información del PDU para la comunicación de red local**
**1. Recopila información de la PDU a medida que un paquete viaja de 172.16.31.5 a**

**172.16.31.2.**

1. Haz clic en **172.16.31.5** y abra el **Command Prompt**.
1. Introduce el comando **ping 172.16.31.2**.

   ![](Aspose.Words.cfacfd52-f78a-4be5-92d0-a62d9bddcbea.002.png)

1. Cambia al modo de simulación y repita el comando **ping 172.16.31.2** . Aparece una PDU junto a **172.16.31.5**.

   ![](Aspose.Words.cfacfd52-f78a-4be5-92d0-a62d9bddcbea.003.png)

1. Haz clic en la PDU y observa la siguiente información de las pestañas **Modelo OSI l** y **Capa de PDU saliente:**
   1. Destination MAC Address:**000C:85CC:1DA7** o Source MAC Address: **00D0:D311:C788** o Source IP Address:**172.16.31.5** o Destination IP Address: **172.16.31.2**
   1. At Device: **172.16.31.5**

      ![Texto, Tabla

Descripción generada automáticamente](Aspose.Words.cfacfd52-f78a-4be5-92d0-a62d9bddcbea.004.png)

1. Haz clic en **Capture / Forward (la flecha derecha seguida de una barra vertical)** para mover la PDU al siguiente dispositivo. Reúna la misma información del paso 1d. Repite este proceso hasta que la PDU llegue al destino. Registra la información que reunió de la PDU en una hoja de cálculo con un formato como el de la tabla que se muestra a continuación:

**Formato de hoja de cálculo de ejemplo**

|**En dispositivo**|**MAC de destino**|**MAC de origen**|**IPv4 de origen**|**IPv4 de destino**|
| :-: | :-: | :-: | :- | :- |
|172\.16.31.5|000C:85CC:1DA7|00D0:D311:C788|172\.16.31.5|172\.16.31.2|
|**En dispositivo**|**MAC de destino**|**MAC de origen**|**IPv4 de origen**|**IPv4 de destino**|
|Switch1|000C:85CC:1DA7|00D0:D311:C788|No corresponde|No corresponde|
|Concentrador|No corresponde|No corresponde|No corresponde|No corresponde|
|172\.16.31.2|00D0:D311:C788|000C:85CC:1DA7|172\.16.31.2|172\.16.31.5|

**2 . Reunir información adicional de la PDU de otros ping.**

Repite el proceso del paso 1 y reúna información para las siguientes pruebas:

- Ping de 172.16.31.2 a 172.16.31.3

|**En dispositivo**|**MAC de destino**|**MAC de origen**|**IPv4 de origen**|**IPv4 de destino**|
| :-: | :-: | :-: | :- | :- |
|172\.16.31.2|0060:7036:2849|000C:85CC:1DA7|172\.16.31.2|172\.16.31.3|
|Concentrador|No corresponde|No corresponde|No corresponde|No corresponde|
|172\.16.31.3|000C:85CC:1DA7|0060:7036:2849|172\.16.31.3|172\.16.31.2|


- Ping de 172.16.31.4 a 172.16.31.5 Vuelva al modo Realtime.

|**En dispositivo**|**MAC de destino**|**MAC de origen**|**IPv4 de origen**|**IPv4 de destino**|
| :-: | :-: | :-: | :- | :- |
|172\.16.31.4|00D0.D311.C788|000C.CF0B.BC80|172\.16.31.4|172\.16.31.5|
|Switch 1|000C.CF0B.BC80|00D0.D311.C788|No corresponde|No corresponde|
|172\.16.31.5|<p>000C.CF0B.BC80</p><p></p>|<p>00D0.D311.C788</p><p></p>|172\.16.31.5|172\.16.31.4|

2. # **Recopila información del PDU para la comunicación de red remota**
Para comunicarse con redes remotas, es necesario un dispositivo de puerta de enlace. Estudia el proceso que tiene lugar para comunicarse con los dispositivos de la red remota. Presta mucha atención a las direcciones MAC utilizadas.

**Recopila información de la PDU a medida que un paquete viaja de 172.16.31.5 a**

**10.10.10.2.**

1. Haz click en **172.16.31.5** y abra el **Command Prompt**.
1. Introduce el comando **ping 10.10.10.2**.

   ![](Aspose.Words.cfacfd52-f78a-4be5-92d0-a62d9bddcbea.005.png)

1. Cambia al modo de simulación y repita el comando **ping 10.10.10.2** . Aparece una PDU junto a **172.16.31.5**.

![Diagrama

Descripción generada automáticamente](Aspose.Words.cfacfd52-f78a-4be5-92d0-a62d9bddcbea.006.png)

1. Haz clic en la PDU y observe la siguiente información en la ficha **Outbound PDU Layer (Capa de PDU saliente)**:

   Destination MAC Address: 00D0:BA8E:741A

   Source MAC Address: 00D0:D311:C788

   Source IP Address: 172.16.31.5

   Destination IP Address: 10.10.10.2

   At Device: 172.16.31.5 

   ![Interfaz de usuario gráfica, Texto, Aplicación

Descripción generada automáticamente](Aspose.Words.cfacfd52-f78a-4be5-92d0-a62d9bddcbea.007.png)Pregunta:

   ¿Qué dispositivo tiene el MAC de destino que se muestra?

   La laptop 10.10.10.2

   ***Escriba sus respuestas aquí.***

1. Haz clic en **Capture / Forward (la flecha derecha seguida de una barra vertical)** para mover la PDU al siguiente dispositivo. Reúne la misma información del paso 1d. Repite este proceso hasta que la PDU llegue al destino. Registra la información de la PDU que recopiló del ping 172.16.31.5 a 10.10.10.2 en una hoja de cálculo utilizando un formato como la tabla de muestra que se muestra a continuación:

|**En dispositivo**|**MAC de destino**|**MAC de origen**|**IPv4 de origen**|**IPv4 de destino**|
| :-: | :-: | :-: | :-: | :- |
|172\.16.31.5|00D0:BA8E:741A|00D0:D311:C788|172\.16.31.5|10\.10.10.2|
|Switch1|00D0:BA8E:741A|00D0:D311:C788|No corresponde|No corresponde|
|Router|0060:2 F 84:4 AB6|00D0:588C:2401|172\.16.31.5|10\.10.10.2|
|Switch0|0060:2F84:4AB6|00D0:588C:2401|No corresponde|No corresponde|
|**En dispositivo**|**MAC de destino**|**MAC de origen**|**IPv4 de origen**|**IPv4 de destino**|
|Punto de acceso|No corresponde|No corresponde|No corresponde|No corresponde|
|10\.10.10.2|00D0:588C:2401|0060:2 F 84:4 AB6|10\.10.10.2|172\.16.31.5|
# **Preguntas** 
Responde las siguientes preguntas relacionadas con los datos capturados: 

1. ¿Se utilizaron diferentes tipos de cables / medios para conectar dispositivos? 

   Si, tenemos tres tipos, medio inalámbrico, cobre y fibra 

   ***Escriba sus respuestas aquí.*** 

1. ¿Los cables cambiaron el manejo de la PDU de alguna manera? 

   No, ya que los cable solo trabajan en capa 1

   ***Escriba sus respuestas aquí.*** 

1. ¿El h**ub** perdió parte de la información que recibió? 

   No

   ***Escriba sus respuestas aquí.*** 

1. ¿Qué hace el **hub** con las direcciones MAC y las direcciones IP? 

   No hace nada, solo reenvía hacia todos sus puertos

   ***Escriba sus respuestas aquí.*** 

1. ¿El **punto de acceso** inalámbrico hizo algo con la información que se le entregó? 

   Si, vueleve a empaquetar la trama para que viaje por ese medio 

   ***Escriba sus respuestas aquí.*** 

1. ¿Se perdió alguna dirección MAC o IP durante la transferencia inalámbrica? 

   No, 

   ***Escriba sus respuestas aquí.*** 

1. ¿Cuál fue la capa OSI más alta que utilizaron el **hub** y el **punto de acceso**? 

   Solamente trabaja en cpa 1

   ***Escriba sus respuestas aquí.*** 

1. ¿El **hub** o el **punto de acceso** reprodujeron en algún momento una PDU rechazada con una “X” de color rojo? 

Si, ya que al reenviar a todos los puertos solo es uno el destino y los demás los rechaza

***Escriba sus respuestas aquí.*** 

1. Al examinar la ficha **PDU Details (Detalles de PDU)**, ¿qué dirección MAC aparecía primero, la de origen o la de destino? 

   La de destino

   ***Escriba sus respuestas aquí.*** 

1. ¿Por qué las direcciones MAC aparecen en este orden? 

   Ya que i conoce la dirección, va a renviar la trama más rápido

   ***Escriba sus respuestas aquí.*** 

1. ¿Había un patrón para el direccionamiento MAC en la simulación? 

no

***Escriba sus respuestas aquí.*** 

1. ¿Los switches reprodujeron en algún momento una PDU rechazada con una “X” de color rojo? 

   No, porque solo renvian la traba aal destino requerido***Escriba sus respuestas aquí.*** 

1. Cada vez que se enviaba la PDU entre las redes 10 y 172, había un punto donde las direcciones MAC cambiaban repentinamente.  ¿Dónde ocurrió eso? 

   Si, ocurre en el router

   ***Escriba sus respuestas aquí.*** 

1. ¿Qué dispositivo usa direcciones MAC que comienzan con 00D0: BA? 

   Es la del router

   ***Escriba sus respuestas aquí.*** 

1. ¿A qué dispositivos pertenecían las otras direcciones MAC? 

   Pertenecían a direcciones emisores y receptores

   ***Escriba sus respuestas aquí.*** 

1. ¿Las direcciones IPv4 de envío y recepción cambiaron los campos en alguna de las PDU? 

   No

   ***Escriba sus respuestas aquí.*** 

1. Cuando sigue la respuesta a un ping, a veces llamado *pong*, ¿ve el cambio de envío y recepción de direcciones IPv4? 

   Si

   ***Escriba sus respuestas aquí.*** 

1. ¿Cuál es el patrón para el direccionamiento IPv4 utilizado en esta simulación? 

   ***El patron es que cada puerto debe de manejar una dirección i diferentee***

1. ¿Por qué es necesario asignar diferentes redes IP a los diferentes puertos de un router? 

   Para poder intereconectar redes

   ***Escriba sus respuestas aquí.*** 

1. Si esta simulación se configura con IPv6 en lugar de IPv4, ¿cuál sería la diferencia? 

   Lo único que cambiaría sería el formato

   ***Escriba sus respuestas aquí.***

*Fin del documento*
Comunicación de Datos y Redes

[^1]: <https://es.wikipedia.org/wiki/Unidad_de_datos_de_protocolo>
[ref1]: Aspose.Words.cfacfd52-f78a-4be5-92d0-a62d9bddcbea.001.png
