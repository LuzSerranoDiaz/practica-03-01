# practica-03-01

## Instalacion Plesk Openstack
![OpenstackInstancia](https://github.com/LuzSerranoDiaz/practica-03-01/assets/125549381/c90ab8af-9eb3-418b-9d76-81fdca720af1)

Creamos una instancia plesk-ubuntu-22-18.0.56 con el flavor m1.large, una clave SSH y una ip flotante

![OpenstackSeguirdad](https://github.com/LuzSerranoDiaz/practica-03-01/assets/125549381/1e2cfa4f-2903-4dd0-8df4-86506c40cf11)

Abrimos los puertos necesarios (y todos los puertos TCP para asegurarse de que no hay nigún error)

## Acceso al panel de administración de Plesk y cambio de contraseña

![OpensTackConsola](https://github.com/LuzSerranoDiaz/practica-03-01/assets/125549381/e28336d8-ffea-4f5f-a936-bfd7338b95d5)

Para cambiar la contraseña de la maquina la iniciamos y presionamos rapidamente *shift* en la consola hasta que aparezca el menú de arranque, seleccionamos *Advanced options for ubuntu*, *ubuntu with linux 5.15.0-88-generic (recovery mode)*, *root - Drop to root shell prompt*, escribimos `mount -o remount,rw /`, para montar la raiz en modo lectura y escritura, y modificamos la contraseña a root y reiniciamos la maquina con `passwd root` y `reboot` respectivamente.


## Dominios y subdominios en plesk

Creamos un dominio llamado web.celia y 4 subdominios para cada tipo de aplicación respectivamente:
![pleskDominios](https://github.com/LuzSerranoDiaz/practica-03-01/assets/125549381/96db0609-1cec-4c18-8467-05ee903f5144)

Y se configuran las entradas DNS locales en el archivo `C:\Windows\System32\drivers\etc\hosts` para que podamos acceder a las paginas
![hosts](https://github.com/LuzSerranoDiaz/practica-03-01/assets/125549381/5a13730f-ea10-49a5-a6b4-349623c5b187)

## Despliegue App WordPress

Utilizando el dominio creado de Wordpress.web.celia instalamos el plugin de *WP toolkits*

![toolkit](https://github.com/LuzSerranoDiaz/practica-03-01/assets/125549381/3ff200c0-6540-407d-9361-9ce3d53fbc53)

![WPMystore](https://github.com/LuzSerranoDiaz/practica-03-01/assets/125549381/dfeb4bfb-74de-4a5b-adcb-01235a753ffa)

Utilizando este plugin accedemos a nuestro dominio y realizamos los siguientes pasos:

1. Escogemos un tema para la página
   
![wpStyle](https://github.com/LuzSerranoDiaz/practica-03-01/assets/125549381/b002a4bc-ec66-4021-9f70-7cd7444bc285)

2. Y se aplican las medidas de seguridad recomendadas por Plesk

![WPSecurity](https://github.com/LuzSerranoDiaz/practica-03-01/assets/125549381/590b1155-c73e-46f8-a9cf-d37523555170)


![appFunciona](https://github.com/LuzSerranoDiaz/practica-03-01/assets/125549381/f6eadb9e-d336-47f2-b88f-24576a784f3c)


## Despliegue App git

1. Se crea una base de datos y un usuario con permisos sobre la misma
![DBcrear](https://github.com/LuzSerranoDiaz/practica-03-01/assets/125549381/041fa375-27de-4962-89b8-18580e9ce101)

2. Se clona el repositorio
![repolink](https://github.com/LuzSerranoDiaz/practica-03-01/assets/125549381/25904215-2a7f-4b52-b0ae-fcdae8e666a9)

3. Se configura el uso de Webhooks para hacer pulls automaticos
![gitPull](https://github.com/LuzSerranoDiaz/practica-03-01/assets/125549381/741fc063-da5d-4f57-8a66-858498fb9865)

4. Se crea una tabla en phpMyAdmin

![crearTabla](https://github.com/LuzSerranoDiaz/practica-03-01/assets/125549381/ab0ae523-2fe8-4d70-9bcf-6b3f291ae637)

5. Se configura el valor de DocumentRoot
![hostname](https://github.com/LuzSerranoDiaz/practica-03-01/assets/125549381/f80c146a-c5cb-4052-88d2-01e85bafc5ae)

6. Se configura las deploy actions para ejecutar comandos en el servicio tras cada pull
![repobash](https://github.com/LuzSerranoDiaz/practica-03-01/assets/125549381/cf3a2852-d958-4dce-bb50-7008e497eadb)


![appFunciona](https://github.com/LuzSerranoDiaz/practica-03-01/assets/125549381/71a7b514-603d-4439-8659-4af8fb06d63c)


## Despliegue App por FTP

1. Se crea la base de datos MySQL
![ftpDB](https://github.com/LuzSerranoDiaz/practica-03-01/assets/125549381/4f5ede0e-13d0-4422-b602-58fbd0550ef4)

2. Se suben los archivos de la aplicacion, modificados de antemano para la base de datos creada, por fileZila
![subir](https://github.com/LuzSerranoDiaz/practica-03-01/assets/125549381/6ae3cf4d-7c33-4db7-a444-6baaa53f1af1)

3. Se crea una tabla en phpMyAdmin
![crearTabla](https://github.com/LuzSerranoDiaz/practica-03-01/assets/125549381/ab0ae523-2fe8-4d70-9bcf-6b3f291ae637)

![appFunciona](https://github.com/LuzSerranoDiaz/practica-03-01/assets/125549381/7bbc3988-355c-4d1d-8bd4-d7d24faa94a7)
