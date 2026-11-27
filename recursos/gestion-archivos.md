# 📁 Laboratorio: Gestión de Directorios y Archivos en Linux

> **Objetivo del Laboratorio:** Dominar los comandos esenciales de Bash para crear, mover, copiar, renombrar y eliminar directorios y archivos de registro dentro de un entorno de análisis de seguridad.

---

## 1. Resumen de Comandos de Gestión

| Comando | Significado | Propósito en Ciberseguridad | Ejemplo Práctico |
| :--- | :--- | :--- | :--- |
| **`mkdir`** | *Make Directory* | Crear carpetas para organizar evidencias, reportes o respaldos. | `mkdir logs_backup` |
| **`rmdir`** | *Remove Directory* | Eliminar directorios vacíos que ya no son necesarios en el sistema. | `rmdir carpeta_vacia` |
| **`touch`** | Crear / Actualizar | Generar rápidamente archivos vacíos de registro o configuración. | `touch alerta.txt` |
| **`cp`** | *Copy* | Duplicar archivos críticos antes de analizarlos o modificarlos. | `cp log.txt log_copia.txt` |
| **`mv`** | *Move* | Reubicar archivos entre carpetas o cambiarles el nombre. | `mv reporte.txt /respaldo/` |
| **`rm`** | *Remove* | Borrar de forma permanente archivos obsoletos o maliciosos. | `rm temporal.txt` |

---

## 2. Operaciones Paso a Paso en Terminal

### 📂 Creación de estructura de directorios (`mkdir`)
Creación de nuevas carpetas para clasificar archivos del sistema:
```bash
mkdir reportes
mkdir -p auditoria/2026/noviembre
```
*(La opción `-p` permite crear una ruta completa con varias subcarpetas al mismo tiempo).*

### 📄 Creación de archivos vacíos (`touch`)
Generación de archivos nuevos dentro del directorio de trabajo actual:
```bash
touch incidentes.log
touch notas_analisis.txt
```

### 📋 Copia de seguridad de archivos (`cp`)
Duplicación de un archivo conservando el original intacto:
```bash
cp incidentes.log incidentes_respaldo.log
cp incidentes.log /home/analyst/reportes/
```

### 🔄 Movimiento y renombrado (`mv`)
El comando `mv` cumple dos funciones principales dependiendo de si el destino es una carpeta o un nuevo nombre:
```bash
# Mover un archivo a otra carpeta
mv notas_analisis.txt /home/analyst/reportes/

# Renombrar un archivo en la misma ubicación
mv incidentes.log incidentes_cerrados.log
```

### 🗑️ Eliminación de archivos y carpetas (`rm` y `rmdir`)
Limpieza del entorno eliminando elementos innecesarios (en Linux, estos comandos borran sin enviar a papelera):
```bash
# Eliminar un archivo específico
rm incidentes_respaldo.log

# Eliminar un directorio completamente vacío
rmdir carpeta_temporal
```

---

## 3. Habilidades Técnicas Demostradas

* **Organización de entornos:** Creación y estructuración de directorios mediante `mkdir` y `rmdir`.
* **Preservación de evidencia:** Creación de copias de seguridad con `cp` antes de manipular archivos de registro.
* **Mantenimiento del sistema:** Reubicación, renombrado y limpieza segura de archivos mediante `touch`, `mv` y `rm`.
