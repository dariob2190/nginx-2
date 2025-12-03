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
