
![ref1]**Departamento Académico de Ingeniería** 

**C8280 -Comunicación de Datos y Redes** 


**


**Actividad 2: Implementación de una conectividad básica**</sub> 



Para completar este laboratorio vamos a utilizar Cisco Packet Tracer. 



Este ejercicio es grupal de a lo más 3 estudiantes, y debe terminarse hasta el sábado 30 de marzo a las 8:00 AM.  

Presenta un vídeo de a lo más 10 minutos mostrando los pasos de resolución de los ejercicios. 
**


**Tabla de asignación de direcciones** 

|**Dispositivo** |**Interfaz** |**Dirección IP** |**Máscara de subred** |
| :-: | :-: | :-: | :-: |
|S1 |VLAN 1 |192\.168.1.253 |255\.255.255.0 |
|S2 |VLAN 1 |192\.168.1.254 |255\.255.255.0 |
|PC1 |NIC |192\.168.1.1 |255\.255.255.0 |
|PC2 |NIC |192\.168.1.2 |255\.255.255.0 |
# **Objetivos** 
**Parte 1: Realizar una configuración básica en S1 y S2** 

**Paso 2: Configurar las PC** 

**Parte 3: Configurar la interfaz de administración de switches** 
# **Aspectos básicos** 
En esta actividad, primero creará una configuración básica de conmutador. A continuación, implementará conectividad básica mediante la configuración de la asignación de direcciones IP en switches y PC. Cuando se complete la configuración de direccionamiento IP, usarás varios comandos **show** para verificar la configuración y usará el comando **ping** para verificar la conectividad básica entre dispositivos. 
# **Instrucciones 1. Realiza una configuración básica en el S1 y el S2** 
Complete los siguientes pasos en el S1 y el S2. 



**Configura un nombre de host en el S1.** 

1. Haz clic en S1 y luego en la ficha CLI. 

   ![](Aspose.Words.4a04a952-2312-4885-bf35-5d11a6786cc3.002.png)

1. Introduce el comando correcto para configurar el nombre de host S1. 

   ![](Aspose.Words.4a04a952-2312-4885-bf35-5d11a6786cc3.003.png)

**Configura la consola y las contraseñas cifradas de modo EXEC privilegiado.**  

1. Usa **checha** como la contraseña de la consola. 

   ![](Aspose.Words.4a04a952-2312-4885-bf35-5d11a6786cc3.004.png)

1. Usa **jeka** para la contraseña del modo EXEC privilegiado. 

   ![](Aspose.Words.4a04a952-2312-4885-bf35-5d11a6786cc3.005.png)

**Verifica la configuración de contraseñas para el S1.** 

Pregunta: 

¿Cómo puedes verificar que ambas contraseñas se hayan configurado correctamente? 

Se puede verificar de dos formas, saliendo y entrando con la contraseña y a la vez ingresando a la RAM con show running-config (**sh run**).

![](Aspose.Words.4a04a952-2312-4885-bf35-5d11a6786cc3.006.png)

**Configura un aviso de MOTD.** 

Utiliza un texto de aviso adecuado para advertir contra el acceso no autorizado. El siguiente texto es un ejemplo: 

**Acceso autorizado únicamente. Los infractores se procesarán en la medida en que lo permita la ley.** 

![](Aspose.Words.4a04a952-2312-4885-bf35-5d11a6786cc3.007.png)

![](Aspose.Words.4a04a952-2312-4885-bf35-5d11a6786cc3.008.png)

**Guarda el archivo de configuración en la NVRAM.** 

Pregunta: 

¿Qué comando emite para realizar este paso? 

Se emite el comando copy running-config startup-config (**wr**)

![](Aspose.Words.4a04a952-2312-4885-bf35-5d11a6786cc3.009.png)





**2. Repita los pasos 1 a 5 para el S2.** 
# **Configurar las PC** 
Configura la PC1 y la PC2 con direcciones IP. 

**Configura ambas PC con direcciones IP.** 

1. Haz clic en PC1 y luego en la ficha Escritorio. 

   ![](Aspose.Words.4a04a952-2312-4885-bf35-5d11a6786cc3.010.png)

1. Haz clic en Configuración de IP. En la tabla de direccionamiento anterior, puede ver que la dirección IP para la PC1 es 192.168.1.1 y la máscara de subred es 255.255.255.0. Introduzca esta información para la PC1 en la ventana Configuración de IP. 

   ![](Aspose.Words.4a04a952-2312-4885-bf35-5d11a6786cc3.011.png)

1. Repite los pasos 1a y 1b para la PC2. 

   ![](Aspose.Words.4a04a952-2312-4885-bf35-5d11a6786cc3.012.png)

**Prueba la conectividad a los switches.** 

1. Haz clic en PC1. Cierre la ventana Configuración de IP si todavía está abierta. En la ficha Escritorio, haga clic en Símbolo del sistema. 

   ![](Aspose.Words.4a04a952-2312-4885-bf35-5d11a6786cc3.013.png)

1. Escribe el comando **ping** y la dirección IP para S1 y presione Enter. 

   Packet Tracer PC Línea de comandos 1.0 PC> **ping 192.168.1.253** 

   ![](Aspose.Words.4a04a952-2312-4885-bf35-5d11a6786cc3.014.png)

Pregunta: 

¿Tuviste éxito? Explica. 

No, puesto que falta configurar la dirección ip de switches.


3. # **Configura la interfaz de administración de switches** 
Configura el S1 y el S2 con una dirección IP. 

**Configura el S1 con una dirección IP.** 

Los switches pueden usarse como dispositivos plug-and-play. Esto significa que no necesitan configurarse para que funcionen. Los switches reenvían información desde un puerto hacia otro sobre la base de direcciones de control de acceso al medio (MAC). 

Pregunta: 

Si este es el caso, ¿por qué lo configuraremos con una dirección IP? 

Porque es necesaria para enviar un mensaje a una determinada dirección y tener control de acceso al medio.

Usa los siguientes comandos para configurar el S1 con una dirección IP. 

S1# **configure terminal** 

Enter configuration commands, one per line.  Finalice con CNTL/Z. 

S1(config)# **interface vlan 1** 

S1(config-if)# **ip address 192.168.1.253 255.255.255.0** S1(config-if)# **no shutdown** 

%LINEPROTO-5-UPDOWN: Line protocol on Interface Vlan1, changed state to up S1(config-if)# 

S1(config-if)# **exit** 

S1# 

Pregunta: 

¿Por qué debe introducir el comando **no shutdown**? 

Para activar la dirección ip del switche



**Configura el S2 con una dirección IP.** 

Usa la información de la tabla de direccionamiento para configurar el S2 con una dirección IP. 

![](Aspose.Words.4a04a952-2312-4885-bf35-5d11a6786cc3.015.png)

**Verifica la configuración de direcciones IP en el S1 y el S2.** 

Usa el comando **show ip interface brief** para ver la dirección IP y el estado de todos los puertos y las interfaces del switch. También puede utilizar el comando **show running-config**. 

**Guarda la configuración para el S1 y el S2 en la NVRAM.** 

Pregunta: 

¿Qué comando se utiliza para guardar en la NVRAM el archivo de configuración que se encuentra en la RAM? 

Se utiliza el comando **wr**.

**Verifica la conectividad de la red.** 

Puedes verificar la conectividad de la red mediante el comando **ping**. Es muy importante que haya conectividad en toda la red. Se deben tomar medidas correctivas si se produce una falla. Desde la PC1 y la PC2, haga ping al S1 y S2. 



1. Haga clic en PC1 y luego en la ficha Escritorio. 

1. Haga clic en Símbolo del sistema. 

   ![](Aspose.Words.4a04a952-2312-4885-bf35-5d11a6786cc3.016.png)

1. Haga ping a la dirección IP de la PC2. 

   ![](Aspose.Words.4a04a952-2312-4885-bf35-5d11a6786cc3.017.png)

1. Haga ping a la dirección IP del S1. 

   ![](Aspose.Words.4a04a952-2312-4885-bf35-5d11a6786cc3.018.png)

1. Haga ping a la dirección IP del S2. 

   ![](Aspose.Words.4a04a952-2312-4885-bf35-5d11a6786cc3.019.png)

**Nota**: También usa el **ping** en la CLI del switch y en la PC2. 

Todos los ping deben tener éxito. Si el resultado del primer ping es 80%, inténtelo otra vez. Ahora debería ser 100%. Más adelante, aprenderá por qué es posible que un ping falle la primera vez. Si no puede hacer ping a ninguno de los dispositivos, vuelva a revisar la configuración para detectar errores. 

*Fin del documento*** 
Comunicación de Datos y Redes 

[ref1]: Aspose.Words.4a04a952-2312-4885-bf35-5d11a6786cc3.001.png
