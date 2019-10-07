## Creación de un contrato inteligente básico

En este paso se va a crear el contrato inteligente GuestBook, el cual ofrece la funcionalidad de registrar todos los visitantes de una página, guardar la fecha de visita, la dirección del visitante y un mensaje que deje el visitante.

A través de editor de texto, crear el archivo fuente del contrato en la carpeta
`contracts` con el nombre `GuestBook.sol`. La extensión .sol identifica los archivos fuente en el lenguaje Solidity.

Ingresar el siguiente programa en el editor de texto:  

`
pragma solidity ^0.5.8;

contract GuestBook {

  struct Visita {
    string mensaje;
    address visitante;
    uint256 timestamp;
  }


  Visita[] public visitas;
  uint256 public numeroVisitantes;


  function registrarVisita(string memory mensaje) public {
    require(bytes(mensaje)[0] != 0);
    Visita memory laVisita = Visita(mensaje, msg.sender, now);
    numeroVisitantes++;
    visitas.push(laVisita);
  }


}
`
