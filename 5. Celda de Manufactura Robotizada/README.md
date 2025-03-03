# Celda de Manufactura Robotizada

[ARCHIVOS](https://drive.google.com/drive/folders/1__USViEgZ829f_1ReBlEpH1N4gLg5yfD?usp=drive_link)

Propuesta de automatización y Celda de Manufactura Robotizada

Nuestro proceso de automatización está diseñado para optimizar la eficiencia y precisión en la línea de producción. Comienza con una banda transportadora que traslada los productos de manera continua y sincronizada, eliminando cuellos de botella y reduciendo tiempos muertos. Luego, una celda robotizada se encarga del ensamble, realizando tareas complejas con alta precisión y repetibilidad, lo que garantiza calidad y consistencia en cada pieza. Finalmente, una máquina empacadora automática completa el proceso, empaquetando los productos de forma rápida y uniforme, lista para su distribución. Este sistema integrado no solo aumenta la productividad, sino que también reduce costos operativos y minimiza errores, asegurando un flujo de trabajo eficiente y escalable.

Automatización del proceso de ensamble:

SI hay un proceso que puede llegar a ser repetitivo, irregular y un punto crítico en la línea de producción de juguetes es el ensamble, que al ser realizado de forma manual no solo puede dar lugar a errores humanos realizados durante el proceso, sino también a irregularidades en los tiempos de producción y desgaste físico en los operarios, por lo cual se decidió automatizar este proceso por medio de una celda robótica, la cual nos permite realizar este proceso de una forma rápida, uniforme y precisa.

Hoja de ruta:

![image](https://github.com/user-attachments/assets/3f1da306-e5a7-49ee-8966-f2094e729d8a)

Selección de componentes:

Partiendo del hecho de que el robot tendrá la tarea de ensamblar piezas realizara dos operaciones principales, una de ellas es realizar un pick and place donde tomara dos piezas distintas de dos bandas y la otra será hacer el acople de dos piezas sin necesidad de tornillos ni soldaduras (ya que las piezas se realizaron para evitar este tipo de juntas por seguridad del usuario final) entregando un juguete ya ensamblado y listo para su empaque. En todo este proceso se demora 25 segundos recibiendo dos piezas y entregando un juguete completo.

Lista de componentes 
Robot ABB IRB 1200: robot de 5kg de fuerza con un alcance de 0.9m

![image](https://github.com/user-attachments/assets/fdcff357-de3e-4365-9ae8-2944c8ee3501)

SCHUNK - Single Gripper JGP-P 80-1 ABB kit: griper neumático con 10mm de recorrido y una fuerza de hasta 500 N.

![image](https://github.com/user-attachments/assets/2427d458-c62a-4c07-8ed5-fc865e8e8b3e)

Cilindro neumático DSNU-S con recorrido de 20mm a 8 bar y una fuerza de 100N

![image](https://github.com/user-attachments/assets/e9eaffc5-5f55-42a3-bc00-e8599207892e)
 
Compresor 24 Litros 115psi Karson: con una capacidad de flujo de 182L/m y 1.5 HP.

![image](https://github.com/user-attachments/assets/e076fc68-ba78-4050-983a-e1a1199195d1)

Manguera de poliuretano de 4mm
Válvula Solenoide 3/2 FESTO VUVS
electroválvula 5/2
bandas de PVC de 433 mm de ancho y con motor de 1HP.
Diseño de la celda
En esta celda lo que se busca es que un robot tome una pieza de la banda de pieza inferior que viene por delante de el la coloque sobre una prensa neumática, recoja la pieza superior, acople las dos piezas, la prensa se suelte y lleve el juguete completo a la banda de empaque

![image](https://github.com/user-attachments/assets/605255db-4bfd-46b1-87a2-2102355b4d49)

 
Para esto se colocan los robots en medio de las 3 bandas con la prensa delante como se puede ver en la imagen a continuación

![image](https://github.com/user-attachments/assets/bb0d5583-3b06-485e-b54f-2eb25e445cf3)

 
Se coloca de tal manera que el robot tenga alcance de las tres bandas, especialmente la de la parte inferior que es la mas lejana por lo cual se opto por un robot con un alcance de 0.9m y un peso de 5Kg para que a pesar del bajo peso de los productos se tenga un factor de seguridad en las posiciones más lejanas donde los momentos son más altos, donde al final la distribución quedo de la siguiente manera donde las dos celdas robóticas quedaron dentro de la misma celda de contención de 3.45m x 2.36m.

![image](https://github.com/user-attachments/assets/077fe763-b5da-4ccf-a811-92673cb970ae)
![image](https://github.com/user-attachments/assets/3ccb9cc6-001b-4794-a8ec-7db6eeeb2906)



Medidas de seguridad:
Realizamos un análisis de riesgos por medio del método HRN donde se evaluaron los riesgos asociados a la celda robótica y se le dieron solución a los mismos y se enumeraron los componentes necesarios para cada una de las medidas de prevención de riesgo:

![image](https://github.com/user-attachments/assets/4cf28000-342f-459d-9ccd-7d85f123a190)

  
