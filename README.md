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

