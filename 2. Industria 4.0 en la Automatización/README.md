# Industria 4.0 en la Automatización:

[ARCHIVOS](https://drive.google.com/drive/folders/1YUnDwA5JcfBu2bErReBwxCYy-bW00Ioa?usp=sharing)

# Sensores y actuadores
A continuación se puede ver un diagrama simplificado de la fábrica donde a cada elemente se le asigna un TAG específico. De esta manera se puede identificar en la programación del Ladder y de NX. Los tags y la explicación de cómo se formaron y a qué corresponden se puede ver [aquí](https://github.com/JoanPinilla/APM_Toy3ST/blob/main/7.%20Controladores%20industriales%20(PLC)/TAGS.md).
![image](https://github.com/user-attachments/assets/032d87ee-057c-4483-bdbe-7f462e2c6f1b)

## Sensores
En toda la planta se usan sensores ópticos para hacer control de las bandas y otros actuadores, así como para llevar un registro de todas las piezas que se producen en las máquinas y las estaciones.

## Actuadores
La mayoría de los actuadores de la planta son las bandas transportadoras. Estas permiten optimizar el proceso de transporte y reducir el tiempo improductivo en el ciclo del producto.
Además de las bandas, están el par de celdas robóticas que consisten en un robot antropomórfico de 6 ejes, una pistón neumático que funciona como prensa y 3 bandas transportadores. Se discute sobre esta celda en más detalle [aquí](https://github.com/JoanPinilla/APM_Toy3ST/blob/main/5.%20Celda%20de%20Manufactura%20Robotizada/README.md)

# Acrquitectura de control
Se muestra la arquitectura de control de todo el proyecto en relación a la pirámide de automatización.

![image](https://github.com/user-attachments/assets/a197e8f8-1542-4461-8bdf-f4128b83b834)

## Nivel de campo
En el nivel de campo se encuentran los dos softwares de comunicación usados: Siemens NX y RobotStudio. El primero se encarga de la simulación de toda la planta y se comunica con LogixEmulate y RobotStudio a través de una conexión OPC DA y OPC UA respectivamente. 

## Nivel de control
La conexión entre NX y LogixEmulate sirve para que el PLC simulado se encargue del control de todos los actuadores y sensores de la simulación. La conexión de OPC UA entre LogixEmulate y RobotStudio sirve para que el robot simulado en RobotStudio le envíe las posiciones angulares de sus joints y para dar y recibir señales. Las posiciones angulares del robot se sincronizan con un ensamble en NX y las señales pueden ser de entrada para hacer que el robot empiece la rutina; o de salida, como por ejemplo una rutina finalizada o la señal para abrir y cerrar la prensa.

## Nivel SCADA
En este caso, Ignition es el software que sirve de SCADA y de puente para las comunicaciones OPC DA y OPC UA de Studio5000 y RobotStudio respectivamente. Las características de este sistema se discuten más a detalle [aquí](https://github.com/JoanPinilla/APM_Toy3ST/tree/main/8.%20SCADA#readme).

## Nivel MES
Como valor agregado al proyecto, se realizó un acercamiento a las funciones de un sistema MES a través de NodeRED y Google Sheets. Esta conexión se logró a través de OPC DA con NodeRED y la hoja de datos se sincroniza con a través de internet. Nuevamente, se habla del sistema MES con más detalle [aquí.]


# Industria 4.0
Las tecnologías y filosofías de industria 4.0 aplicadas a este proyecto fueron:
* Conectar completamente la pirámide de automatización: a través de las conexiones OPC UA y DA, se logó la completa integración del nivel de campo, de control, de supervisión e incluso de un acercamiento a un sistema MES.
* Gemelo digital: Hacer la validación digital de la planta tiene muchas ventajas a la hora de la puesta en marcha y permite hacer simulaciones de escenarios de producción para plantear diferentes estrategias
* Métricas en tiempo real: Gracias a la integración entre Studio5000 e Ignition, se logró hacer el conteo de todas las piezas producidas. Esto con el objetivo de enviar infromación al sistema MES sobre la cantidad de material usado en tiempo real y estimar el rendimiento de la planta a través de sus unidades producidas.
