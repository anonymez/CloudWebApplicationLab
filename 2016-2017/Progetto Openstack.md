Progetto Openstack  
  
Scrivere un client per openstack che fornisca un riassunto sullo stato del tenant in uso.   
Si vuole elencare tutti i servizi, indicando se il servizio è attivo o no, e per ogni servizio in caso positivo, fornire una sintesi che ne rappresenti lo stato dato in input il tenant.   
  
Esempio:  
  
quotas:  
  
Keystone - active  
user information  
  
Nova - active  
VM: 3  
VM-1 image: Ubuntu flavor:m1.small securityGroup:default ip: 172.25.27.44 network: --  
...  
  
Glance - active  
Images:10  
Image-1 name: Ubuntu public: YES checksum:  
Image-2   
  
Neutron - active  
number of networks :10  
routers: 5  
load balancer: 2  
  
Cinder - active  
number of storage : 20  
type of storage:2    
Storage-1 size: 10Gb Encrypted:none used:10%  
Storage-2 size: 100GB Encrypted:yes used:99%  
  
Swift - disabled  
Heat - disabled  
....  
....  
  
Il progetto comprende l'installazione e configurazione di una macchina all-in-one Devstack.  
