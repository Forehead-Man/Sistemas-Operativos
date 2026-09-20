**Tipo de Núcleo:** **[[Núcleo Híbrido]]**.

**Definición:** Es la familia de arquitectura de sistemas operativos de 32 y 64 bits desarrollada por Microsoft (liderada por el diseñador Dave Cutler e introducida en 1993) sobre la cual se basan las versiones modernas de Windows (Windows XP, 7, 10, 11, Windows Server, etc.).

**Características e Info Clave:**

- **Arquitectura Híbrida:** Combina la estructura conceptual de un **[[Micronúcleo]]** (separación en subsistemas/servidores) con el rendimiento de un **[[Núcleo Monolítico]]**.

- **Capa de Abstracción de Hardware ([[HAL]]):** Utiliza un componente en la base del núcleo para aislar y abstraer las diferencias de hardware del procesador y chipset respecto al resto del sistema.

- **Estabilidad y ABI:** Ofrece una Interfaz Binaria de Aplicación (ABI) relativamente estable para controladores y componentes internos.

- **Subsistema Gráfico e I/O:** Aunque inicialmente el sistema gráfico residía en modo usuario, a partir de NT 4.0 se integró el subsistema gráfico (GDI) dentro del espacio de núcleo para mejorar sustancialmente el rendimiento de la interfaz gráfica (GUI).