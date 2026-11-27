---

## Caso #02: Organización de Evidencia y Limpieza de Archivos

### 📋 Escenario
Tras cerrar un incidente de phishing (`INCIDENTE #402`), el directorio de trabajo (`/home/analyst`) contenía evidencia sin clasificar y archivos temporales residuales. El objetivo fue validar el reporte final, archivar la evidencia en una estructura jerárquica y eliminar los archivos innecesarios.

### 🛠️ Comandos Ejecutados y Resultados

1. **Verificación del reporte final (`cat`):**
   ```bash
   cat reporte_final.txt
   ```
   *Resultado:* Se confirmó el cierre del incidente y el bloqueo del dominio malicioso.

2. **Clasificación de evidencia y eliminación de temporales (`mv` y `rm`):**
   ```bash
   mv correo_malicioso.eml evidencia_phishing/
   rm borrador_basura.tmp
   ```
   *Resultado:* El correo malicioso se movió al directorio de evidencia y se eliminó el archivo temporal `.tmp`.

3. **Estructuración de carpetas de archivo (`mkdir`, `mv` y `rmdir`):**
   ```bash
   pwd
   mkdir casos_cerrados
   mv evidencia_phishing /home/analyst/casos_cerrados
   mkdir temp_test
   rmdir temp_test
   ```
   *Resultado:* Se creó el directorio contenedor `casos_cerrados`, se movió la carpeta de evidencia en su interior y se eliminó el directorio de prueba vacío.

### 💡 Lecciones Clave Aprendidas
* **Identificación visual (`ls -la`):** Los directorios comienzan con `d` (`drwxr-xr-x`) y no llevan extensiones de archivo; los archivos regulares comienzan con `-` (`-rw-r--r--`).
* **Rutas relativas vs. absolutas:** Estando en `/home/analyst`, `evidencia_phishing/` (relativa) y `/home/analyst/evidencia_phishing/` (absoluta) apuntan al mismo destino.
* **Eliminación segura:** `rm` elimina archivos individuales, `rmdir` elimina directorios vacíos y `rm -r` elimina directorios con contenido en su interior.
