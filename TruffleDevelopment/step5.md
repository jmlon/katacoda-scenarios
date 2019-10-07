## Depliegue y pruebas del contrato

Para desplegar el contrato se crea un script de migracion del contrato:
Crear un nuevo archivo `migrations\2_guestbook.js` y agregar el siguiente
contenido:

---

  var GuestBook = artifacts.require("./GuestBook.sol");

  module.exports = function(deployer) {
    deployer.deploy(GuestBook);
  };

---
<pre class="file" data-filename="app.js"
data-target="replace">var GuestBook = artifacts.require("./GuestBook.sol");

module.exports = function(deployer) {
  deployer.deploy(GuestBook);
};
</pre>
