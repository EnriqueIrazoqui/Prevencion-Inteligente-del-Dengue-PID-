# **Prevención Inteligente de Dengue (PID).**
El objetivo general del proyecto es aplicar técnicas de inteligencia artificial para simular y predecir los niveles de contagio del Dengue en México en diversos períodos de tiempo, como meses y años. El propósito principal es proporcionar información relevante a los profesionales de la salud, con el fin de apoyar sus esfuerzos en la adopción de medidas preventivas efectivas. A través de esta iniciativa, se busca fortalecer la capacidad de respuesta ante las epidemias y disminuir la incidencia del Dengue a nivel local.
## **Participantes:**
 - Enrique Irazoqui Ruelas.  
 - Nicolas Bañuelos Hernadez. 
 - Luis Fernando  Castorena.
# **Uso.**
Proyecto en Google Colab -> [Prevención Inteligente de Dengue (PID).](https://colab.research.google.com/drive/12t2iB0v-U8fKBxSt7lXGFM5ho832CGQH?usp=sharing)

***Ignorar el primer cuadro de código, ya que este lo usamos para conectarnos a Drive y tener acceso a las bases de datos que tenemos en una unidad compartida.***

En el segundo cuadro de código se debe poner la dirección donde se encuentran las bases de datos, nosotros trabajamos con cuatro, por eso las concatenamos.

![](https://raw.githubusercontent.com/EnriqueIrazoqui/Prevencion-Inteligente-del-Dengue-PID-/main/Imagenes/1.png)

En el quinto cuadro de código se busca la Entidad (Estado) deseada, en nuestro caso fue Jalisco, en la linea dos del código donde dice jalisco en mayúsculas, ahí se va a escribir el Estado con el que se quiera trabajar en mayúsculas, es importante hacer esto en dado caso de que se vaya a filtrar por Entidad, ya que se necesita saber la clave de la entidad.

![](https://raw.githubusercontent.com/EnriqueIrazoqui/Prevencion-Inteligente-del-Dengue-PID-/main/Imagenes/2.png)

En el séptimo cuadro de texto se muestran las calves de Estatus_Caso, y en el octavo cuadro de texto en la primera linea de código es donde se filtra por Estatus de caso, nada mas es cambiar el numero que esta dentro del método .eq() por la clave del tipo de caso que se quiera trabajar. 

![](https://raw.githubusercontent.com/EnriqueIrazoqui/Prevencion-Inteligente-del-Dengue-PID-/main/Imagenes/3.png)
