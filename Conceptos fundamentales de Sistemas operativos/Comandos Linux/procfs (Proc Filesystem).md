**Definición:** Sistema de archivos pseudo/virtual generado dinámicamente en memoria por el núcleo (normalmente montado en `/proc`) que expone información sobre los procesos y el estado del kernel al **[[Modo Usuario]]**.
- **Características:**
    - No está vinculado a un dispositivo de almacenamiento físico y **no consume espacio en disco**.
    - Permite consultar métricas de hardware y runtime directamente con comandos estándar (ej. `cat /proc/cpuinfo` o `cat /proc/meminfo`).