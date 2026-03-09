# Despliegue de Redes Privadas Virtuales (VPN) Multiprotocolo

## 📝 Descripción General
Práctica avanzada de seguridad perimetral consistente en el diseño e implementación de múltiples túneles VPN en un entorno simulado con GNS3. El objetivo es establecer comunicaciones seguras entre distintas sedes a través de una WAN emulada, aplicando técnicas de encapsulación, cifrado y evasión de firewalls mediante diversos protocolos estándar e infraestructuras de código abierto.

## 🎯 Objetivos
* Establecer túneles de comunicación cifrada empleando topologías Site-to-Site.
* Demostrar la evasión de inspección de paquetes encapsulando tráfico dentro de peticiones web convencionales (HTTP/HTTPS).
* Desplegar túneles SSH de capa de red para la interconexión transparente de subredes.
* Implementar soluciones empresariales de VPN (IPsec y SSL) haciendo uso de appliances de firewall (OPNSense).
* Capturar e inspeccionar el tráfico en tránsito con Wireshark para validar la confidencialidad de los datos.

## 🛠️ Tecnologías y Herramientas
* **Simulación de Red**: GNS3 con switches y nodos VPCS.
* **Sistemas Operativos**: Servidores Linux (Ubuntu) y OPNSense (basado en FreeBSD).
* **Protocolos y Servicios**: OpenSSH, HTTP Tunneling (`httptunnel`), SSL/TLS Wrapper (`stunnel4`).
* **VPN Empresarial**: IPsec, OpenVPN (vía OPNSense).
* **Análisis Forense de Red**: Wireshark.

## ⚙️ Detalles de Implementación Destacados
* **Evasión con HTTP/SSL**: Se configuró un entorno donde el tráfico interno se encapsula primero en HTTP y posteriormente se cifra con SSL, permitiendo enmascarar la conexión VPN como si fuese tráfico de navegación web segura tradicional.
* **Túneles SSH Enrutados**: Se habilitaron interfaces virtuales (`tun`) a través de conexiones SSH persistentes, configurando el reenvío de paquetes y las tablas de rutas estáticas para lograr visibilidad bidireccional entre las redes locales de ambos extremos.
* **Despliegue de OPNSense**: Se utilizaron firewalls OPNSense para configurar túneles robustos (IPsec y SSL VPN), aplicando políticas de cifrado avanzadas y control de acceso estricto entre sedes.
* **Validación de Cifrado**: La comprobación de seguridad se realizó interceptando las tramas en la WAN emulada, confirmando que las cargas útiles (payloads) de los paquetes generados por los clientes eran completamente ilegibles debido a la encriptación.

## 📄 Documentación Completa
Para revisar en detalle las topologías de red, las reglas de enrutamiento exactas aplicadas en los servidores y las evidencias de las capturas de paquetes, puedes acceder a la memoria técnica completa:

👉 [Enlace al Informe Técnico en Google Drive](https://docs.google.com/document/d/1XOVfnoYTwMW5xKVwG5mljI1ckEym9X4jXeXM0mls-es/edit?usp=sharing)

## ⚠️ Aviso Legal / Ética
*El uso de técnicas de ofuscación de tráfico y túneles encriptados debe realizarse siempre bajo autorización explícita en entornos reales. Este proyecto se desarrolló en un laboratorio aislado con fines puramente académicos.*
