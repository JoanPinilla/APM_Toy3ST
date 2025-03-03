# Gestión de producción y automatización

[ARCHIVOS](https://drive.google.com/drive/folders/1Z3YmBvwmxOz1VESsb6aUUCm6mJurlJfT?usp=sharing)

## 1. Gestión de producción  
   ### 1.1 Simulación proceso sin automatizar

Para esta planta se necesitaron varias líneas de producción que se van juntando hasta llegar al producto final, se empieza por una línea donde se cortan los ejes y se ensamblan con lo producido por la inyectora de llantas que produce cuatro llantas en cada moldada luego pasa por un proceso de desbarbado manual para luego ser ensamblado y llevado a las líneas del tanque y el carro, luego estas dos líneas tienen procesos similares donde se generan por inyección dos piezas de la parte inferior de los vehículos se desbarban y se ensamblan con la transmisión para luego ensamblarse con una tercera pieza superior y luego se llevan a empaquetado. Con el helicóptero ya no hay dependencia de la transmisión por lo que se inyectan tres piezas, se desbarban, se ensamblan y empacan. En esta planta las maquinas que se tienen son las inyectoras y las dos bandas que llevan las transmisiones, el resto de los procesos se realizan de forma manual.

<p align="center">
  <img src="https://github.com/user-attachments/assets/9102b2cd-2825-4adb-a8ea-5d246f7ea38a" width="500"/>
</p>

Con esta configuración, al mes se producen 16.321 juguetes en total donde se llegan a producir 2390 tanques, 3094 carros y 10837 helicópteros, donde se puede ver la primera área de oportunidad de la planta y es la falta de homogeneidad en la planta ya que la dependencia del tanque y del carro a las transmisiones genera un gran retraso en la producción de ambos productos ya que no se generan suficientes transmisiones para realizar una producción constante

<p align="center">
  <img src="https://github.com/user-attachments/assets/223f847d-865b-4284-ab02-bd01aaa7c4bd" width="500"/>
</p>

También se obtuvieron los indicadores de estado de cada una de las estaciones del proceso y lo que primero se logra observar son los grandes tiempos de espera que tienen las estaciones de ensamble ya que ya sea por falta de piezas o por los tiempos de transporte de los operarios al estar caminando de un lugar a otro no se logra hacer un proceso de ensamble del todo eficiente lo que aporta a la falta de homogenización de la planta y hace que se generen bloqueos y colas en la producción como se puede ver en los gráficos.

<p align="center">
  <img src="https://github.com/user-attachments/assets/badc198a-89ad-4c83-ac6a-d036d210bdb5" width="500"/>
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/4130cb49-d3d2-4252-ac47-727fb6e92b17" width="500"/>
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/d514ee36-93fd-4bfc-a61d-e5f4e8ce4a3b" width="500"/>
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/9f83a7d0-cb2c-4654-ad74-9332c4a1aefe" width="500"/>
</p>

   ### 1.2 Vsm proceso sin automatizar  
   ### 1.3 Simulación proceso automatizado


<p align="center">
  <img src="https://github.com/user-attachments/assets/cf9932f3-80b6-4603-9ae0-529f89b7a744" width="500"/>
</p>
Para el planteamiento final de la planta, que básicamente se trataba de una reimaginación de todo el proceso inicial, se tuvieron en cuenta varios principios ordenadores. El primero de ellos era que se buscaba mantener la maquinaria de inyección y corte original, así como el número de empleados originales de la planta, pero esta vez destinándolos a puestos que sí generaran valor al producto. A través de la inserción de maquinaria altamente tecnificada y automatización, se buscaba aumentar la producción de tal manera que la empresa pudiera ser más presente y fuerte en el mercado, a la vez que reducían los precios de venta para hacerlos más competitivos.

<p align="center">
  <img src="https://github.com/user-attachments/assets/8831169a-aa1a-4514-bd67-372ca7764c50" width="500"/>
</p>

Siguiendo el diseño de una celda de manufactura tipo Peine, se buscó crear una línea central de trabajo y producción a la que, desde los lados, se añadieran piezas o procesos de valor en los puntos de ensamblaje. Esto permitió integrar nuevas estaciones de ensamble que no existían en la planta original y que descongestionan y aceleran el proceso, además de incorporar un robot antropomórfico encargado del ensamblaje final de dos de nuestros vehículos: el carro y el tanque, que previamente eran los más rezagados en producción.  
Adicionalmente, para crear una simulación adecuada de la planta, se tuvieron en cuenta varios tiempos. Para la maquinaria, los tiempos de fallo se asociaron al tiempo necesario para reparar un fallo, que se fijó en 2 horas, mientras que el tiempo de establecimiento de moldes de inyección, home del robot y precarga de la máquina de corte se fijó en una hora. Por parte del personal, se consideró que un fallo es una incapacidad de un turno laboral completo de 8 horas y el tiempo de establecimiento se estableció en 20 minutos para que los trabajadores pudieran ubicarse y prepararse al inicio del turno. Estos fallos se generaron de manera aleatoria durante el tiempo de simulación, fijado en un mes de trabajo o 22 días hábiles, con una probabilidad del 95-97% para la maquinaria y del 90% para los trabajadores.

<p align="center">
  <img src="https://github.com/user-attachments/assets/96f74aef-af51-4399-9da6-3e456eb9923e" width="500"/>
</p>
<p align="center">
  <img src="https://github.com/user-attachments/assets/8c7d8b2a-d126-48dc-beee-c49477497373" width="500"/>
</p>
<p align="center">
  <img src="https://github.com/user-attachments/assets/d0dbe699-70cb-4a65-9082-4f67686b7964" width="500"/>
</p>

Con estos valores, la simulación realizada tras 22 días hábiles con un turno diario de 8 horas arrojó los siguientes resultados: se logró una homogenización de producción del 87%, con un aumento del 252% en la producción de tanques, del 233% en automóviles y un crecimiento adicional del 2% en helicópteros. Este representa un importante primer avance.

<p align="center">
  <img src="https://github.com/user-attachments/assets/028b5704-c02b-455e-ad89-335a3848362e" width="500"/>
</p>

   ### 1.4 Kpis del proceso  
   ### 1.5 Vsm proceso automatizado  
<p align="center">
  <img src="https://github.com/user-attachments/assets/19b0a140-df9f-4b96-90f7-a73c9fe8cf24" width="500"/>
</p>



