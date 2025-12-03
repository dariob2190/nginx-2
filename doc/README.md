# Práctica 2.2: Autenticación en Nginx

## Sumario:

1.  Paquetes necesarios
2.  Creación de usuarios y contraseñas
3.  Configurando el servidor Nginx
4.  Comprobación
5.  Tareas \
    5.1. Tarea 1 \
    5.2. Tarea 2 \
    5.3. Combinación de la autenticación básica con la restricción de acceso por IP \
    5.4. Tarea 3 \
    5.5. Tarea 4

## 1. Paquetes necesarios

Vamos a empezar comprobando si tenemos las herramientas necesarias en nuestra máquina Debian. Para esta práctica utilizamos la herramienta `openssl` para crear las contraseñas. Comprobamos si el paquete está instalado con el siguiente comando:

```
dpkg -l | grep openssl
```

Si no lo estuviera, tendríamos que instalarlo.

## 2. Creación de usuarios y contraseñas

Ahora vamos a crear un archivo oculto llamado `.htpasswd` dentro del directorio de configuración `/etc/nginx` donde guardaremos los usuarios y contraseñas.

Ejecutamos el siguiente comando para crear el archivo y añadir el primer usuario (con mi nombre), teniendo cuidado de no olvidar los dos puntos después del nombre:

```
sudo sh -c "echo -n 'luisdario:' >> /etc/nginx/.htpasswd"
```

Hecho esto, vamos a crear la contraseña cifrada para este usuario de forma interactiva:

```
sudo sh -c "openssl passwd -apr1 >> /etc/nginx/.htpasswd"
```

Repetimos el proceso para crear un segundo usuario con mi primer apellido. Podemos comprobar con un `cat` que los usuarios y las contraseñas aparecen correctamente cifrados en el fichero:

```
cat /etc/nginx/.htpasswd
```

Nos tendría que salir algo así:

![Captura del contenido .htpasswd](./capturas/captura1.png)
