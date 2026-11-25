# 🛡️ Realización de una Auditoría de Seguridad (Botium Toys)

## 📌 Descripción del Proyecto
Este proyecto consiste en realizar una auditoría interna de seguridad para **Botium Toys**, una empresa minorista de juguetes que expandió sus operaciones al comercio electrónico a nivel internacional. El objetivo es evaluar el cumplimiento de sus controles actuales frente a los estándares del sector y reducir los riesgos sobre los activos críticos del negocio.

## 🎯 Alcance y Objetivos
* Evaluar el estado actual de los controles técnicos, físicos y administrativos.
* Identificar brechas de seguridad en la protección de datos de clientes y sistemas de pago.
* Alinear las recomendaciones con el **Marco de Ciberseguridad del NIST (NIST CSF)** y normativas aplicables (**PCI-DSS**, **GDPR**).

## 🔍 Hallazgos Principales y Evaluación de Controles

| Área / Control Evaluado | Estado Actual | Riesgo Identificado |
| :--- | :--- | :--- |
| **Control de Acceso (IAM)** | ❌ Deficiente | No se aplica el principio de mínimo privilegio; todos los empleados tienen acceso amplio a los sistemas. |
| **Seguridad de Redes (Firewall / IDS)** | ⚠️ Parcial | Existen firewalls básicos, pero carecen de un sistema de detección de intrusiones (IDS) activo. |
| **Cifrado de Datos** | ❌ Deficiente | Los datos de tarjetas de pago y registros de clientes no están cifrados adecuadamente en tránsito ni en reposo. |
| **Gestión de Contraseñas y MFA** | ❌ Deficiente | Falta de autenticación multifactor (MFA) y políticas de contraseñas robustas. |
| **Copias de Seguridad (Backups)** | ⚠️ Parcial | Se realizan respaldos locales, pero no existen copias externas (*off-site*) ni pruebas periódicas de restauración. |
| **Seguridad Física** | ✅ Adecuado | Existen cerraduras y vigilancia básica, aunque requiere mejorar el registro de visitantes. |

## 🛠️ Recomendaciones de Remediación
1. **Implementar el Principio de Mínimo Privilegio (PoLP):** Restringir los permisos de usuario únicamente a los recursos necesarios para su rol laboral.
2. **Habilitar Autenticación Multifactor (MFA):** Exigir MFA para todos los empleados, especialmente en accesos remotos y sistemas administrativos.
3. **Cifrar Datos Sensibles:** Implementar protocolos **TLS** para datos en tránsito y cifrado **AES-256** para bases de datos en reposo, cumpliendo con **PCI-DSS**.
4. **Desplegar un Sistema IDS/IPS:** Monitorear el tráfico de red en tiempo real para detectar actividades maliciosas.
5. **Establecer Copias de Seguridad 3-2-1:** Mantener respaldos cifrados fuera de las instalaciones y programar simulacros de recuperación ante desastres.

## 📚 Competencias Demostradas
* Evaluación de riesgos y auditoría interna de seguridad.
* Aplicación de marcos normativos (**NIST CSF**, **PCI-DSS**, **GDPR**).
* Redacción de informes técnicos y recomendaciones ejecutivas de mitigación.
