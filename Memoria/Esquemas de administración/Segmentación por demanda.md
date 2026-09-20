Así como la [[paginación simple]] puede modificarse para crear [[paginación por demanda]],
la [[Segmentación Simple|segmentación]] también se puede modificar para crear segmentación por demanda.

Sin embargo, la variabilidad de los tamaños de los segmentos complica muchos de los problemas encontrados en la paginación por demanda. En la decisión del intercambio, el tamaño de los segmentos se convierte en un factor importante para decidir qué segmentos intercambiar. Una forma mucho más práctica de implementar segmentación en un sistema con memoria virtual es combinarlo con paginación por demanda. 

La capacidad de memoria virtual se crea por paginación por demanda de los segmentos.