## Preparación del entorno de desarrollo

La consola Linux (CentOS 7) en la parte inferior derecha es una instalación básica de linux.
Para instalar las herramientas necesarias para el desarrollo de contratos inteligentes, se deben
ingresar los siguientes comandos en la consola:

1. Cambiar al rol root  
`su -`{{execute}}

2. Desintalar versiones anteriores de nodejs en caso de estar instaladas  
`yum erase -y nodejs`{{execute}}

3. Instalar las herramientas de desarrollo (Lenguajes C y C++) en el ambiente linux  
`yum install -y gcc.x86_64 gcc-c++.x86_64 make.x86_64`{{execute}}

4. Actualizar los repositorios Yum para obtener una versión actual de node.js  
`curl -sL https://rpm.nodesource.com/setup_10.x | bash -`{{execute}}

5. Instalar node.js  
`yum install -y nodejs`{{execute}}

6. Salir del rol de superusuario  
`exit`{{execute}}

7. Comprobar versiones instaladas de node.js y de npm  
`node -v`{{execute}}  
`npm -v`{{execute}}  

