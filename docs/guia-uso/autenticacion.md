# Autenticación 🔐

Para acceder a los recursos de la API, es necesario autenticar cada solicitud. Actualmente se soporta el siguiente método:

---

## ✅ 1. Autenticación mediante API Key (recomendado)

Este método consiste en enviar tu clave privada en cada solicitud, usando el encabezado `X-API-KEY`.

### 🧾 Ejemplo de solicitud

```http
GET /v1/colecciones HTTP/1.1
Host: api.relojesdelujo.com
X-API-KEY: tu_clave_secreta_123
Accept: application/json
```