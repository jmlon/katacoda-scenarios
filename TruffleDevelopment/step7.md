## Interaccion con el contrato via consola



Ingresar a la consola interactiva de truffle donde se puede interacturar con el contrato
inteligente utilizando la libreria web3.js:
`truffle console`{{execute}}

guestbook = await GuestBook.deployed()
guestbook.address
await guestbook.numeroVisitantes()
await guestbook.registrarVisita('Hola, saludo desde Medellin')
await guestbook.numeroVisitantes()

await guestbook.visitas(0) // rango 0..N-1

let x = await guestbook.visitas(1)
x.mensaje
x.visitante
x.timestamp

let n = await guestbook.numeroVisitantes()
for(let i=0; i<n; i++) { guestbook.visitas(i).then( r => console.log(r.mensaje) ) }

Ctrl-D para salir de la consola de truffle
