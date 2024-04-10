![ref1]**Departamento Académico de Ingeniería**

**C8280 -Comunicación de Datos y Redes**

**Actividad 4: Configuración inicial de un Switch**

Para completar este laboratorio vamos utilizar Cisco Packet Tracer
# **Objetivos**
**Parte 1: Verifica la configuración predeterminada del switch**

**Parte 2: Establece una configuración básica del switch**

**Parte 3: Configura un aviso de MOTD**

**Parte 4: Guarda los archivos de configuración en la NVRAM Parte 5: Configura el S2**
# ` `**Escenario**
En esta actividad, realizará tareas básicas de configuración del switch. Protegeremos el acceso a la interfaz de línea de comandos (CLI) y a los puertos de la consola mediante contraseñas cifradas y contraseñas de texto no cifrado. Configuraremos mensajes para los usuarios que inician sesión en el switch. Estos banners de mensajes también se utilizan para advertir a los usuarios no autorizados que el acceso está prohibido.

**Nota:** En Packet Tracer, el switch Catalyst 2960 utiliza la versión 12.2 de IOS de forma predeterminada. Si es necesario, la versión IOS se puede actualizar desde un servidor de archivos en la topología Packet Tracer. El switch puede configurarse para arrancar a IOS versión 15.0, si esa versión es necesaria.
# ` `**Instrucciones**
## ` `**Verifica la configuración predeterminada del switch**
1. **Ingresa al modo EXEC privilegiado.**

Puedes acceder a todos los comandos del switch en el modo EXEC privilegiado. Sin embargo, debido a que muchos de los comandos privilegiados configuran parámetros operativos, el acceso privilegiado se debe proteger con una contraseña para evitar el uso no autorizado.

El conjunto de comandos EXEC privilegiado incluye los comandos disponibles en el modo EXEC del usuario, muchos comandos adicionales y el comando **configure** a través del cual se obtiene acceso a los modos de configuración.

1. Haz clic en S1 y luego en la pestaña CLI. Presione Enter.

   ![](Aspose.Words.ee184615-bb90-4573-aadb-a8fef09db785.002.png)

1. Ingresa al modo EXEC privilegiado introduciendo el comando enable:

*Abra la ventana de configuración para S1*

Switch> **enable**

Switch#

Observa que la solicitud cambió para reflejar el modo EXEC privilegiado. ![](Aspose.Words.ee184615-bb90-4573-aadb-a8fef09db785.003.png)

1. **Examina la configuración actual del switch.**

Ingresa el comando show running-config.

Switch# **show running-config**

Responde las siguientes preguntas:

![](Aspose.Words.ee184615-bb90-4573-aadb-a8fef09db785.004.png)

1. ¿Cuántas interfaces Fast Ethernet tiene el switch?

   Tiene 24 interfaces Fast Eternet

1. ¿Cuántas interfaces Gigabit Ethernet tiene el switch?

   Tiene dos interfaces Gigabit

1. ¿Cuál es el rango de valores que se muestra para las líneas vty?

   Del 0 al 4 y del 5 al 15

1. ¿Qué comando muestra el contenido actual de la memoria de acceso aleatorio no volátil

   (NVRAM)? show star

   Show running-config startup-config

1. ¿Por qué el switch responde con "startup-config no está presente"

   Porque faltaría ponerlo el show running-config, ya que esto nos permite mostrar información sobre la asignación de direcciones ip en una red.

**2. Crea una configuración básica del switch**

**Asigna un nombre a un switch.**

Para configurar los parámetros de un switch, quizá deba pasar por diversos modos de configuración. Observa cómo cambia la petición de entrada mientras navega por el switch.

Switch# **configure terminal**

Switch(config)# **hostname S1**

S1(config)# **exit**

S1#

![](Aspose.Words.ee184615-bb90-4573-aadb-a8fef09db785.005.png)

**Proporciona acceso seguro a la línea de consola.**

Para proporcionar un acceso seguro a la línea de la consola, acceda al modo config-line y establezca la contraseña de consola en **cesar**.

S1# **configure terminal**

Enter configuration commands, one per line. End with CNTL/Z.

S1(config)# **line console 0**

S1(config-line)# **password cesar**

S1(config-line)# **login**

S1(config-line)# **exit**

S1(config)# **exit**

%SYS-5-CONFIG\_I: Configured from console by console S1#

![](Aspose.Words.ee184615-bb90-4573-aadb-a8fef09db785.006.png)

Pregunta:

¿Por qué se requiere el comando **login**?

Para identificar la identidad del usuario antes de permitir el acceso.

**Verifica que el acceso a la consola sea seguro.**

Salimos del modo privilegiado para verificar que la contraseña del puerto de consola esté vigente.

S1# **exit**

Switch con0 is now available Press RETURN to get started.

User Access Verification Password:

S1>

![](Aspose.Words.ee184615-bb90-4573-aadb-a8fef09db785.007.png)

**Proporciona un acceso seguro al modo privilegiado.**

Establece la contraseña de **enable** en **jeka**. Esta contraseña protege el acceso al modo privilegiado.

S1> **enable**

S1# **configure terminal**

S1(config)# **enable password jeka**

S1(config)# **exit**

%SYS-5-CONFIG\_I: Configured from console by console

S1#

![](Aspose.Words.ee184615-bb90-4573-aadb-a8fef09db785.008.png)

**Verifica que el acceso al modo privilegiado sea seguro.**

1. Introduce el comando **exit** nuevamente para cerrar la sesión del switch.
1. Presiona **<Enter>**; a continuación, se le pedirá que introduzca una contraseña:

   User Access Verification Password:

1. La primera contraseña es la contraseña de consola que configuró para **line con 0**. Introduzca esta contraseña para volver al modo EXEC del usuario.
1. Introduce el comando para acceder al modo privilegiado.
1. Introduce la segunda contraseña que configuró para proteger el modo EXEC privilegiado.

   ![](Aspose.Words.ee184615-bb90-4573-aadb-a8fef09db785.009.png)

1. Verifica su configuración examinando el contenido del archivo de configuración en ejecución:

   S1# **show running-config**

   ![](Aspose.Words.ee184615-bb90-4573-aadb-a8fef09db785.010.png)

   Ten en cuenta que la consola y las contraseñas de activación están en texto plano. Esto podría suponer un riesgo para la seguridad si alguien está mirando por encima de su hombro u obtiene acceso a los archivos de configuración almacenados en una ubicación de copia de seguridad.

**Configura una contraseña encriptada para proporcionar un acceso seguro al modo privilegiado.**

La **contraseña de enable** se debe reemplazar por una nueva contraseña secreta encriptada mediante el comando **enable secret**. Configura la contraseña de enable secret como **itsasecret**.

S1# **config t**

S1(config)# **enable secret itsasecret**

S1(config)# **exit**

S1#

![](Aspose.Words.ee184615-bb90-4573-aadb-a8fef09db785.011.png)

**Nota**: La contraseña de **enable secret** sobrescribe la contraseña de **enable** password. Si ambos están configurados en el switch, debes ingresar la contraseña **enable secret** para ingresar al modo EXEC privilegiado.

**Verifica si la contraseña de enable secret se agregó al archivo de configuración.**

Introduce el comando show running-config nuevamente para verificar si la nueva contraseña de enable secret está configurada.

**Nota**: Puedes abreviar **show running-config** como

S1# **show run**

Preguntas:

¿Qué se muestra como contraseña de enable secret?

![](Aspose.Words.ee184615-bb90-4573-aadb-a8fef09db785.012.png)

Me muestra otra contraseña encriptada, es decir más difícil de descifrar.

***Escriba sus respuestas aquí.***

¿Por qué la contraseña de enable secret se ve diferente de lo que se configuró?

Porque ahora ya se encuentra encriptada y tiene una mayor seguridad.

**Encripta las contraseñas de consola y de enable.**

Como notó en el paso anterior, la contraseña **enable secret** estaba encriptada, pero las contraseñas **enable** y **console** todavía estaban en texto plano. Ahora encriptamos estas contraseñas de texto no cifrado con el comando **service password-encryption**.

S1# **config t**

S1(config)# **service password-encryption** S1(config)# **exit**

![](Aspose.Words.ee184615-bb90-4573-aadb-a8fef09db785.013.png)

Pregunta:

Si configuras más contraseñas en el switch, ¿se mostrarán como texto no cifrado o en forma cifrada en el archivo de configuración? Explica.

Se mostrarían como texto no cifrado, porque hay que encriptarlas para que recién se muestren de forma cifrada.***scriba sus r***
## **3. Configure un aviso de MOTD**
**Configura un aviso de mensaje del día (MOTD).**

El conjunto de comandos de Cisco IOS incluye una característica que permite configurar los mensajes que cualquier persona puede ver cuando inicia sesión en el switch. Estos mensajes se denominan “mensajes del día” o “avisos de MOTD”. Coloca el texto del mensaje en citas o utilizando un delimitador diferente a cualquier carácter que aparece en la cadena de MOTD.

S1# **config t**

S1(config)# **banner motd "This is a secure system. Authorized Access Only!**

S1(config)# **exit**

%SYS-5-CONFIG\_I: Configured from console by console S1#

Preguntas:

¿Cuándo se muestra este aviso?

Cuando el usuario necesite ingresar.

![](Aspose.Words.ee184615-bb90-4573-aadb-a8fef09db785.014.png)

¿Por qué todos los switches deben tener un aviso de MOTD?

Porque es importante para que ingresen personas autorizaadas.
## **4 . Guarda y verifica archivos de configuración en NVRAM**
**Verifica que la configuración sea precisa mediante el comando show run.**

Guarda el archivo de configuración. Tu has completado la configuración básica del switch. Ahora haga una copia de seguridad del archivo de configuración en ejecución a NVRAM para garantizar que los cambios que se han realizado no se pierdan si el sistema se reinicia o se apaga.

S1# **copy running-config startup-config** Destination filename [startup-config]?**[Enter]** Building configuration...

[OK]

*Cierre la ventana de configuración para S1* Preguntas:

¿Cuál es la versión abreviada más corta del comando **copy running-config startup-config**?

La forma más corta es wr

Examine el archivo de configuración de inicio.¿Qué comando muestra el contenido de la NVRAM?

El comando sh run o show run

***Escriba sus respuestas aquí.***

¿Todos los cambios realizados están grabados en el archivo?

Sí, mientras los guardes si podrías verificarlo

***Escriba sus respuestas aquí.***
## **5. Configura S2**
Hemos completado la configuración en S1. Ahora configura el S2. Si no recuerda los comandos, consulte las partes 1 a 4 para obtener ayuda.

**Configura el S2 con los siguientes parámetros:**

*Abra la ventana de configuración para S2*

1. Device name: **S2**
1. Protege el acceso a la consola con la contraseña **chalo**.
1. Configura enable password como **claudi** y una contraseña enable secret como **itsasecret**.
1. Configura un mensaje apropiado para aquellos que inician sesión en el switch.

   ![](Aspose.Words.ee184615-bb90-4573-aadb-a8fef09db785.015.png)

1. Encripta todas las contraseñas de texto no cifrado.
1. Asegúrate de que la configuración sea correcta.

   ![](Aspose.Words.ee184615-bb90-4573-aadb-a8fef09db785.016.png)

   ![](Aspose.Words.ee184615-bb90-4573-aadb-a8fef09db785.017.png)

1. Guarda el archivo de configuración para evitar perderlo si el switch se apaga.

   ![](Aspose.Words.ee184615-bb90-4573-aadb-a8fef09db785.018.png)

`	`g.	Cierra la ventana de configuración para S2

*Fin del documento*
Comunicación de Datos y Redes

[ref1]: Aspose.Words.ee184615-bb90-4573-aadb-a8fef09db785.001.png
