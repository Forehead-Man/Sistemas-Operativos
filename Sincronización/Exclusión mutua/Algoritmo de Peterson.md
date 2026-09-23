El algoritmo de Peterson, también conocido como solución de Peterson, es un algoritmo de programación concurrente para [[exclusión mutua]], que permite a dos o más procesos o hilos de ejecución compartir un recurso sin conflictos, utilizando sólo memoria compartida para la comunicación.

Gary L. Peterson desarrolló en 1981 el algoritmo básico para dos procesos, como una simplificación del [[algoritmo de Dekker]]. El algoritmo básico puede generalizarse fácilmente a un número arbitrario de procesos.
```
bandera[0] = false
  bandera[1] = false
  turno      // No es necesario asignar un turno
  p0: bandera[0] = true                      p1: bandera[1] = true
      turno = 1                                 turno = 0
      while( bandera[1] && turno == 1 );        while( bandera[0] && turno == 0 );
      //{ no hace nada; espera. }               //{ no hace nada; espera. }
      // sección crítica                        // sección crítica
                                           
      // fin de la sección crítica              // fin de la sección crítica
      bandera[0] = false                        bandera[1] = false
```

Los procesos p0 y p1 no pueden estar en la sección crítica al mismo tiempo: si p0 está en la sección crítica, entonces bandera[0] = true, y ocurre que bandera[1] = false, con lo que p1 ha terminado la sección crítica, o que la variable compartida turno = 0, con lo que p1 está esperando para entrar a la sección crítica. En ambos casos, p1 no puede estar en la sección crítica.
