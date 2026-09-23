Un **semáforo** ($s$) es una estructura de datos abstracta utilizada para la **sincronización de procesos**. Funciona como un **contador de permisos** de acceso a recursos compartidos.
## 1. Operaciones Primarias

Las operaciones sobre un semáforo son **atómicas** (o indivisibles) para garantizar la **exclusión mutua**.

### A. `wait(s)` *(También conocida como $P$ o `down`)*
Solicita el uso de un recurso.
* **Lógica:**
  $$\text{Si } s > 0 \implies s = s - 1 \quad (\text{Ocupa recurso})[cite: 1]$$
  $$\text{Si } s = 0 \implies \text{El proceso pasa a estado BLOQUEADO en la cola de } s[cite: 1]$$
### B. `signal(s)` *(También conocida como $V$ o `up`)*
Notifica la liberación de un recurso.
* **Lógica:**
  $$\text{Si hay procesos bloqueados en } s \implies \text{Desbloquea (despierta) a uno}[cite: 1]$$
  $$\text{Si NO hay procesos esperando } \implies s = s + 1[cite: 1]$$

---

## 2. Tipos de Semáforos

* **Semáforo Contador / General:** Admite valores enteros positivos ($s \ge 0$). Se utiliza para controlar el acceso a un conjunto de instancias de un mismo recurso.
* **Semáforo Binario:** Su valor solo toma los estados $0$ o $1$. Es equivalente en comportamiento a un **Mutex** para garantizar exclusión mutua.

---

## 3. Propiedades Clave

1. **Atomicidad / Indivisibilidad:** Ni la verificación del valor ni la modificación de $s$ pueden ser interrumpidas a la mitad por el Planificador (Scheduler).
2. **Espera Pasiva:** A diferencia de un *Spinlock* (espera activa), cuando $s = 0$ el proceso cede el uso de la CPU y pasa a la cola de bloqueados del kernel.