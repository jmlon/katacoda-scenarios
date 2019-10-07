## Interaccion con el contrato via consola

Arrancar el emulador local de Ethereum para efecto de poder desarrollar
las pruebas. En una nueva pestana 'Terminal' ejecutar el comando:
`ganache-cli`{{execute}}


Configurar la red de desarrollo donde se desplegara el contrato inteligente para las pruebas:
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


Compilar el contrato inteligente
`truffle compile`{{execute}}

Migrar (desplegar el contrato inteligente) en el blockchain local de ganache:
`truffle migrate`{{execute}}

Ingresar a la consola interactiva de truffle donde se puede interacturar con el contrato
inteligente utilizando la libreria web3.js:
`truffle console`{{execute}}
