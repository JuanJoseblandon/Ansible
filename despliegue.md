# Despliegue de wordpress
Despues de configurar ansible  debemos clonar el repositorio do-community/ansible-playbooks.git con el siguiente comando

```bash
git clone https://github.com/do-community/ansible-playbooks.git
```
Despues de clonar el repositorio debemos entrar en la carpeta ansible-playbooks, después entramos  en la carpeta wordpress-lamp_ubuntu1804 y editamos el archivo vars/default.yml

```bash
cd ~/ansible-playbooks
cd wordpress-lamp_ubuntu1804
nano vars/default.yml
```
Este archivo contiene algunas variables que requieren su atención
![image](https://user-images.githubusercontent.com/91255763/222919439-92923216-73f1-4d45-80cc-cd4866848848.png)

De este documento cambiare el nombre de mysql_user de sammy a ansibleslave, las contraseñas y el nombre de los documentos de apache2, después de editarlo guardamos y escribimos el siguiente comando:

```bash 
$ sudo sudo ansible-playbook playbook.yml -u ansibleslave --ask-become-pass
```
pedira la contraseña de la máquina cliente y saldra lo siguiente

![image](https://user-images.githubusercontent.com/91255763/222922477-2aff3680-78e5-4e4a-9c9f-416fadf3a9f8.png)
 
 Una vez hecho esto dbemos ier a la maquina cliente e introducir en el bavegador la ip del cliente de la siguiente forma
  ```
  http://ip_host
  ```
  
  Al hacerlo nos mostrara la siguiente página
  ![image](https://user-images.githubusercontent.com/91255763/222922620-545653ef-5c26-4ffb-938d-f5753aab3d67.png)

 
