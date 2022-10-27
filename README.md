## Practica-dns ##

### Configura un sistema con un servidor DNS y un cliente alpine que cumpla los siguientes requisitos ###

-Volumen por separado de la configuración.

-Red propia interna para todos los contenedores.

-ip fija en el servidor.

-Configurar Forwarders.

-Crear Zona propia.

-Registros a configurar: NS, A, CNAME, TXT, SOA.

-Cliente con herramientas de red.

-Lineas del docker-compose explicada.

-Procedimiento de creación de servicios (contenedor).

-Modificación de la configuración, arranque y parada de servicio bind9.

-Configuración zona y como comprobar que funciona.


#### 1.Para añadir un nuevo volumen nos dirigimos al archivo "named.conf" y hacemos un 'include' del nuevo volumen despues de crearlo.

#### 2.Despues para crear una nueva red, nos dirigimos al documento .yml y añadimos la subred en el apartado de networks,  "bind9_subnet".

#### 3.Para asignarle una Ip fija al servidor, hay que añadir la linea 'ipv4_address:' y asignarla. En este caso "10.1.0.254".

#### 4.Para configurar los forwardes debemos dirigirnos al archivo "named.conf.options" y  en la llave de forwarders puedo modoficar o añadir ips . 
Yo tengo las ips "8.8.8.8" y "8.8.4.4".

#### 5.Para añadir una nueva zona nos dirigimos al archivo 'named.conf.local' y una vez allí añadiremos una nueva zona , en este caso yo cambie la que ya había por 
"practicadns".

#### 6.Para configurar su registro me dirijo a la carpeta de "zonas" > "db.asircastelao.int" aqui se puede añadir el nombre de mi zona así como un alias si se desea.

#### 7.Para configurar el cliente me dirijo a "docker-compose.yml", desde aqui puedo crear un nuevo cliente y le indico la network que va a utilizar, el modo de arranque, etc.

