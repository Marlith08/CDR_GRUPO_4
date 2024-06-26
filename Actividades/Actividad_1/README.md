﻿
<img src="https://github.com/Marlith08/CDR_GRUPO_4/blob/main/Actividades/Actividad_1/IMAGENES/Aspose.Words.01c9ed49-c098-4c18-a904-600dcfbefe17.001.png" alt="ref1" width="300" height="100">


**<p align="center"> **Departamento Académico de Ingeniería C8280 -Comunicación de Datos y Redes** </p>**


# **Actividad 1: Creación de una red simple** 


Para completar este laboratorio vamos a utilizar Cisco Packet Tracer 
## **Topología** 
![](https://github.com/Marlith08/CDR_GRUPO_4/blob/main/Actividades/Actividad_1/IMAGENES/Aspose.Words.01c9ed49-c098-4c18-a904-600dcfbefe17.002.png) 
## **Tabla de direccionamiento** 

|**Dispositivo** |**Interface** |**Dirección IP** |**Máscara de subred** |
| :- | :-: | :-: | :- |
|PC-A |NIC |192\.168.1.10 |255\.255.255.0 |
|PC-B |NIC |192\.168.1.11 |255\.255.255.0 |
## **Objetivos** 
**Parte 1: Configuración de la topología de la red**  

- Identificar los dispositivos de red y construir una red simple con Packet Tracer. - 	Realizar el cableado de una topología de red. 

**Parte 2: Configuración de hosts en las PC** 

- Introducir la información de dirección IP estática en la interfaz LAN de los hosts. 
- Verificar que las PC puedan comunicarse por medio de la utilidad **ping**. 
## **Información básica/situación** 
Las redes están formadas por tres componentes principales: hosts, switches y routers. En este laboratorio, armará una red simple con dos hosts y un switch. En esta práctica de laboratorio, aplicará la asignación de direcciones IP a las PC para habilitar la comunicación entre estos dos dispositivos. Use la utilidad **ping** para verificar la conectividad. 

**Nota**: Los switches que se usan son Cisco Catalyst 2960 con Cisco IOS Release 15.0(2) (imagen lanbasek9).  

Se pueden utilizar otros switches y otras versiones de Cisco IOS. 
## **Recursos necesarios** 
- 1 switch (Cisco 2960 con Cisco IOS versión 15.0(2), imagen lanbasek9 o similar) 
- 2 PC (Windows 10) 
- cables Ethernet como se muestra en la topología. 



Paso 1: Construye la red simple configurando cada uno de los dispositivos dados. 

Comunicación de Datos y Redes 


### ![ref1]**Departamento Académico de Ingeniería C8280 -Comunicación de Datos y Redes** 




1. En la interfaz de Packet Tracer selecciona los dispositivos dados: Switch 2960.  

   ![](https://github.com/Marlith08/CDR_GRUPO_4/blob/main/Actividades/Actividad_1/IMAGENES/Aspose.Words.01c9ed49-c098-4c18-a904-600dcfbefe17.003.png)

1. Click en el dispositivo y en la pestaña Config, Display Name, Hostname Cambia el nombre a S1. 

   ![](https://github.com/Marlith08/CDR_GRUPO_4/blob/main/Actividades/Actividad_1/IMAGENES/Aspose.Words.01c9ed49-c098-4c18-a904-600dcfbefe17.004.png)![]([Aspose.Words.01c9ed49-c098-4c18-a904-600dcfbefe17.005.png](https://github.com/Marlith08/CDR_GRUPO_4/blob/main/Actividades/Actividad_1/IMAGENES/Aspose.Words.01c9ed49-c098-4c18-a904-600dcfbefe17.005.png))

1. Realiza el mismo procedimiento para los otros dispositivos. Llamalos PC-A, PC-B respectivamente 

   ![](https://github.com/Marlith08/CDR_GRUPO_4/blob/main/Actividades/Actividad_1/IMAGENES/Aspose.Words.01c9ed49-c098-4c18-a904-600dcfbefe17.006.png)

1. Selecciona el ícono Rayo de conexiones y escoge Copper Straight-Through.  
1. Conecte un extremo de un cable Ethernet al puerto de NIC en PC-A. Conecte el otro extremo del cable a F0/6 en S1. Después de conectar la PC al switch, la luz de F0/6 debería tornarse ámbar y luego verde, lo que indica que la PC-A se conectó correctamente.  
1. ![]([Aspose.Words.01c9ed49-c098-4c18-a904-600dcfbefe17.007.png](https://github.com/Marlith08/CDR_GRUPO_4/blob/main/Actividades/Actividad_1/IMAGENES/Aspose.Words.01c9ed49-c098-4c18-a904-600dcfbefe17.007.png))
1. Conecte un extremo de un cable Ethernet al puerto de NIC en PC-B. Conecte el otro extremo del cable a F0/1 en S1. Después de conectar la PC al switch, la luz de F0/1 debería tornarse ámbar y luego verde, lo que indica que la PC-B se conectó correctamente.  

` 	`![](https://github.com/Marlith08/CDR_GRUPO_4/blob/main/Actividades/Actividad_1/IMAGENES/Aspose.Words.01c9ed49-c098-4c18-a904-600dcfbefe17.008.png)

Paso 2: Verifique la configuración y la conectividad de la PC. 

Use la línea de comandos para verificar la configuración de la PC y la conectividad. a. Desde PC-A, haga clic y Desktop seleccione **Command Prompt**. 

2. En la ventana de comandos de packet tracer, puedes introducir comandos directamente en la PC y ver los resultados de esos comandos. Verifique la configuración de la PC mediante el comando **ipconfig /all**. Este comando muestra información sobre el nombre del host de la PC y la dirección IPv4. 

   ![](https://github.com/Marlith08/CDR_GRUPO_4/blob/main/Actividades/Actividad_1/IMAGENES/Aspose.Words.01c9ed49-c098-4c18-a904-600dcfbefe17.009.png)

2. Escriba **ping 192.168.1.11** y presione Intro. 

   ![](Aspose.Words.01c9ed49-c098-4c18-a904-600dcfbefe17.010.png)

   ¿Fueron correctos los resultados del ping? Sí, puesto que presenta una información que envía datos, pero que no los recibe esto se puede deber que falta la conectividad mediante la ip a otro dispositivo.

 

2. Repite los pasos anteriores para PC-B 

   ![](https://github.com/Marlith08/CDR_GRUPO_4/blob/main/Actividades/Actividad_1/IMAGENES/Aspose.Words.01c9ed49-c098-4c18-a904-600dcfbefe17.011.png)

   ¿Fueron correctos los resultados del ping? Sí, puesto que presenta una información que envía datos, pero que no los recibe esto se puede deber que falta la conectividad mediante la ip a otro dispositivo.

   ![](https://github.com/Marlith08/CDR_GRUPO_4/blob/main/Actividades/Actividad_1/IMAGENES/Aspose.Words.01c9ed49-c098-4c18-a904-600dcfbefe17.012.png)

   **Nota**: Si no obtuvo una respuesta de PC-B, intente hacer ping a PC-B nuevamente. Si sigue sin obtener respuesta de PC-B, intente enviar un comando ping a PC-A desde PC-B.** 



![](https://github.com/Marlith08/CDR_GRUPO_4/blob/main/Actividades/Actividad_1/IMAGENES/Aspose.Words.01c9ed49-c098-4c18-a904-600dcfbefe17.013.png) 

<sup>1</sup> Esta actividad está basada en el curso Networking Essential de  Cisco y/o sus filiales. Todos los derechos reservados. 

Comunicación de Datos y Redes 
