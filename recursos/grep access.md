# 🔍 Laboratorio: Filtrado de Contenidos en Linux (`grep` y Tuberías)

> **Objetivo del Laboratorio:** Utilizar comandos de terminal en Bash y tuberías (`|`) para analizar registros de seguridad del servidor, filtrar archivos de acceso y auditar cuentas de usuarios eliminados.

---

## 1. Resumen de Tareas y Comandos Ejecutados

| Tarea | Propósito de Seguridad | Comando Ejecutado | Resultado Clave |
| :--- | :--- | :--- | :--- |
| **Análisis de Logs** | Identificar intentos de acceso no autorizados y fallos de contraseña en el servidor. | `grep "error" server_logs.txt` | Se filtraron 6 eventos críticos de error y acceso no autorizado. |
| **Filtrado de Archivos** | Localizar rápidamente reportes relacionados con permisos y accesos. | `ls \| grep access` | Se aislaron 4 archivos de auditoría (`Q1` a `Q4_access.txt`). |
| **Auditoría de Usuarios** | Verificar si una cuenta específica fue dada de baja del sistema. | `grep "jhill" Q2_deleted_users.txt` | Se confirmó la eliminación del usuario `jhill` en el segundo trimestre. |

---

## 2. Detalle Paso a Paso en Terminal

### 🛡️ Tarea 1: Búsqueda de errores en registros del servidor
Navegación hacia el directorio de registros y extracción de líneas que contienen la cadena `"error"`:
```bash
cd /home/analyst/logs
grep "error" server_logs.txt
```

### 📂 Tarea 2: Filtrado de nombres de archivo con tuberías (`|`)
Encadenamiento de la salida del comando `ls` hacia `grep` para filtrar archivos específicos dentro de `/home/analyst/reports/users`:
```bash
cd /home/analyst/reports/users
ls | grep access
```

### 👤 Tarea 3: Búsqueda de usuarios eliminados
Inspección directa dentro del reporte de bajas del sistema para confirmar el estado de un usuario:
```bash
grep "jhill" Q2_deleted_users.txt
```

---

## 3. Habilidades Técnicas Demostradas

* **Navegación del sistema de archivos:** Uso eficiente de rutas absolutas con `cd` y listado de directorios con `ls`.
* **Filtrado de información crítica:** Búsqueda de patrones específicos dentro de archivos de texto plano mediante `grep`.
* **Redirección de comandos:** Uso del operador tubería (`|`) para conectar la salida estándar de un comando con la entrada de otro.
