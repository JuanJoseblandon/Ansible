## Instalación de Ansible
Para instalar ansible y prepararlo para el despliegue de wordpress, primero debemos instalar ansible en la maquina que servira como servidor y el software neceario con:

```bash
$ sudo apt install software-properties-common
```

Ahora debemos instalar el repositorio de ansible
```bash
$ sudo apt-add-repository --yes --update ppa:ansible/ansible
```

Y actualizamos con:
```bash
$ sudo apt update
```
Ahora podemos instalar ansible con

```bash
$ sudo apt install ansible
```

## Configuración 
Ansible se conecta a su cliente a través de SSH (Secure shell).

Primero generaremos una clave pública en el servidor ansible, que debe copiarse en el cliente ansible.

Asegúrese de haber iniciado sesión como usuario root.
Genere la clave usando ssh-keygen comando como se muestra a continuación

![image](https://user-images.githubusercontent.com/91255763/222104935-1f26b3c8-7df7-4170-9f53-209ee6e6e816.png)

Como habrás notado, ha generado una clave pública en el .ssh carpeta. La ruta completa es /root/.ssh/id_rsa.pub, debemos revisar los permisos y que los archivos tengasn un permiso 400

![image](https://user-images.githubusercontent.com/91255763/222116381-3ed376f0-78e4-4345-b97b-a5b6758971a7.png)

Si los permisos no son correctos debemos cambiarlos

```bash 
chmod id_rsa 400
chmod id_rsa.pub 400
```
![image](https://user-images.githubusercontent.com/91255763/222116737-23ebfb37-eca7-4a15-bb33-72bad951f0f2.png)

Tambien debemos instalar openssh-server y modificar el archivo de configuración de ssh
![image](https://user-images.githubusercontent.com/91255763/222119047-aee43314-3c06-4ea7-894f-c34cd371d31b.png)

Ahora debemos copiar la clave public al cliente cuya ip es 192.168.196.150
![image](https://user-images.githubusercontent.com/91255763/222119301-c0f871ab-ccf4-473d-ac50-0b1a4a70a5a2.png)

La configuración del cliente o del host no es más que hacer que el servidor Ansible conozca a los clientes. Y para hacerlo:

Inicie sesión en el servidor Ansible
Vaya a / etc / ansible
Agregue lo siguiente en archivo de hosts usando tu editor favorito

```bash
[client]
node1 ansible_ssh_host=<usuario>@<ip>
```

![image](https://user-images.githubusercontent.com/91255763/222120863-8427ffc9-8640-4bf9-9aa7-9d408144b908.png)

  
