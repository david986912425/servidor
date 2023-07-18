# servidor

## Paso 1: Crear usuario

Abre la terminal y ejecuta el siguiente comando para crear un nuevo usuario:
```bash
adduser david
```

Este comando creará un nuevo usuario llamado "david" en el sistema.
Luego, para proporcionarle permisos de administrador, ejecuta el siguiente comando:
```bash
usermod -aG sudo david
```
Esto agregará al usuario "david" al grupo "sudo", lo que le permitirá ejecutar comandos con privilegios de superusuario cuando sea necesario.

## Paso 2: Instalar Node
Para instalar Node.js en el servidor, primero necesitaremos instalar cURL, que es una herramienta que nos permitirá obtener los archivos necesarios. Ejecuta el siguiente comando:
```bash
sudo apt-get install curl
```
Después, utiliza cURL para obtener el script de instalación de Node.js con la versión específica que deseas. Por ejemplo, aquí utilizaremos la versión 16.x:
```bash
curl -s https://deb.nodesource.com/setup_16.x | sudo bash
```
Una vez que hayas obtenido el script de instalación, procede a instalar Node.js ejecutando el siguiente comando:
```bash
sudo apt install nodejs -y
```
