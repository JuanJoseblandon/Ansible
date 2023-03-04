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
De este documento cambiare el nombre de mysql_user de sammy a ansibleslave
