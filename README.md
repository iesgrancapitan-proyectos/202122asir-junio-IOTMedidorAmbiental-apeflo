# Proyecto final Administración Sistemas Informáticos en Red

# Sistema IOT para la monitorización y visualización de parámetros ambientales.

## 1. Descripción del proyecto

Hemos creado un sistema IoT que recibe datos medioambientales como CO2, temperatura o humedad emitidos por unos sensores que se sitúan en el interior de las clases. En ellos encuentra la información sobre el estado actual de la ventilación. Los sensores han de ubicarse en los lugares más desfavorables de ventilación, incluyen una pantalla para observar los valores de los datos en directo. Además estos datos son enviados a un servidor desde dónde podrán visualizarse y poder actuar en consecuencia. Por ello nuestro sistema es seguro ya que emite alertas a una sola persona que puede controlar todas las ventilaciones de todas las aulas.

De esta forma creamos un entorno más seguro y todo el personal que compartimos espacios (profesores, alumnos, personal de otro tipo) tenemos la seguridad de que la calidad del aire en las aulas está controlada. «Los encargados pueden ventilar lo justo, sin gasto energético innecesario», y comentar que la red de datos que se genera se puede usar para transmitir a su vez otro tipo de mediciones de forma gratuita.

Todos los componentes van protegidos dentro de una caja hecha a medida en una impresora 3D que se hizo en el Aula Ateca de nuestro centro.

## 2. Información sobre despliegue

El despliegue necesario para este proyecto se basa básicamente en el microcontrolador ESP8266 y varios sensores que recogerían valores medioambientales y que enviarán a través de Wifi. Estos datos son procesados por un broker MQTT y enviados para su almacenamiento una base de datos a través de una aplicación llamada Telegraf. Para acceder a la información se usará Grafana, una herramienta que monitoriza y visualiza datos mediante representación con gráficas y tablas, con la finalidad de que la información representada sea más fácil de interpretar.

Un uso apropiado y útil de este proyecto de IoT, por la situación de pandemia actual, es el de medir los niveles de CO2 en las diferentes aulas, y si los niveles se superan en base a unos valores predefinidos, enviar alertas para que se actúe de forma inmediata. La implementación de un medidor de CO2 (dióxido de carbono) consta de una una placa con un microcontrolador ESP8266, a la que están conectados los sensores, el del CO2, temperatura y humedad. Mediante esa placa lo que haremos es configurarla para que recoja los datos de los sensores de una forma periódica, cada minuto. Los sensores son clientes publicadores en un Broker MQTT, que recoge los datos para posteriormente enviarlos al agente Telegraf, y que a su vez inserta los valores recogidos en una base de datos temporal InfluxDB. Por último y mediante los datos de la base de datos temporal lo que se hará es generar unos gráficos mediante Grafana.

Una vez hecho todo el despliegue y visto que funciona correctamente hemos añadido un sistema de avisos mediante correo electrónico, esto es por ejemplo si se llega a una situación en la que hay demasiado CO2 en el aula, se pueda notificar al profesor y ventilar el aula.


## 3. Información sobre cómo usarlo

Su uso es muy simple, una vez implementado como indica la documentación sólo hay que enchufarlo en un aula y esperar una posible notificación al correo en la que algún valor de los sensores haya rebasado el límite. 

## 4. Autores
* [Juan Antonio Cuenca Martínez](https://github.com/cuenca1805)
* [Francisco Javier Rodríguez Méndez](https://github.com/mendezfr)

## 5. Wiki

[Ver wiki](https://github.com/iesgrancapitan-proyectos/202122asir-junio-IOTMedidorAmbiental-apeflo/wiki)
