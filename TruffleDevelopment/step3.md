## Inicialización de un proyecto Truffle

Truffle ofrece varias funciones para facilitar el desarrollo de contratos inteligentes.
En primer lugar debemos crear un directorio para el proyecto e inicializarlo como un proyecto Truffle:

`cd`{{execute}}
`mkdir GuestBook`{{execute}}
`cd GuestBook`{{execute}}
`truffle init`{{execute}}

Luego de inicializar el proyecto, truffle crea el árbol de directorios y archivos
iniciales del proyecto así:

- `contracts` : Contiene el código fuente de los contratos del proyecto.
- `migrations` : Contiene el codigo utilizado por Truffle para "migrar el estado de un
contrato", es decir desplegar un contrato en el blockchain.
- `test` : Aquí es donde se coloca el código que permite ejecutar pruebas del correcto funcionamiento del contrato.
- `truffle-config.js` : Es la configuración del proyecto Truffle.
- `build` : Se crea luego de haber realizado una compilación. Contiene el código compilado.
 
