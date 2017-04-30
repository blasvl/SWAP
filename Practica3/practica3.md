## 1. Configurar una maquina e instalarle nginx como balanceador de carga
Para realizar esto en primer lugar tendremos que crear una nueva maquina virtual, instalaremos nginx mediante los comandos:  
  
  *sudo apt-get update && sudo apt-get dist-upgrade && sudo apt-get autoremove*  
  *sudo apt-get install nginx*  
  *sudo systemctl start nginx*  
  
Usaremos la configuración dada en la practica para que nginx reparta la carga mediante el algoritmo round-robin, a continuación se muestra una imagen con los datos de la maquina.  
![alt text](https://github.com/blasvl/SWAP/tree/master/Practica3/img/datos_nginx.png)    
Como vemos la ip del balanceador es 190.168.1.102, le haremos varias peticiones mediante curl.  
![alt text](https://github.com/blasvl/SWAP/tree/master/Practica3/img/balanceo_nginx.png)    
Podemos ver como va alternando la petición entre las dos maquinas al estar usando el algoritmo round-robin.  
## 2. Configurar una maquina e instalarle haproxy como balanceador de carga
Instalaremos haproxy mediante el comando:  
*sudo apt-get install haproxy*  
A continuación la configuraremos tal y como nos muestra la práctica, la siguiente imagen muestra los datos de la maquina, incluyendo su ip.  
![alt text](https://github.com/blasvl/SWAP/tree/master/Practica3/img/datos_haproxy.png)  
Haremos las peticiones mediante curl.  
![alt text](https://github.com/blasvl/SWAP/tree/master/Practica3/img/balanceo_haproxy.png)  
Podemos ver como la carga se va repartiendo mediante round-robin.  
## 3. Someter a la granja web a una alta carga, teniendo primero nginx y después haproxy.
Usaremos Apache Benchmark (ab) para comprobar el rendimiento de las maquinas, realizaremos 10000 peticiones con un nivel de concurrencia de 10, a continuación se muestran los resultados.  
![alt text](https://github.com/blasvl/SWAP/tree/master/Practica3/img/carga_nginx.png)  
![alt text](https://github.com/blasvl/SWAP/tree/master/Practica3/img/carga_haproxy.png)  
Podemos ver como nginx a conseguido un mejor tiempo(5.463 segundos frente a 7.594 segundos), consiguiendo también un mayor ratio de transferencia.
