#Informe de auditoria de Red Wi-Fi Insegura

##Introducción.

El objetivo de esta practica es analizar los riesgos de seguridad asociados al uso de redes Wi-Fi publicas, comprender las diferencias entre HTTP y HTTPS y explicar como una VPN puede contribuir a proteger la información transmitida

Para realizar el análisis se utilizo una captura de trafico de red y se examino una solicitud HTTP hacia un sitio web sin cifrado.

Sitio Analizado.

	http://neverssl.com
	Host: neverssl.com
	Protocolo: HTTP
	Método HTTP: GET
	Recuso Solicitado: /
	Respuesta del servidor: 200 OK

El sitio fue seleccionado porque permite realizar conexiones HTTP sin redirigir automáticamente al usuario hacia HTTPS.

#Evidencia observada

Durante el análisis de tráfico se identificaron los siguientes elementos:

Elemento	Resultado

Método		GET

Host		neverssl.com

URI		/

Protocolo	HTTP

Respuesta	200 OK

También es posible observar información adicional en los encabezados HTTP, como el User-Agent, que identifica el navegador utilizado, y otros datos asociados a la solicitud.

La comunicación HTTP no cifra el contenido de la solicitud, por lo que puede ser inspeccionada por terceros que tengan acceso al tráfico de red.

#Riesgos encontrados.

	-La navegación mediante HTTP en una red Wi-Fi pública presenta distintos riesgos de seguridad:

	-Intercepción de datos: Un atacante puede capturar paquetes de red y analizar información transmitida sin cifrado.

	-Ataques Man-in-the-Middle: Un atacante puede posicionarse entre el usuario y el destino de la comunicación para interceptar o modificar información.

	-Exposición de información: Las direcciones solicitadas, encabezados y otros datos pueden quedar visibles.

	-Manipulación del tráfico: Un atacante podría modificar respuestas o redirigir al usuario hacia sitios maliciosos.

Es importante destacar que HTTPS reduce considerablemente estos riesgos al cifrar la comunicación entre el navegador y el servidor.

#¿Cómo ayuda una VPN?

Una VPN protege la conexión mediante un túnel cifrado entre el dispositivo del usuario y el servidor VPN.

Sus principales funciones son:

	-Cifrado: La información transmitida dentro del túnel se convierte en datos ilegibles para terceros que intenten interceptarla.

	-Encapsulamiento: Los paquetes originales se introducen dentro de otros paquetes para transportarlos mediante el túnel VPN.

	-Protección del tráfico: Reduce la posibilidad de que otros usuarios de la red pública puedan inspeccionar directamente la comunicación protegida.

	-Privacidad: Oculta el tráfico original frente a otros dispositivos de la red local, aunque el proveedor VPN sigue siendo un intermediario de confianza.

Una VPN complementa la seguridad de la conexión, pero no reemplaza HTTPS ni garantiza protección absoluta frente a todas las amenazas.


#Las 3 Reglas de Oro para utilizar redes Wi-Fi públicas

	-Evitar operaciones sensibles: No acceder a cuentas bancarias ni realizar operaciones importantes mediante redes públicas que no sean de confianza.

	**-Utilizar conexiones seguras:** Comprobar que los sitios web utilicen HTTPS y, cuando sea necesario, utilizar una VPN confiable.

	**-Desconfiar de redes desconocidas:** Verificar el nombre de la red con el establecimiento, evitar conectarse a puntos de acceso sospechosos y desactivar la conexión automática a redes públicas.

