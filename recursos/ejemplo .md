# 📁 Laboratorio: Gestionar Archivos y Directorios con Comandos de Linux

> **Objetivo del Laboratorio:** Administrar la estructura de archivos y directorios en un entorno Linux utilizando comandos de terminal en Bash (`mv`, `rmdir`, `mkdir`, `rm`, `touch`) y el editor de texto `nano` para documentar tareas de seguridad.

---

## 1. Resumen de Tareas y Comandos Ejecutados

| Tarea | Objetivo de Administración | Comando Ejecutado | Resultado Obtenido |
| :--- | :--- | :--- | :--- |
| **1. Mover archivos** | Reubicar un archivo de parches hacia el directorio de reportes. | `mv Q3patches.txt /home/analyst/reports` | Se movió `Q3patches.txt` a `/home/analyst/reports`. |
| **2. Eliminar directorio** | Borrar un directorio temporal vacío del sistema. | `rmdir temp` | Se eliminó el directorio `/home/analyst/temp`. |
| **3. Crear directorio** | Crear una nueva carpeta dedicada a registros del sistema. | `mkdir logs` | Se creó el directorio `/home/analyst/logs`. |
| **4. Eliminar archivo** | Remover un archivo de notas obsoleto para limpiar el entorno. | `rm tempnotes.txt` | Se eliminó `tempnotes.txt` de `/home/analyst/notes`. |
| **5. Crear nuevo archivo** | Generar un archivo vacío de seguimiento de actividades. | `touch tasks.txt` | Se creó el archivo `tasks.txt` en `/home/analyst/notes`. |
| **6. Editar y verificar** | Documentar las tareas completadas dentro del archivo y validar. | `nano tasks.txt` / `cat tasks.txt` | Se guardó y verificó el registro de tareas completadas. |

---

## 2. Detalle Paso a Paso en Terminal

### 📦 Tarea 1: Reubicación de archivos de parches (`mv`)
Traslado del archivo `Q3patches.txt` desde `/home/analyst/notes` hacia la carpeta `/home/analyst/reports`:
```bash
cd /home/analyst/notes
mv Q3patches.txt /home/analyst/reports
ls /home/analyst/reports
```

### 🗑️ Tarea 2: Eliminación de directorios vacíos (`rmdir`)
Limpieza del directorio temporal `/home/analyst/temp` que ya no se encontraba en uso:
```bash
cd /home/analyst
rmdir temp
ls
```

### 📂 Tarea 3: Creación de directorio de registros (`mkdir`)
Generación de la carpeta `logs` dentro del directorio principal del analista:
```bash
mkdir /home/analyst/logs
ls
```

### 🧹 Tarea 4: Eliminación de archivos innecesarios (`rm`)
Borrado permanente del archivo residual `tempnotes.txt` ubicado en `/home/analyst/notes`:
```bash
cd /home/analyst/notes
rm tempnotes.txt
ls
```

### 📝 Tarea 5 y 6: Creación y edición de archivo de registro (`touch` y `nano`)
Creación del archivo `tasks.txt`, edición mediante el editor de terminal `nano` y verificación de su contenido con `cat`:
```bash
touch tasks.txt
nano tasks.txt
cat tasks.txt
```

**Contenido registrado en `tasks.txt`:**
```text
Completed tasks
1. Managed file structure in /home/analyst
```

---

## 3. Habilidades Técnicas Demostradas

* **Gestión de directorios:** Creación y eliminación segura de carpetas mediante `mkdir` y `rmdir`.
* **Manipulación de archivos:** Movimiento, creación y eliminación de archivos del sistema con `mv`, `touch` y `rm`.
* **Edición en línea de comandos:** Creación y modificación de archivos de texto directamente en terminal usando `nano` y lectura rápida con `cat`.
