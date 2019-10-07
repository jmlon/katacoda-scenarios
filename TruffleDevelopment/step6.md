## Pruebas del contrato

Para realizar pruebas unitarias del contrato inteligentes se
crea un nuevo archivo `test/guestbook.js` y se le agrega el siguiente
código:

<pre class="file" data-filename="test/guestbook.js" data-target="replace">
const gb = artifacts.require('GuestBook')
const assert = require('assert')
let instance;

contract('GuestBook', accounts => {

  // deploy before running tests
  beforeEach( async () => {
    instance = await gb.deployed();
  })

  // tests

  // Comprobar que el número de visitantes al momento de empezar es cero
  it('numeroVisitantes debe ser cero', async () => {
    const expectedValue=0;
    const actualValue = await instance.numeroVisitantes();
    console.log('expectedValue', expectedValue)
    console.log('actualValue', actualValue, parseInt(actualValue))
    assert.equal(expectedValue, parseInt(actualValue), 'actualValue is not equal to actualValue')
  })


}
</pre>


Para realizar la comprobaciones de las pruebas unitarias se ejecuta:

`truffle test`{{execute}}
