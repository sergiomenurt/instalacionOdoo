<h1>Instalación de Odoo</h1>

<h3>Lo primero que voy a explicar son las funciones que tienen las diferentes partes del docker-compose.yml:</h3>

![Captura de pantalla 2023-03-15 234257.png](Captura%20de%20pantalla%202023-03-15%20234257.png)

<h3>1. image: </h3>Nombre de la imagen que se creará a partir del archivo Dockerfile.

<h3>2. container_name: </h3>Nombre del contenedor.

<h3>3. environment: </h3>Permite pasar valores de parámetros al contenedor.

<h3>4. ports: </h3>Permite publicar puertos expuestos dentro del contenedor, para nuestro ejemplo, la imagen de odoo expone el puerto 8069 y este es solo visible dentro del contenedor, sin embargo, para que este pueda ser accesible desde afuera se debe publicar mediante un puerto disponible en el sistema.

<h3>5. volumes: </h3>volumes: Permite la persistencia de datos en el contenedor. Debido a que los contenedores son volátiles por naturaleza, entonces es necesario asegurar los datos modificados y creados durante su funcionamiento. Para ello se suele definir una lista con pares ruta del sistema:ruta de contenedor, en donde ambas rutas serán sincronizadas.

<h3>6. depends-on: </h3> Lista de servicios de los cual depende el servicio de Odoo, en este caso, Odoo depende de solo del servicio de db (base de datos).

Para levantar nuestro docker-compose deberemos de utilizar el siguiente comando:

![Captura de pantalla 2023-03-15 234312.png](Captura%20de%20pantalla%202023-03-15%20234312.png)

Tras haber realizado esto, podremos ir al navegador que elijamos y buscar localhost:8069. En esta dirección tendremos nuestro proyecto odoo ejecutandose en el puerto que le asignamos. En primer lugar nos aparecerá esta pantalla de inicio en la cual tendremos que asignar los valores que le dimos a nuestra base de datos postgres.

![Captura de pantalla 2023-03-15 234230.png](Captura%20de%20pantalla%202023-03-15%20234230.png)

Tras haber introducido todos los datos creqaremos nuestra base de datos y se creará nuestro odoo. La pantalla que nos aparece de inicio nos muestra que estamos identificados como un usuario administrador llamado Mitchell Admin y nos aparecen muchas aplicaciones con las cuales podríamos trabajar.

![Captura de pantalla 2023-03-16 004816.png](Captura%20de%20pantalla%202023-03-16%20004816.png)

Si el puerto 5432 de nuestro ordeador estuviese ocupado podríamos ejecutar el siguiente comando en nuestro terminal. Al ejecutar este comando pararíamos cualquier servicio que se estuviese ejecutando de postgresql. Esto nos liberaría el puerto 5432, ya que es al que esta conectado postgresql.

![Captura de pantalla de 2023-03-17 12-37-08.png](Captura%20de%20pantalla%20de%202023-03-17%2012-37-08.png)