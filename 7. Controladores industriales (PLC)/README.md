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

- **Diagrama GRAFCET - Rutina de bandas de la sección PACKING**  
  La sección de Packing opera con tres máquinas empacadoras las cuales son alimentadas desde un ensamble anterior, siguiendo el mismo principio de control de bandas empleado en las otras áreas de producción.  

![image](https://github.com/user-attachments/assets/a551f89d-3579-4fe7-9744-814bc467cb12)

  Aquí, cada empacadora cuenta con su propia banda transportadora, la cual se activa tras la detección de un ensamble depositado en la banda mediante un sensor óptico. Estas bandas continúan funcionando hasta que la capacidad de la empacadora se llena, momento en el que la bandera de bloqueo se activa. Una vez se resuelve la operación de la maquina, el proceso se reinicia.  


### 4. Programación en Ladder
- **Main Routine**

## Implementación y Simulación
Se realizarán pruebas en un entorno virtual utilizando TIA Portal y Siemens NX para validar la funcionalidad antes del despliegue físico, asegurando una transición eficiente y sin riesgos operacionales.
