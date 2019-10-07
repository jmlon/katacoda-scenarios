## Configuración de la migración

Para desplegar el contrato se crea un script de migracion del contrato:
Crear un nuevo archivo `migrations/2_guestbook.js` y agregar el siguiente
contenido:  

<pre class="file" data-filename="migrations/2_guestbook.js"
data-target="replace">var GuestBook = artifacts.require("./GuestBook.sol");

module.exports = function(deployer) {
  deployer.deploy(GuestBook);
};
</pre>


Arrancar el emulador local de Ethereum para efecto de poder desarrollar
las pruebas. En una nueva pestaña 'Terminal' ejecutar el comando:  
`ganache-cli`{{execute}}


Configurar la red de desarrollo donde se desplegará el contrato inteligente para las pruebas:
Editar el archivo truffle-config.js y en la sección networks, activar la red de desarrollo,
la cual se ejecuta sobre ganache-cli:  

<pre class="file" data-filename="GuestBook/truffle-config.js" data-target="replace">
networks: {
    development: {
      host: '127.0.0.1',
      port: 8545,
      network_id: '*' // Match any network id
    }
}
</pre>


Migrar (desplegar el contrato inteligente) en el blockchain local de ganache:  
`truffle migrate`{{execute}}
