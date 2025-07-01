# docker-projects 🐳

Infraestructura modular en Docker utilizada para exponer servicios locales, entornos de pruebas y herramientas de automatización, orquestada sobre Lubuntu en un host ESXi.

---

## 🧱 Estructura

core/ # Servicios base (nginx-proxy, Let's Encrypt, etc.)
dummies/ # Proxies de prueba o redirectores (esx1, esx2, etc.)
haproxy-tcp/ # Redirección TCP a múltiples puertos para VMs
html-shared/ # Archivos estáticos para validación ACME (Let's Encrypt)
services/ # Aplicaciones como n8n, Portainer, etc.

yaml
Copiar
Editar

---

## 🚀 ¿Cómo levantar?

Cada módulo tiene su propio `docker-compose.yml`.  
Ejemplo para core:

```bash
cd core/
docker-compose up -d
🔐 Seguridad
Este repositorio excluye automáticamente archivos .pem, .key, .crt, .env, etc., gracias al .gitignore.
Asegúrate de tener tus certificados y archivos sensibles solo en local.

🛠️ Funcionalidades previstas
Certificados TLS con Let's Encrypt y nginx-proxy

Acceso externo vía FortiGate + FortiDDNS

Publicación de VMs detrás de proxy inverso

TCP passthrough con HAProxy

Automatizaciones futuras con n8n y GitHub Actions

📦 Requisitos
Docker + Docker Compose

ESXi host (con FortiGate o router compatible con NAT)

Acceso a FortiDDNS o dominio propio (opcional)

🧾 Notas
Este proyecto es parte de mi laboratorio y entorno personal.
Si tienes dudas o quieres ideas de despliegue similar, abre un issue o mándame un mensaje.

🧠 Made with seguridad, automatización y café ☕ by @itsmillanessa
