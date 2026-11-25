# 🌐 Análisis de la Estructura y Seguridad de las Redes

## 📌 Descripción del Proyecto
Este proyecto analiza una arquitectura de red corporativa típica para identificar puntos de exposición frente a amenazas externas e internas, evaluar la segmentación del tráfico y diseñar controles defensivos en capas (*Defensa en Profundidad*).

## 🎯 Objetivos del Análisis
* Examinar la topología de red, dispositivos clave (routers, switches, firewalls) y flujos de tráfico.
* Identificar vulnerabilidades asociadas a protocolos inseguros y falta de aislamiento de sistemas críticos.
* Implementar controles perimetrales e internos para proteger la confidencialidad, integridad y disponibilidad de las comunicaciones.

## 🔍 Evaluación de Arquitectura y Vectores de Riesgo

| Componente / Protocolo | Riesgo Identificado | Vector de Ataque Potencial |
| :--- | :--- | :--- |
| **Servidores Públicos (Web/Correo)** | Ubicación directa dentro de la red interna (LAN) sin aislamiento. | Un atacante que comprometa el servidor web puede pivotar (*movimiento lateral*) hacia las bases de datos internas. |
| **Tráfico Web y Remoto** | Uso de protocolos en texto plano (`HTTP` puerto 80, `Telnet` puerto 23). | Interceptación de credenciales y datos sensibles mediante ataques *Man-in-the-Middle* (MitM) o *sniffing*. |
| **Control Perimetral** | Firewall sin estado (*stateless*) con reglas demasiado permisivas. | Escaneo de puertos, inundaciones *SYN Flood* y acceso no autorizado a servicios internos. |
| **Acceso Remoto de Empleados** | Conexiones directas a recursos corporativos a través de redes públicas sin cifrar. | Secuestro de sesión y exposición de tráfico corporativo en redes Wi-Fi públicas. |
| **Monitoreo de Red** | Ausencia de sensores de detección de intrusiones en puntos críticos de la red. | Intrusiones silenciosas que pasan desapercibidas durante largos períodos. |

## 🛡️ Controles y Arquitectura Recomendada (Defensa en Profundidad)
1. **Implementación de una Zona Desmilitarizada (DMZ):** Aislar los servidores accesibles desde Internet (web, DNS público) en una subred intermedia protegida por firewalls, evitando el contacto directo con la red interna.
2. **Migración a Protocolos Cifrados:** Reemplazar `HTTP` por `HTTPS` (puerto 443 con TLS) y `Telnet` por `SSH` (puerto 22) para garantizar la confidencialidad e integridad en tránsito.
3. **Configuración de Firewall con Estado (*Stateful*):** Aplicar reglas de filtrado estricto basadas en el estado de la conexión y el principio de denegación por defecto (*Implicit Deny*).
4. **Despliegue de VPN Corporativa:** Exigir el uso de túneles VPN cifrados (IPsec / WireGuard) junto con MFA para todo el personal remoto.
5. **Monitoreo Continuo con IDS/IPS:** Instalar sistemas de detección y prevención de intrusiones para inspeccionar paquetes anómalos y enviar alertas al SIEM.

## 📚 Competencias Demostradas
* Comprensión del modelo **TCP/IP**, direccionamiento IP y puertos estándar de red.
* Diseño de arquitecturas segmentadas (**DMZ**, subredes y firewalls).
* Mitigación de ataques de red (*MitM*, *DoS/SYN Flood*, movimiento lateral).
