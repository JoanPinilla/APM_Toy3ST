# Controladores Industriales (PLC)

### Desarrollo y Programación de PLCs para Automatización Industrial

Esta sección, dedicada a los Controladores Industriales se enfoca en la configuración y programación de sistemas de control lógico programable (PLC) para la automatización y gestión de nuestra planta de producción de juguetes. Para esto partiremos del despliegue de los sensores y actuadores presentes en la planta, seguido del desarrollo de un diagrama de flujo general mediante el método paso a paso y el enfoque GRAFCET, para posteriormente realizar un desgloce, nuevamente en diagrama GRAFCET de cada subsistema con el fin de lograr una visualización clara y de allí poder realizar una programación precisa del sistema.

La codificación en ladder, basada en estos diagramas, se lleva a cabo en Studio 5000, donde se utilizan subrutinas y saltos para organizar el código principal. Este proceso se realiza en un entorno simulado con Logix Emulate, lo que facilita la integración y verificación del PLC antes de su implementación física. 

## Desarrollo de Sistemas PLC

### 1. Identificación de sensores y actuadores
- **Diagrama de TAGS** En el siguiente diagrama, no solo se abstrae la organización del sistema junto con la ubicación de las máquinas, bandas y sensores sino que tambien se explica la creación del codigo de pseudo nombres que se utilizo para la organización del flujo de trabajo.

### 2. GRAFCET GENERAL
- **Diagrama GRAFCET general** A continuación se presenta el diagrama GRAFCET inicial donde se plasma el flujo de la operación de la planta, aquí no se presentan señales de los sensores ni de los actuadores presentes pero si permite conceptualizar en un primer momento lo que sucede en el nivel de operación.

- ![image](https://github.com/user-attachments/assets/16210334-d53b-4ea7-ae6d-3a9eb4b8931f)


### 3. Conversión a GRAFCET
- **Objetivo:** Reestructurar los diagramas de flujo en formato GRAFCET para facilitar su implementación en lógica programada.
- **Requisitos:** Diagramas de flujo validados.

### 4. Programación en Ladder
- **Objetivo:** Implementar la lógica de control en Studio 5000 mediante subrutinas y estructuras organizadas en Logix Emulate.
- **Requisitos:** Diagramas GRAFCET optimizados.

### 5. Selección de Hardware PLC
- **Objetivo:** Evaluar y escoger PLCs, DCS o PAC según los requerimientos operativos y de procesamiento.
- **Requisitos:** Análisis de tiempos de respuesta y compatibilidad con sensores.

### 6. Evaluación de Seguridad
- **Objetivo:** Incorporar redundancia y mecanismos de seguridad en el sistema de control.
- **Requisitos:** Normativas de seguridad y análisis de riesgos.

### 7. Ajustes Finales y Optimización
- **Objetivo:** Revisión de costos, eficiencia del sistema y validación final para implementación física.
- **Requisitos:** Presupuesto disponible y ajustes de seguridad.

## Implementación y Simulación
Se realizarán pruebas en un entorno virtual utilizando TIA Portal y Siemens NX para validar la funcionalidad antes del despliegue físico, asegurando una transición eficiente y sin riesgos operacionales.
