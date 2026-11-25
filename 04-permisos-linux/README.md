# 🐧 Gestión de Permisos de Archivo con Comandos de Linux

## 📌 Descripción del Proyecto
Este proyecto consiste en auditar y corregir los permisos de archivos y directorios dentro de un entorno Linux para el departamento de investigación de una organización. El objetivo es aplicar el **Principio de Mínimo Privilegio (PoLP)** mediante la interfaz de línea de comandos (**Bash**) para evitar accesos o modificaciones no autorizadas sobre información confidencial.

## 🎯 Objetivos del Laboratorio
* Navegar por el sistema de archivos de Linux utilizando comandos de terminal (`cd`, `pwd`, `ls`).
* Inspeccionar permisos actuales de archivos regulares y ocultos (`ls -la`).
* Restringir permisos excesivos para usuarios, grupos y otros mediante el comando `chmod`.
* Verificar la correcta aplicación de los controles de acceso tras la remediación.

## 🔍 Auditoría y Remediación Aplicada

| Archivo / Directorio | Permisos Iniciales | Riesgo Identificado | Comando Ejecutado | Permisos Finales |
| :--- | :--- | :--- | :--- | :--- |
| `proyecto_k.txt` | `-rw-rw-rw-` | Otros usuarios (`o`) tienen permiso de lectura y escritura global. | `chmod o-rw proyecto_k.txt` | `-rw-rw----` |
| `proyecto_m.txt` | `-rw-rw----` | El grupo (`g`) tiene permisos de escritura innecesarios sobre un archivo sensible. | `chmod g-w proyecto_m.txt` | `-rw-r-----` |
| `.proyecto_x.txt` | `-rw-r--r--` | Archivo oculto accesible para lectura por el grupo (`g`) y otros usuarios (`o`). | `chmod go-r .proyecto_x.txt` | `-rw-------` |
| `borradores/` | `drwxrwxr-x` | Directorio accesible para lectura y ejecución por usuarios externos al grupo (`o`). | `chmod o-rx borradores` | `drwxrwx---` |

## 💻 Secuencia de Comandos Utilizados (Bash)

```bash
# 1. Ubicarse e ingresar al directorio del departamento
pwd
cd proyectos

# 2. Listar todos los archivos (incluidos los ocultos) y sus permisos actuales
ls -la

# 3. Aplicar principio de mínimo privilegio con chmod
chmod o-rw proyecto_k.txt
chmod g-w proyecto_m.txt
chmod go-r .proyecto_x.txt
chmod o-rx borradores

# 4. Verificar que los nuevos permisos se aplicaron correctamente
ls -la
```

## 🛡️ Impacto de Seguridad y Conclusiones
Mediante el uso de `chmod` en modo simbólico, se eliminaron los vectores de exposición interna donde usuarios no autorizados podían leer o alterar documentos críticos. Esta práctica refuerza la **confidencialidad** e **integridad** de los datos en servidores Linux sin afectar la operatividad de los propietarios legítimos.

## 📚 Competencias Demostradas
* Administración básica de sistemas Linux mediante línea de comandos (**CLI / Bash**).
* Lectura e interpretación de permisos en el sistema de archivos de Linux (`r`, `w`, `x`).
* Implementación práctica del **Principio de Mínimo Privilegio (PoLP)**.
