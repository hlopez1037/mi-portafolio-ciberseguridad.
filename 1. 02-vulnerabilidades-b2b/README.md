# 🔍 Identificación de Vulnerabilidades para un Pequeño Negocio

## 📌 Descripción del Proyecto
Este proyecto consiste en realizar una evaluación de vulnerabilidades para una pequeña empresa comercial (**B2B / comercio electrónico**) con el objetivo de identificar debilidades en sus sistemas, priorizar los riesgos según su impacto operativo y proponer un plan de remediación accionable.

## 🎯 Objetivos de la Evaluación
* Identificar activos críticos expuestos y posibles vectores de ataque.
* Analizar vulnerabilidades técnicas, administrativas y humanas en la infraestructura actual.
* Clasificar los hallazgos según su nivel de severidad y probabilidad de explotación.
* Proporcionar soluciones prácticas alineadas con el **Marco de Ciberseguridad del NIST (NIST CSF)**.

## 🛡️ Matriz de Vulnerabilidades Identificadas

| Activo / Área | Vulnerabilidad Detectada | Severidad | Impacto Potencial (Tríada CIA) |
| :--- | :--- | :--- | :--- |
| **Servidor Web / Base de Datos** | Sistema operativo y aplicaciones sin parches de seguridad actualizados (*Legacy Software*). | 🔴 Alta | Compromiso total del servidor, robo de datos (**Confidencialidad**) y alteración de registros (**Integridad**). |
| **Cuentas de Empleados** | Uso de contraseñas débiles y ausencia de Autenticación Multifactor (MFA). | 🔴 Alta | Acceso no autorizado mediante ataques de fuerza bruta o relleno de credenciales (*Credential Stuffing*). |
| **Red Interna / Wi-Fi** | Falta de segmentación entre la red de invitados y la red operativa interna. | 🟠 Media | Movimiento lateral de atacantes hacia equipos administrativos y servidores internos. |
| **Dispositivos de Punto Final** | Ausencia de cifrado de disco completo en laptops utilizadas de forma remota. | 🟠 Media | Exposición de información confidencial en caso de robo o pérdida física del equipo. |
| **Personal de la Empresa** | Falta de capacitación periódica contra ingeniería social y *phishing*. | 🟡 Media | Infección por malware o entrega involuntaria de credenciales a actores maliciosos. |

## 🛠️ Plan de Remediación Recomendado
1. **Gestión de Parches y Actualizaciones:** Establecer un calendario mensual de actualización automática para sistemas operativos, navegadores y software de servidor.
2. **Endurecimiento de Autenticación (IAM):** Implementar políticas de contraseñas robustas y activar **MFA obligatorio** en todas las cuentas corporativas.
3. **Segmentación de Red:** Configurar redes VLAN separadas para aislar el tráfico de invitados de los servidores y estaciones de trabajo críticas.
4. **Cifrado en Reposo:** Habilitar el cifrado de disco completo (ej. *BitLocker* o *FileVault*) en todos los dispositivos portátiles de la empresa.
5. **Concientización en Seguridad:** Realizar capacitaciones trimestrales y simulaciones de *phishing* para fortalecer la defensa humana.

## 📚 Competencias Demostradas
* Evaluación y priorización de vulnerabilidades en entornos empresariales.
* Análisis de impacto bajo la **Tríada CIA** (Confidencialidad, Integridad y Disponibilidad).
* Diseño de planes de mitigación alineados con estándares de la industria.
