**Definición:** Estructura de seguridad de acceso a archivos dividida en tres clases de usuarios y tres tipos de permisos básicos:
- **Clases:** 
	- Propietario (`u`)
	- Grupo propietario (`g`)
	- Otros (`o`).
- **Tipos de acceso:**
	- Lectura (`r` = 4)
	- Escritura (`w` = 2)
	- Ejecución (`x` = 1).

- **Representación Numérica/Octal:** Suma de los valores bits (ej. `chmod 755` otorga `rwx` al dueño, y `r-x` a grupo y otros).