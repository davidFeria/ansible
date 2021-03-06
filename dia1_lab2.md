# Dia 1 - Laboratorio 2

El objetivo de este laboratorio es crear un playbook que dadas 3 máquinas haga las siguientes tareas:

Dado un grupo www de 2 máquinas

1. Instalar el servidor http nginx
2. Configurar el servidor http nginx 
3. Active y arranque el servidor http nginx 
4. Despliegue una página de bienvenida

Dado un grupo mariadb de 1 máquina

1. Instalar el servidor mariadb
2. Configurar mariadb
3. Activar y arrancar el servidor mariadb


Dejando segregados los roles para configurar mariadb y nginx

## Arrancar el laboratiorio

```bash
ansible-playbook crear-lab3vm.yml
```

Tras unos segundos este playbook habrá creado 3 máquinas Centos 7, podéis ver sus IP's en el 
fichero ```inventories/laboratorio.txt```

Para acceder a ellas podréis hacerlo mediante el usuario "centos", con la clave privada que
se os ha dado junto con el fichero aws_vault.yml

Recomendamos dejar la clave privada en el directorio $HOME del usuario que vayáis a usar
en la VM de laboratorio que se usa para control. De esta forma los comandos de la documentación
se ajustarán al entorno.

Ejemplo de comando para acceder a una de las máquinas de lab:

```ssh -i $HOME/curso-ansible-verano.pem centos@a.b.c.d```


## Desarrollo del laboratorio

Este laboratorio está pensado para consolidar los conocimientos del laboratorio 1.

Se podrá reutilizar código del laboratorio 1.

Los pasos, a modo de guía, serían:
1. Preparar el inventario
2. Configurar nginx y desplegar la página
3. Crear el rol de mariadb
4. Aplicar el playbook
5. Validar el resultado

Se comprobará con el profesor el playbook resultante

## Fin del laboratorio

Ha acabado el laboratorio, tras él deberíamos haber consolidado los conceptos de:
- playbook
- play
- task
- handler
- role
- variable (var)
- fact
- template
- inventory

Procederemos a la destrucción del laboratorio:

```bash
ansible-playbook borrar-lab3vm.yml
```

