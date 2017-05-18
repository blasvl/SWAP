## Ejercicio T4.2:
#### Buscar información sobre precio y características de balanceadores hardware específicos. Compara lasprestaciones que ofrecen unos y otros.
Los balanceadores elegidos son KEMP LoadMaster, F5 - Big IP y Citrix Netscaler. La siguiente tabla muestra una comparación de sus precios y rendimiento.   
  
![alt text](img/comparacionbalanceadores.png)  
  
## Ejercicio T4.3:
#### Buscar información sobre los métodos de balanceo que implementan los dispositivos recogidos en el ejercicio 4.2.
Los algoritmos usados por KEMP LoadMaster son los siguientes:  
  
- Round Robin
- Weighted round robin
- Least connection
- Weighted least connection
- Agent-Based Adaptive Balancing
- Fixed weighting
- Weighted response time
- Source IP hash  
  
Los algoritmos usados por F5 - BIG IP son los siguientes:  
  
- Round Robin
- Ratio
- Least connection
- Fastest
- Observed
- Predictive  
  
Por ultimo los algoritmos usados por Citrix Netscaler son:  
  
- Least connection
- Round robin
- Least response time
- Url hash
- Domain hash
- Destination IP hash
- Source IP hash
- Src IP Dest IP hash
- Call ID hash
- Src IP Src Port hash
- Least Band width
- Least Packets
- Custom load
- Token 
- LRTM  
  
## Ejercicio T4.7:
#### Buscar información sobre métodos y herramientas para implementar GSLB.
Una forma es hacer uso de de Netscaler, los comandos a ejecutar para realizar su configuración son los siguientes:  
  
- enable ns feature gslb
- add gslb site site-US LOCAL 10.3.1.101
- add gslb site site-MX REMOTE 172.16.1.101
- add gslb site site-CO REMOTE 192.168.1.101
- add gslb vserver gslb-lb HTTP
- add gslb service gslb_SVC30 172.16.1.100 HTTP 80 -siteName site-MX
- add gslb service gslb_SVC10 10.3.1.100 HTTP 80 -siteName site-US
- add gslb service gslb_SVC20 192.168.1.100 HTTP 80 -siteName site-CO
- bind gslb vserver gslb-lb -serviceName gslb_SVC10
- bind gslb vserver gslb-lb -serviceName gslb_SVC20
- bind gslb vserver gslb-lb -serviceName gslb_SVC30
