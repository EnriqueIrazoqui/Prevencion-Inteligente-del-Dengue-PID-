# **Prevención Inteligente de Dengue (PID).**
El objetivo general del proyecto es aplicar técnicas de inteligencia artificial para simular y predecir los niveles de contagio del Dengue en México en diversos períodos de tiempo, como meses y años. El propósito principal es proporcionar información relevante a los profesionales de la salud, con el fin de apoyar sus esfuerzos en la adopción de medidas preventivas efectivas. A través de esta iniciativa, se busca fortalecer la capacidad de respuesta ante las epidemias y disminuir la incidencia del Dengue a nivel local.
## **Participantes:**
 - Enrique Irazoqui Ruelas.  
 - Nicolas Bañuelos Hernadez. 
 - Luis Fernando  Castorena.
# **Uso.**
Proyecto en Google Colab -> [Prevención Inteligente de Dengue (PID).](https://colab.research.google.com/drive/12t2iB0v-U8fKBxSt7lXGFM5ho832CGQH?usp=sharing)

***Ignorar el primer cuadro de código, ya que este lo usamos para conectarnos a Drive y tener acceso a las bases de datos que tenemos en una unidad compartida.***

    from google.colab import drive
    drive.mount('/content/drive')
En el segundo cuadro de código se debe poner la dirección donde se encuentran las bases de datos, nosotros trabajamos con cuatro, por eso las concatenamos.

    d2020 =  'drive/Shareddrives/PID/Dengue/dengue_abierto2020.csv'
    d2021 =  'drive/Shareddrives/PID/Dengue/dengue_abierto2021.csv'
    d2022 =  'drive/Shareddrives/PID/Dengue/dengue_abierto2022.csv'
    d2023 =  'drive/Shareddrives/PID/Dengue/dengue_abierto2023.csv'
    datosHistoricos = pd.concat(map(pd.read_csv,  [d2020, d2021, d2022, d2023]), ignore_index=True)
    datosHistoricos

En el quinto cuadro de código se busca la Entidad (Estado) deseada, en nuestro caso fue Jalisco, en la linea dos del código donde dice jalisco en mayúsculas, ahí se va a escribir el Estado con el que se quiera trabajar en mayúsculas, es importante hacer esto en dado caso de que se vaya a filtrar por Entidad, ya que se necesita saber la clave de la entidad.

     entidades = pd.read_excel('drive/Shareddrives/PID/Dengue/Catálogos_Dengue.xlsx', sheet_name='CATÁLOGO ENTIDAD')  # SE BUSCA A JALISCO EN EL CATALOGO ENTIDAD
    jalisco = entidades[entidades.ENTIDAD_FEDERATIVA.eq('JALISCO')]
    entidad =  list(jalisco.CLAVE_ENTIDAD)
    jalisco

En el séptimo cuadro de texto se muestran las calves de Estatus_Caso, y en el octavo cuadro de texto en la primera linea de código es donde se filtra por Estatus de caso, nada mas es cambiar el numero que esta dentro del método .eq() por la clave del tipo de caso que se quiera trabajar. 

![](https://raw.githubusercontent.com/EnriqueIrazoqui/Prevencion-Inteligente-del-Dengue-PID-/main/Imagenes/3.png)

El en cuadro de codigo N° 10 se busca cual es el la clave de municipio en la cual se quiere trabajar.

    municipio = municipiosJalisco[municipiosJalisco.MUNICIPIO.eq('ZAPOPAN')]
    municipio =  list(municipio.CLAVE_MUNICIPIO)
    print('LA CLAVE DEL MUNICIPIO ES: ',municipio[0])
En la cuadro de codigo N° 14 se filtra un dataframe con un año especifico, esto para obtener el total de contagios de ese año y pode mostrar los casos de manera grafica.

    year =  2020
    df_por_year = casosConfirmadosEnZapopan[(casosConfirmadosEnZapopan['FECHA_SIGN_SINTOMAS'].dt.year == year)]
    df_por_year
