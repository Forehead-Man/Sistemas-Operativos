Los mensajes son copiados desde el espacio de memoria del emisor hacia el del
receptor.

En algunos casos se recurre al núcleo del sistema operativo para que almacene
el mensaje hasta que el receptor esté listo. El proceso receptor debe contar con
un buffer para poder almacenar el mensaje.

Si tenemos comunicación síncrona, es imposible usar buffer, (buffer nulo) en el
caso de la comunicación asíncrona, deberíamos tener un buffer de capacidad
ilimitada.