## Ejercicio T5.1:
#### Buscar información sobre cómo calcular el número de conexiones por segundo.
Desde nginx tendremos que editar el archivo de configuración nginx.conf y añadir lo siguiente:  
  
location /nginx_status {  
  
       stub_status on;  
       access_log   off;  
        
       allow 192.168.1.5;  
       deny all;  
  }  
  
Para ver las conexiones por segundo tan solo habra que teclear *http://your-domain-name-here/nginx_status* en el navegador.

También podremos ver el número de conexiones con el uso del comando netsat:  
  
- *netstat -na* para ver las conexiones establecidas.
- *netstat -an | grep :80 | sort* para ver las conexiones al puerto 80.
- *netstat -n -p | grep SYN_REC | sort -u* para ver también las IP.  
## Ejercicio T5.3:
#### Buscar información sobre características, disponibilidad para diversos SO, etc de herramientas para monitorizar las prestaciones de un servidor.
  
El comando top nos ofrece una interfaz en modo texto que es actualizada cada 3 segundos. Muestra un resumen del estado de nuestro sistema y la lista de procesos que se están ejecutando.  
  
El comando vmstat nos ofrece estadísticas de la memoria virtual y de los eventos del sistema. También nos da información sobre intercambio, vaciado de antememoria e interrupciones.  
  
El comando netstat muestra un listado de las conexiones activas, tanto entrantes como salientes, mostrando información como las tablas de ruteo o las estadísticas de las interfaces y estado de la conexión.
