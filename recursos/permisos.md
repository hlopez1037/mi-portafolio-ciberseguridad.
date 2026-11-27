---

## Caso #04: Gestión de Usuarios y Propiedad de Archivos (`sudo`, `useradd`, `chown`)

### 📋 Escenario
Se realizó el alta (*onboarding*) de una nueva analista (`sofia`) y la baja inmediata (*offboarding*) de un contratista temporal (`carlos_temp`). Posteriormente, se transfirió la propiedad del manual de bienvenida a la nueva analista aplicando restricciones estrictas de acceso.

### 🛠️ Comandos Ejecutados y Resultados

1. **Creación y eliminación de cuentas de usuario (`sudo useradd` y `sudo userdel`):**
   ```bash
   sudo useradd sofia
   sudo userdel carlos_temp
   tail -n 3 /etc/passwd
   ```
   *Resultado:* Se creó la cuenta `sofia` (UID 1002), se revocó el acceso de `carlos_temp` y se verificó el registro actualizado en `/etc/passwd`.

2. **Transferencia de propiedad y ajuste de permisos (`chown` y `chmod`):**
   ```bash
   sudo chown sofia guia_onboarding.txt
   sudo chmod go-rwx guia_onboarding.txt
   ls -la
   ```
   *Resultado:* El archivo `guia_onboarding.txt` pasó a ser propiedad de `sofia` con permisos `-rw-------` (`600`), bloqueando lectura, escritura y ejecución para el grupo y otros usuarios.

### 💡 Lecciones Clave Aprendidas
* **Sensibilidad a mayúsculas (*Case-Sensitive*):** Linux diferencia estrictamente entre `sofia` y `Sofia`; los nombres de usuario deben escribirse exactamente como fueron registrados (por convención, en minúsculas).
* **Privilegios administrativos (`sudo`):** Comandos que alteran usuarios del sistema o archivos de otros propietarios requieren anteponer `sudo`.
* **`chown` vs. `chmod`:** `chown` cambia el **propietario** de un archivo o directorio, mientras que `chmod` modifica los **permisos** (`u` = dueño, `g` = grupo, `o` = otros).
