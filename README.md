Rol simple para despliegue de stack LAMP.

Todos los directorios y archivos mencionados a continuación se encuentran dentro del fork del repositorio "obligatorio202102", considerándolo como la raíz y omitiendo su mención.

------
Archivo /lamp_simple/hosts

Se incluyen los nombres y direcciones IP de nuestros equipos, uno dentro del grupo "webservers" y uno dentro del grupo "dbservers".

------
Archivo /lamp_simple/site.yml

Se modifica el archivo dejando como comentarios las líneas correspondientes a los roles "web" y "dbserver". Se incluyen esos dos roles dentro de la configuación aplicable a todos los hosts (all). 

------
Archivo /lamp_simple/roles/db/tasks/main.yml

Se adapta el playbook a las versiones actuales de CentOS, cambiando los paquetes y servicio de Mysql por los de Mariadb, además de la línea "with_items" por "loop".

------
Archivo /lamp_simple/roles/db/handlers/main.yml

Se cambia el nombre del servicio "mysqld" por "mariadb".

------
Archivo /lamp_simple/roles/web/tasks/install_httpd.yml

Se adapta el playbook a las versiones actuales de CentOS, corrigiendo a la versión actual de Python.
También se contempla una variable con "apache2" para la familia de sistemas operativos Debian/Ubuntu.

------
Archivo /lamp_simple/roles/common/tasks/main.yml

Se contempla ambas familias de sistemas operativos (Debian/Ubuntu y RedHat/CentOS), y los nombres correctos de los paquetes y servicios.

------
Archivo /lamp_simple/roles/common/handlers/main.yml

Se contempla ambas familias de sistemas operativos (Debian/Ubuntu y RedHat/CentOS), y los nombres correctos de los servicios.
