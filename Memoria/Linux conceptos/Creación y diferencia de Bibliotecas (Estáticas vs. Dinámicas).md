- **Librería Estática (`.a`):** Se empaqueta con `ar rcs libsaludo.a saludo.o`. Al enlazarla (`gcc ... -lsaludo`), el código de la librería se **copia físicamente** dentro del ejecutable.
- **Librería Compartida/Dinámica (`.so`):** Se genera con `gcc -shared -fPIC ...`. El ejecutable solo guarda una **referencia/dependencia**.

- **Comando clave para inspeccionar dependencias:** `ldd saludo-compartido` (te muestra qué `.so` necesita el programa para poder correr).