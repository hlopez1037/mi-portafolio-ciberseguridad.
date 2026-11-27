---

## Caso #03: Caza de Intrusos en Registros del Sistema (`grep` y Redirección)

### 📋 Escenario
Se detectó actividad anómala en los inicios de sesión SSH del servidor (`server01`). Dado que el archivo `/var/log/auth.log` superaba los 4 MB, fue necesario inspeccionar los eventos recientes y filtrar intentos de fuerza bruta sin saturar la consola, extrayendo únicamente las líneas relevantes como evidencia.

### 🛠️ Comandos Ejecutados y Resultados

1. **Inspección de eventos recientes (`tail`):**
   ```bash
   pwd
   tail -n 5 auth.log
   ```
   *Resultado:* Se visualizaron las últimas 5 entradas del log, detectando múltiples fallos de autenticación consecutivos.

2. **Filtrado de intentos fallidos (`grep`):**
   ```bash
   grep "Failed password" auth.log
   ```
   *Hallazgo:* Se identificó un ataque de fuerza bruta contra el usuario `admin` originado desde la dirección IP `185.220.101.44`.

3. **Extracción y verificación de evidencia (`>` y `cat`):**
   ```bash
   grep "Failed password" auth.log > /home/analyst/alerta_intrusion.txt
   ls /home/analyst/alerta_intrusion.txt
   cat /home/analyst/alerta_intrusion.txt
   ```
   *Resultado:* Las 5 líneas de evidencia se exportaron exitosamente a un archivo independiente listo para el informe de incidentes.

### 💡 Lecciones Clave Aprendidas
* **`head` y `tail`:** Permiten leer solo el inicio o el final de archivos de registro masivos sin colapsar la terminal con `cat`.
* **`grep "texto" archivo`:** Filtra patrones exactos dentro de miles de líneas en milisegundos.
* **Redirección (`>`):** Envía la salida estándar de cualquier comando directamente hacia un archivo nuevo para documentar hallazgos.
* **Rutas absolutas en comandos:** Se puede listar (`ls`) o leer (`cat`) un archivo ubicado en otro directorio indicando su ruta completa (`/home/analyst/archivo.txt`) sin necesidad de usar `cd`.
