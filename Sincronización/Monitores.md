Un monitor es un mecanismo de abstracción de datos, que permite representar el recurso compartido.

Es similar a un objeto en la programación orientada a objetos ya que consta de variables y procedimientos.

Las variables pueden accederse sólo a través de los procedimientos del monitor pero a diferencia de los objetos, solo 1 proceso a la vez podrá acceder a estos procedimientos.

Cuando un proceso ejecuta un procedimiento del monitor se dice que el proceso ha “entrado en el monitor”. Cualquier otro proceso que quiera acceder se bloqueará hasta que el proceso anterior “salga del monitor”.

![[Ej monitor.png]]