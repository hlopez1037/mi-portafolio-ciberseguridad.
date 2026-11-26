# 🐧 Guía Rápida de Comandos Linux (Bash) — Ciberseguridad

> **Regla de Oro:** Linux distingue estrictamente entre **MAYÚSCULAS y minúsculas**. Todos los comandos se escriben en **minúsculas**.

---

## 1. Navegación y Exploración de Archivos

| Comando | Significado | Qué hace | Ejemplo |
| :--- | :--- | :--- | :--- |
| **`pwd`** | *Print Working Directory* | Muestra la ruta exacta de la carpeta donde estás parado. | `pwd` |
| **`ls`** | *List* | Muestra una lista simple de los archivos y carpetas actuales. | `ls` |
| **`ls -l`** | *List (Long)* | Muestra la lista detallada con dueño, fecha y **permisos**. | `ls -l` |
| **`ls -a`** | *List (All)* | Muestra todos los archivos, incluyendo los **ocultos** (empiezan con `.`). | `ls -a` |
| **`ls -la`** | *List (Long + All)* | Muestra el detalle completo y **permisos de todos los archivos (incluso ocultos)**. | `ls -la` |
| **`cd`** | *Change Directory* | Entra a una carpeta específica. | `cd proyectos` |
| **`cd ..`** | *Change Directory (Up)* | Sale un nivel hacia atrás (regresa a la carpeta anterior). | `cd ..` |
| **`cd ~`** | *Change Directory (Home)* | Regresa directamente a tu carpeta personal principal. | `cd ~` |

---

## 2. Lectura y Búsqueda en Registros (Logs)

| Comando | Significado | Qué hace | Ejemplo |
| :--- | :--- | :--- | :--- |
| **`cat`** | *Concatenate* | Imprime en pantalla todo el contenido de un archivo. | `cat accesos.log` |
| **`head -n X`** | *Head* | Muestra solo las primeras `X` líneas de un archivo. | `head -n 10 auth.log` |
| **`tail -n X`** | *Tail* | Muestra solo las últimas `X` líneas de un archivo. | `tail -n 10 auth.log` |
| **`grep`** | *Global Regular Expression Print* | Filtra y muestra solo las líneas que contienen una palabra exacta. | `grep "ERROR" auth.log` |

---

## 3. Creación y Gestión de Archivos

| Comando | Significado | Qué hace | Ejemplo |
| :--- | :--- | :--- | :--- |
| **`mkdir`** | *Make Directory* | Crea una nueva carpeta (directorio). | `mkdir evidencias` |
| **`touch`** | *Touch* | Crea un archivo nuevo vacío. | `touch reporte.txt` |
| **`rm`** | *Remove* | Elimina un archivo (¡cuidado, no va a la papelera!). | `rm borrador.txt` |
| **`rmdir`** | *Remove Directory* | Elimina una carpeta vacía. | `rmdir carpeta_vacia` |

---

## 4. Anatomía de los Permisos en Linux (`ls -l`)

Cuando ejecutas `ls -l`, los primeros 10 caracteres te dicen todo sobre la seguridad del archivo:

```text
  -     r w -     r - -     - - -
  │     └──┬──┘   └──┬──┘   └──┬──┘
Tipo    Usuario    Grupo     Otros
        (u)        (g)       (o)
```

* **Primer carácter (Tipo):**
  * **`-`** = Archivo normal
  * **`d`** = Directorio (carpeta)
* **Letras de permisos:**
  * **`r`** = Lectura (*Read*)
  * **`w`** = Escritura (*Write*)
  * **`x`** = Ejecución (*Execute*)
  * **`-`** = Sin permiso

---

## 5. Cambiar Permisos con `chmod` (Modo Simbólico)

**Fórmula:** `chmod [A quién][Qué hacer][Qué permiso] nombre_del_archivo`

### 1. A quién:
* **`u`** = Usuario dueño (*User*)
* **`g`** = Grupo (*Group*)
* **`o`** = Otros (*Others*)
* **`a`** = Todos (*All*)

### 2. Qué hacer:
* **`+`** = Agregar permiso
* **`-`** = Quitar permiso
* **`=`** = Asignar exactamente ese permiso

### 3. Qué permiso:
* **`r`** = Lectura (*Read*)
* **`w`** = Escritura (*Write*)
* **`x`** = Ejecución (*Execute*)

### Ejemplos Prácticos de `chmod`:
* Quitar lectura a otros: `chmod o-r archivo.txt`
* Quitar lectura y escritura a otros: `chmod o-rw archivo.txt`
* Quitar escritura al grupo: `chmod g-w archivo.txt`
* Dar ejecución al usuario dueño: `chmod u+x script.sh`
* Dos cambios a la vez (separados por coma, sin espacios): `chmod g-w,o-r informe.txt`

* ## 🛠️ Control de Terminal y Gestión de Paquetes (`apt`)

### Limpieza y Ayuda
* `clear` (o `Ctrl + L`) — Limpia el historial visible en la pantalla de la terminal.
* `man [comando]` — Abre el manual de instrucciones oficial de un comando (presiona `q` para salir).

### Instalación y Gestión de Programas (Debian/Ubuntu)
* `sudo [comando]` — Ejecuta una acción con privilegios de administrador (*Superuser Do*).
* `sudo apt update` — Actualiza el índice local de paquetes disponibles en los repositorios.
* `sudo apt install [paquete]` — Descarga e instala un programa (ej. `sudo apt install nload`).
* `sudo apt remove [paquete]` — Desinstala un programa manteniendo sus archivos de configuración.

### Monitoreo en Tiempo Real
* `nload` — Muestra el tráfico de red entrante y saliente en tiempo real (presiona `q` o `Ctrl + C` para salir).

