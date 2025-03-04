# Controladores Industriales (PLC)

### Desarrollo y Programación de PLCs para Automatización Industrial

Esta sección, dedicada a los Controladores Industriales se enfoca en la configuración y programación de sistemas de control lógico programable (PLC) para la automatización y gestión de nuestra planta de producción de juguetes. Para esto partiremos del despliegue de los sensores y actuadores presentes en la planta, seguido del desarrollo de un diagrama de flujo general mediante el método paso a paso y el enfoque GRAFCET, para posteriormente realizar un desgloce, nuevamente en diagrama GRAFCET de cada subsistema con el fin de lograr una visualización clara y de allí poder realizar una programación precisa del sistema.

La codificación en ladder, basada en estos diagramas, se lleva a cabo en Studio 5000, donde se utilizan subrutinas y saltos para organizar el código principal. Este proceso se realiza en un entorno simulado con Logix Emulate, lo que facilita la integración y verificación del PLC antes de su implementación física. 

## Desarrollo de Sistemas PLC

### 1. Identificación de sensores y actuadores
- **Diagrama de TAGS** En el siguiente diagrama, no solo se abstrae la organización del sistema junto con la ubicación de las máquinas, bandas y sensores sino que tambien se explica la creación del codigo de pseudo nombres que se utilizo para la organización del flujo de trabajo.

### 2. GRAFCET general
- **Diagrama GRAFCET general** A continuación se presenta el diagrama GRAFCET inicial donde se plasma el flujo de la operación de la planta, aquí no se presentan señales de los sensores ni de los actuadores presentes pero si permite conceptualizar en un primer momento lo que sucede en el nivel de operación.

![image](https://github.com/user-attachments/assets/16210334-d53b-4ea7-ae6d-3a9eb4b8931f)


### 3. Grafcet por rutina y subrutina
- **Diagrama GRAFCET general detallado** Ahora bien, tomando como suministro el diagrama GRAFCET anteriormente presentado, es posible extender el concepto para visualizar al interior de cada subrutina que es lo que sucede, en el caso de maquinaria, no se hace enfasis puesto que la premisa será que esta sección solo encendera toda la maquinaria, para el caso de las bandas es dentro de ellas donde ocurre la mayor extensión.
  
![image](https://github.com/user-attachments/assets/aded6d88-5f3d-4f0d-9844-0aa4f9cae2fc)


Aquí podemos evidenciar que aparecen varias rutinas nuevas, haciendo referencia cada una a cada sección productiva de la planta, de izquierda a derecha tendremos la fabricación de las piezas del carro, tanque, helicoptero y transmisión, posteriormente aparece  la rutina de las bandas que deben alimentar a las estaciones de ensamble del robot donde se desprende tanto el robot de la izquierda o RobotA y el de la derecha RobotB, tambien tenemos finalmente la rutina de las bandas que alimentan las maquinas empacadoras.

- **Diagrama GRAFCET - Rutina de bandas de la sección CARRO, TANQUE Y HELICOPTERO** Por como esta constituida la planta y como desde un principio ha sido la fabricación, la sección de carros, tanques y helicopteros cuentan con la misma cantidad de inyectoras, bandas, estaciones de ensamble y de desbarbado, por lo que a continuación se presenta el diagrama GRAFCET de control de la sección "Carros" que es homoloable para las otras dos secciones anteriormente mensionadas:

![image](https://github.com/user-attachments/assets/9616b87b-53e8-40ae-b40c-74de37035c8f)

Aquí podemos ver que cada una de las bandas, conectadas a cada una de las inyectoras, se enciende una vez el sensor optico de entrada detecta que hubo una primera pieza, y que estas no se apagan hasta que la bandera de bloqueo de la banda se enciende, lo cual ocurre cuando la capacidad de la estación de desbarbado esta completa, una vez se soluciona la cola, es posible continuar y vuelve a comenzar la subrutina

- **Diagrama GRAFCET - Rutina de bandas de la sección TRANSMISIÓN**  
  En esta sección, el proceso de fabricación involucra solo dos máquinas: una cortadora y una inyectora. A pesar de la diferencia en cantidad de equipos, el principio de operación de las bandas sigue la misma lógica utilizada en la sección de Carros, Tanques y Helicópteros.  

![image](https://github.com/user-attachments/assets/7aec3c3f-4a68-4229-bc94-c9148db2422f)


  En este caso, cada banda está conectada a su respectiva máquina y se activa cuando el sensor óptico de entrada detecta la primera pieza procesada. La banda permanecerá en funcionamiento hasta que la bandera de bloqueo se active, lo que ocurre cuando la capacidad de la cortadora está completa. Una vez se resuelve la congestión, la rutina reinicia el ciclo y permite la continuidad del proceso de manufactura.  

- **Diagrama GRAFCET - Rutina de bandas de la sección ROBOTS**

La siguiente información presenta el diagrama GRAFCET del ensamble central realizado por robots, este par de robots es alimentado por 4 bandas en pares de 2, que deben ser controladas de manera individual, estas bandas se encienden al percibir por su sensor de entrada una pieza resultado de un ensamble o estación de desbarbado previo, y una vez llevan la pieza hasta las inmediaciones del robot, la banda debe ser apagada para que el Robot pueda tomar la pieza.
  
![image](https://github.com/user-attachments/assets/4417bb62-2f28-42d6-b8e5-18dfc5c0d143)

Una vez ambos sensores de salida de la banda son activados para cada robot, la rutina del robot debe ser activada; dicha rutina acaba dejando la pieza en una tercera banda, la cual, su sensor de entrada envia la señal al robot para que vuelva a HOME, y de esta manera este listo nuevamente para repetir el ciclo.

- **Diagrama GRAFCET - Rutina de bandas de la sección PACKING**  
  La sección de Packing opera con tres máquinas empacadoras las cuales son alimentadas desde un ensamble anterior, siguiendo el mismo principio de control de bandas empleado en las otras áreas de producción.  

![image](https://github.com/user-attachments/assets/a551f89d-3579-4fe7-9744-814bc467cb12)

  Aquí, cada empacadora cuenta con su propia banda transportadora, la cual se activa tras la detección de un ensamble depositado en la banda mediante un sensor óptico. Estas bandas continúan funcionando hasta que la capacidad de la empacadora se llena, momento en el que la bandera de bloqueo se activa. Una vez se resuelve la operación de la maquina, el proceso se reinicia.  


### 4. Programación en Ladder
La programación del PLC se realizo por medio de lenguaje LADDER teniendo como suministro los anteriores diagramas GRAFCET, pero como diferencias, primero se añadieron más subrutinas que sin añadir más contenido, ayudan a la organización y permiten una mayor claridad y manejo del programa; tambien, como suministro para el sistema SCADA se añadieron diferentes contadores y timer que permiten controlar y supervisar la operación en tiempo real. El codigo Ladder se presenta a continuación por cada rutina junto con los comentarios sobre cada variable para guiar al lector.

- **Main Routine**
  
![image](https://github.com/user-attachments/assets/f0695bfc-d52a-4c75-9af3-bdeb76f5cb0c)

- **Maquinas**

![image](https://github.com/user-attachments/assets/d0ae4780-ef6f-454c-9b28-4576d24d3490)

- **Bandas**

![image](https://github.com/user-attachments/assets/6b314875-f11f-464f-a0a9-ce9ee9535ccc)

- **Car**

![image](https://github.com/user-attachments/assets/7adcf21f-eeca-4a2e-9ad6-1972e7d5c31d)

- **Hel**
  
![image](https://github.com/user-attachments/assets/8c8e2690-c24b-483d-bb78-de64d573a600)

- **Tank**

![image](https://github.com/user-attachments/assets/6a5f0bf1-6350-482c-8165-bde0458f4a5c)

- **To Robot**

![image](https://github.com/user-attachments/assets/0dc497dd-fdf0-4d59-986e-b711e7444d92)
![image](https://github.com/user-attachments/assets/42a590b2-58e9-4c02-aeb8-49330eaaedec)
![image](https://github.com/user-attachments/assets/c9e98029-9043-48f9-a8ae-5c94608bd7af)

- **Trans**  

![image](https://github.com/user-attachments/assets/52ed0280-9aea-400e-9b4f-263cb0ff6c52)

- **Packing**
  
![image](https://github.com/user-attachments/assets/99aa0a9e-0c08-4731-b367-ab6da0c726cb)
![image](https://github.com/user-attachments/assets/20b955a2-41e8-49b9-9ec8-a998c5a3c936)

- **Contadores**
  
![image](https://github.com/user-attachments/assets/7ec58223-cd08-42b3-b4b3-fb9af00d0353)
![image](https://github.com/user-attachments/assets/ff40e0f9-4877-45d5-ac14-0377c5a2c0a8)
![image](https://github.com/user-attachments/assets/366e3132-cb14-4bc6-ab3d-810074178d91)

- **Bloqueo**
  
![image](https://github.com/user-attachments/assets/cada4dfd-4fba-4020-a488-c4f0d0b6895e)
![image](https://github.com/user-attachments/assets/3daf81a0-7588-4e9d-960a-0aace46aa24b)
![image](https://github.com/user-attachments/assets/b5aed4cb-7df4-4087-aa45-9578d5f0cde9)
![image](https://github.com/user-attachments/assets/fc96436c-3ef4-4d7d-a798-ee9e70a2e13b)

- **Robot A**

![image](https://github.com/user-attachments/assets/3daca496-74ad-4d67-86d1-2585c0037be5)

- **Robot B**

![image](https://github.com/user-attachments/assets/94eec001-2e24-46d9-a08a-c3a7658d2a68)

- **Stop Routine**

![image](https://github.com/user-attachments/assets/ce6af0c9-1e14-4b87-ba18-50d4b3d5979e)
![image](https://github.com/user-attachments/assets/7d41aa0d-a720-4248-853b-9453daa580d5)

- **Master Stop**
  
![image](https://github.com/user-attachments/assets/811954f2-6452-411a-be49-f96dbead85d8)
