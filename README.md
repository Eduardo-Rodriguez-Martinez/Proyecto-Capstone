# Proyecto-Capstone
![Plano Inclinado 1](https://user-images.githubusercontent.com/87343531/143146929-555e00f2-3123-42c5-a006-dff3fc246fee.jpg)
## Resumen
En este repositorio se encuentra la documentación y código desarrollado para la implementación de un experimento de física consistente en el manejo de un plano inclinado con acceso remoto, como proyecto desarrollado para el Diplomado de IoT de Samsung Innovation Campus 2021/2022
## Datos generales
1. **Nombre del proyecto**: Laboratorio remoto para cursos de física básica
2. **Participantes**: [Fernando José de Jesús Ramírez Rojas](https://github.com/ferramr) y [Eduardo Rodríguez Martínez](https://github.com/Eduardo-Rodriguez-Martinez)
3. **Descripción**: El experimento del plano inclinado podrá ser observado de forma remota. El usuario podrá ajustra el ángulo de inclinación a través de una interfáz gráfica, en donde también se desplegarán los resultados del experimento mediante curvas de desplazamiento, velocidad y aceleración. La detección del movimiento de la esfera sobre el plano se realizará con técnicas de visión por coputadora sobre cada una de las tramas de video capturado con una cámara web

## Conteido
- Código fuente para el microcontrolador, realiza el control del plano inclinado: `./codigo/arduino_src/plano_inclinado_200.ino`

- Código fuente para seguimiento de trayectoria y control del experimento, desarrollado en python: `./codigo/python_src/modelo.py`[^1]

- Paquetes con la declaración y definición de clases usadas por `modelo.py`, desarrolladas en python:
    - Paquete con las clases implementan los métodos de comunicación: `./codigo/python_src/c`
        - Clase encargada de enviar y recibir información de ARDUINO a
través del puerto serial USB: `./codigo/python_src/c/comunicacion.py`
        - Clase encargada de la comunicación con el broker MQTT: `./codigo/python_src/c/mqtt.py`
    - Paquete con las clases que implementan los métodos de vision por computadora: `./codigo/python_src/m`
        - Clase reconocedora de la esfera amarilla: `./codigo/python_src/m/esfera.py`
        - Clase reconocedora de dos marcadores azules de referencia
localizados en los extremos del plano inclinado. Se uitilzan como
auxiliares para medir la longitud del plano y el ángulo que foma con
la horizontal: `./codigo/python_src/m/marcadores.py`
        - Clase encargada de realizar el procesamiento digital de los datos
obtenidos en el experimento: `./codigo/python_src/m/dsp.py`
    - Paquete con las clases que implementan los métodos de graficación: `./codigo/python_src/v`
        - Clase encargada de generar las gráficas de desplazamiento,
velocidad y aceleración de la esfera sobre el plano inclinado: `./codigo/python_src/v/graficador.py`
        - Clase encargada de mostrar la información resultante del
experimento en el lateral derecho de la imagen: `./codigo/python_src/v/display.py`

- Archivo JSON para importar un FLOW para NodeRed: `./codigo/node-red_src/flow_node-red`[^2]

- Informe del desarrollo y funcionamiento del proyecto: `./documentacion/PROYECTO CAPSTONE 2022.pdf`

- Documentos intermedios de avances reportados a CodigoIoT: `./documentacion/Kardex.docx`, `./documentacion/Plan_de_accion.docx`

[^1]: Se debe actualizar la dirección IP del broker público de HiveMQ
[^2]: Se deben actualizar los nodos MQTT con la dirección del broker público de HiveMQ