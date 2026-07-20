# sprint7-final-project
Final project - Sprint 7

**Ojetivo:**
evaluar el comportamiento de los clientes de una empresa de telecomunicaciones en Latinoamérica, ConnectaTel, hasta el año 2024.

**Datasets utilizados:**
1. plans.csv → información de los planes actuales (precio, minutos incluidos, GB incluidos, costo por extra)
2. users.csv → información de los clientes (edad, ciudad, fecha de registro, plan, churn)
3. usage.csv → detalle del uso real de los servicios (llamadas y mensajes)

**Etapas del análisis realizadas:**
Paso	Acción	Resultado para el negocio
1. Cargar y explorar - reg_date y churn_date a datetime y checar nulls the city
2. Identificación de problemas de calidad - La columna churn en users probablemente será ignorada o eliminada, ya que cuenta con el 88% de valores nulos.
Columnas duration y length en usage tienen 55% y 44% respectivamente de valores nulos, investigar para tomar acción.
La columna city en users tiene 11% de valores nulos; se requiere investigación para tomar la siguiente acción: imputación o dejar como nulos.
La columna date en usage tiene 0.12% de valores nulos, hay que revisar si requiere imputación o dejar como nulos.
3. Limpieza básica - Tanto duration como length tiene sentido que tengan valore nulos. Duration en text y length en call porque duration se mide en tiempo de llamada, no texto, y length se mide en tamaño de texto, no de llamada.
4. Summary statistics - La columna user_id tiene promedio (mean) y media (50%) iguales: 11999.50. Mínimo 10000 y máximo 13999 coincidiendo con los 4000 valores.
La columna age tiene un promedio (mean) de 33.7% y media de 47%; no coinciden. El mínimo es -999; hay que arreglarlo. El máximo es de 79. El 25% es 32 y coincide más con el promedio, que es 33.7, lo que significa que probablemente la mayoría de usuarios es alrededor de esa edad.
5. Visualización & outliers
- La mayoría de los usuarios se encuentran entre los 42 y los 49 años de edad.
- Para los usuarios que usan el plan Básico, la distribución entre edades es similar, con una mayoría notoria en los 40's. Y para los que tienen plan Premium, la mayoría de usuarios se encuentra en el último rango de edad, seguido de las edades en los 20's y los 40's.
- En el rango de 2.5 - 5.0 se concentra la mayoría de usuarios Básico, y los Premium se concentran más cerca de 5.0.
- El plan Básico envía más mensajes en general.
- La distribución parece sesgada a la derecha con la excepción de los primeros rangos de cantidad de mensajes.
- Hay más mensajes en Básico tal vez porque hay más usuarios de Básico que de Premium.
- La distribución parece sesgada a la derecha con la excepción de los primeros rangos de cantidad de llamadas.
- La mayoría de los usuarios, tanto en Básico como en Premium, se concentra en el rango de 3-4 llamadas.
- Los dos planes se comportan de manera similar.
- La distribución está sesgada a la derecha.
- Los dos tipos de usuarios, Básico y Premium se comportan de manera similar: la mayoría realiza llamadas que duran hasta 30mins y van disminuyendo con excepciones de hasta 155 minutos.

6. Segmentación - El grupo más grande es Adultos, seguido de Adultos Mayores y Jóvenes.
Los usuarios Premium se concentran más en Adultos Mayores.
Tanto los adultos mayores como los adultos son un grupo especial. Los adultos mayores, por ser la mayoría que usa premium, y los adultos, por ser la mayoría de clientes. La mayoría de los usuarios son de uso medio, y el de uso alto es el menor.
La cantidad de llamadas y mensajes tanto en Básico como en Premium tiene un comportamiento similar similar independientemente del plan.

7. Insight ejecutivo - 

**⚠️ Problemas detectados en los datos**
La columna age tenía un std de 123.23 y el mínimo era de -999. Después de limpiar, el std bajó a 17.69 y el mínimo se convirtió en 18.
La columna reg_datee tenía 40 fechas con año 2026, y trabajamos solamente hasta el 2024.
La columna date tenía 50 valores nulos de 40,000, representando el 0.125%.
La columna city tenía 3531 valores no nulos y, al parecer, también 7 ciudades.

**🔍 Segmentos por Edad**
El grupo más grande es Adultos, seguido de Adultos Mayores y Jóvenes.
Los usuarios Premium se concentran más en Adultos Mayores.
Tanto los adultos mayores como los adultos son un grupo especial. Los adultos mayores por ser la mayoría que usa premium, y los adultos por ser la mayoría de clientes.

**📊 Segmentos por Nivel de Uso**
La mayoría de los usuarios son de uso medio y el uso alto es el menor.
La cantidad de llamadas y mensajes tanto en Básico como en Premium tiene un comportamiento similar similar independientemente del plan.

**💡 Recomendaciones**
Los adultos son la mayoría de los clientes, pero alrededor de la mitad usan Premium. Se podría hacer una campaña invitando a los adultos a unirse a Premium, ya sea bajando el precio por llamada y por longitud de mensaje, y hasta más adultos podrían unirse a Básico también.
Los adultos mayores son la mayoría de los usuarios Premium. Se recomienda crear promociones para que más adultos mayores puedan disfrutar del plan Premium, con más llamadas por más tiempo y más mensajes. Así, también los adultos mayores que ya son parte del plan Premium quieren seguir ahí.
El grupo de jóvenes representa una oportunidad de negocio, porque es el grupo que menos usuarios tiene; sin embargo, podría llegar a un nivel de uso medio, tanto de Básico como de Premium, creando tanto un crecimiento como una retención.
Se podría hacer una promoción a los usuarios de uso medio para que se conviertan en usuarios de uso alto, ya que son la mayoría de los usuarios.
Para los outliers de cant_minutos_llamada se sugiere crear un grupo con promociones especiales para que crezca la retención y más usuarios puedan disfrutar de llamadas largas.

8. Publicación

**Cómo ejecutar el notebook:**
1. *Cómo abrir el notebook* → puedes poner un link directo a Google Colab
2. *Cómo cargar los datos* → indicar dónde están los archivos CSV y cómo subirlos si es necesario
3. *Cómo ejecutar las celdas* → Ejecutar todas las celdas en orden desde Runtime > Run all

