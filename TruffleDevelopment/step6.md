## Pruebas del contrato

Para realizar pruebas unitarias del contrato inteligentes se
crea un nuevo archivo `test/guestbook.js` y se le agrega el siguiente
código:


<pre class="file" data-filename="test/guestbook.js" data-target="replace">
const gb = artifacts.require('GuestBook')

contract('GuestBook', accounts => {
  let instance;

  // deploy before running tests
  before( async () => {
    instance = await gb.deployed();
  })

  // tests
  describe('deployment', async () => {

      // Comprobar que ha sido desplegado exitosamente
      it('Despliegue exitoso', async () => {
        const address = await instance.address
        assert.notEqual(address, 0x0)
        assert.notEqual(address, '')
        assert.notEqual(address, null)
        assert.notEqual(address, undefined)
      })

      // Comprobar que el número de visitantes al momento de empezar es cero
      it('numeroVisitantes debe ser cero', async () => {
        const expectedValue=0;
        const actualValue = await instance.numeroVisitantes();
        console.log('expectedValue', expectedValue)
        console.log('actualValue', actualValue, parseInt(actualValue))
        assert.equal(expectedValue, parseInt(actualValue), 'actualValue is not equal to actualValue')
      })

      // Comprobar que se registran mensajes en el libro de visitas
      it('publica visita', async() => {
        const msg = 'Hola, saludos de un visitante';
        await instance.registrarVisita(msg)
        const nro = await instance.numeroVisitantes();
        assert.equal(1, parseInt(nro), 'Debe haber un registro de visita')
        const visita = await instance.visitas(0);
        assert.equal(msg, visita.mensaje, 'El mensaje recuperado debe ser igual al publicado')
      })


    })




});
</pre>




Para realizar la comprobaciones de las pruebas unitarias se ejecuta:

`truffle test`{{execute}}



<!--

Included in truffle are the Mocha testing framework and the Chai assertion library.

-->
