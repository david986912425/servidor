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
## Paso 3: Instalar MySQL
Ejecuta el siguiente comando para instalar el servidor de MySQL:
```bash
sudo apt install mysql-server
```
Durante la instalación, se te pedirá configurar una contraseña para el usuario "root" de MySQL. Asegúrate de recordar esta contraseña, ya que la necesitarás para acceder al servidor de MySQL.

Una vez instalado, puedes ajustar la configuración de MySQL si lo deseas. Para ello, ejecuta el siguiente comando:
```bash
sudo mysql_secure_installation
```
Este comando te guiará a través de un asistente para configurar opciones de seguridad básicas para MySQL, como eliminar usuarios anónimos, deshabilitar el inicio de sesión remoto para el usuario "root", eliminar la base de datos de pruebas y recargar los privilegios.

Inicia sesión en MySQL como usuario root utilizando autenticación de socket. Esto se puede hacer ejecutando el siguiente comando en la terminal:
```bash
sudo mysql -u root
```
Esto iniciará la sesión de MySQL como usuario root sin requerir una contraseña.

Ahora, dentro de MySQL, utiliza el comando ALTER USER para cambiar la contraseña de 'root'. Por ejemplo, para cambiar la contraseña a "nuevacontraseña", ejecuta el siguiente comando:
```bash
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'nuevacontraseña';
```
Después de ejecutar el comando ALTER USER, asegúrate de recargar los privilegios de MySQL para que los cambios surtan efecto:
```bash
FLUSH PRIVILEGES;
```

Finalmente, puedes salir de la consola de MySQL ejecutando el comando:
```bash
exit;
```
