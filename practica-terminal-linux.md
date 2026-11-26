# 🖥️ Laboratorios Prácticos de Terminal Linux

Registro de simulacros de investigación y remediación en línea de comandos (Bash) realizados durante mi preparación en el **Certificado de Ciberseguridad de Google**.

---

## Caso #01: Remediación de Archivo Confidencial Expuesto

### 📋 Escenario
El equipo de auditoría detectó un archivo con información sensible de nómina con permisos inseguros (`-rw-rw-rw-`) dentro del servidor de Recursos Humanos (`servidor-rh`). El objetivo fue localizar el archivo, verificar su contenido y aplicar el principio de menor privilegio.

### 🛠️ Comandos Ejecutados y Resultados

1. **Reconocimiento de ubicación y directorio inicial:**
   ```bash
   pwd
   ls -la
   ```
   *Resultado:* Se confirmó la ruta `/home/analyst` y se identificó el subdirectorio `documentos_rh`.

2. **Exploración del subdirectorio y revisión de permisos:**
   ```bash
   cd documentos_rh
   ls -la
   ```
   *Hallazgo:* El archivo `nomina_confidencial_2026.txt` tenía permisos `-rw-rw-rw-` (`666`), permitiendo lectura y escritura a cualquier usuario del sistema.

3. **Inspección del contenido del archivo:**
   ```bash
   cat nomina_confidencial_2026.txt
   ```
   *Hallazgo:* Se confirmó la exposición de datos financieros (salarios y cuentas bancarias de empleados).

4. **Remediación mediante restricción de permisos (`chmod`):**
   ```bash
   chmod 600 nomina_confidencial_2026.txt
   ls -la
   ```
   *Resultado:* Los permisos cambiaron a `-rw-------` (`600`), dejando acceso de lectura y escritura únicamente para el propietario.

### 💡 Lecciones Clave Aprendidas
* **`/` (barra diagonal):** Separa directorios de subdirectorios o archivos (ej. `documentos_rh/archivo.txt` significa "dentro de `documentos_rh`").
* **`cd ..`:** Permite subir un nivel hacia la carpeta padre sin incluir nombres de archivos.
* **Principio de menor privilegio:** Archivos confidenciales deben restringirse con `chmod 600` (o `chmod go-rw`) para evitar accesos no autorizados.
