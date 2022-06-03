# Configuração interface de rede com netplan
1 - Exemplo de uma configuração dinâmica.
```yaml
network:
   version: 2
   renderer: NetworkManager
   ethernets:
      enp0s3:
        dhcp4: yes #or true
      enp0s8: 
        dhcp4: yes #or true

```
2 - Exemplo de uma configuração estática.
```yml
network:
   version: 2
   renderer: NetworkManager
   ethernets:
      enp0s3:
        dhcp4: no #or false
        addresses: [192.168.1.10/24] #ip e mask
        nameservers: # dns
            addresses: [8.8.8.8, 8.8.4.4]
        routes: #novo metodo pra gateway
            - to: default
              via: 192.168.1.1 #gateway da rede
```