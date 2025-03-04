# SCADA

[ARCHIVOS](https://drive.google.com/drive/folders/1TnPqE6KaKf5XbkpvsdCBDhcv3kqK7Lac?usp=sharing)

# Operación
![image](https://github.com/user-attachments/assets/019c4b06-2563-4701-a4a4-9cc05f0f5fc8)
En esta pantalla están los botones de START, STOP y STOP DE EMERGENCIA. Además, se puede manipular cada actuador y cada máquina de la planta de manera independiente. Esto es útil para el balanceo de línea o cuando hay pedidos grandes de uno o dos tipos de productos, pero no de los 3 simultáneamente.

# Alarmas
![image](https://github.com/user-attachments/assets/ec51b16d-109a-40e4-9568-28ca50c80187)
En este caso, cada actuador tiene un indicador LED visual que indica si está activo o no. Además, la pantalla de alarmas también reporta en tiempo real la posición angular de cada joint de ambos robots.

# Datos e Históricos
![image](https://github.com/user-attachments/assets/c06ac1d7-324d-4d32-ada1-aa8735578c98)
Como última pantalla del sistema SCADA se tiene la de datos e históricos, donde se puede ver máquina a máquina la cantidad de piezas que ha producido. Se observan gráficas que indican la tendencia de la producciónde cada poroducto durante la última hora. Adicionalmente, se tiene un bootón de sincronizado y 3 barras de progreso. Estos elementos tienen que ver con la exploración de un sistema MES a través de Google Sheets y NodeRED. El estado del botón de sincronizar es leído constantemente por NodeRED. Cuando se oprime el botón, se toman los datos de celdas específicas en la hoja de cálculo MES de Toy3ST, específicamente, de la suma total de órdenes de cada producto. 
![image](https://github.com/user-attachments/assets/4ad2a094-d001-4460-9bfd-6601ac4f43d1)

# Sistema MES
Se realiza un acercamiento simple hacia las funciones principales de un sistema MES. La primera de las funciones es la de administrar las órdenes de producción. Esta hoja de cálculo se conecta directamente con el sistema SCADA para darle una meta diaria de producción a la panta de acuerdo al número de productos de cada tipo que se requiran.
![image](https://github.com/user-attachments/assets/b962daf3-fd60-465c-992f-a63f05267bdc)

La segunda función que realiza este sistema MES es la de llevar y administrar el inventario de materias primas. En este caso, se contempla el plástico de cada color y de alarmbre para los ejes. Al principio de cada día se cuenta con un material disponible, pero a medida que avanza la producción se va consumiendo materia prima. Esta se calcula de acuerdo al número de piezas producidas por color, que es un dato que se obtiene directamente de los sensores en las bandas a la salida de cada máquina y la suma por colores que realiza el PLC. Esta conexión directa entre el nivel de campo y el nivel MES demuestra la aplicación de paradigmas de la industria 4.0. 
![image](https://github.com/user-attachments/assets/207ad61b-3919-40fc-b966-b393f68f9b1c)


