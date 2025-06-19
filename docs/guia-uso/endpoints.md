# Endpoints API Relojes de Lujo 🚀

## Modelos

### `GET /v1/modelos`
Lista todos los modelos disponibles con paginación.

## 🧩 Parámetros de consulta

Puedes personalizar tu solicitud GET agregando los siguientes parámetros:

| Parámetro     | Tipo     | Requerido | Descripción                                 |
|---------------|----------|-----------|---------------------------------------------|
| `marca`       | `string` | No        | Filtra resultados por marca (ej. `"Patek"`) |
| `precio_min`  | `number` | No        | Define el precio mínimo en USD              |
| `limit`       | `number` | No        | Límite de resultados (por defecto: `50`)    |

!!! tip
    Puedes combinar varios parámetros en la misma consulta para afinar los resultados.


**Ejemplo de respuesta:**
```json
{
  "data": [
    {
      "id": "5711-1A-010",
      "nombre": "Nautilus 5711/1A-010",
      "marca": "Patek Philippe",
      "precio_retail": 120000
    }
  ],
  "pagination": {
    "total": 125,
    "next_page": "https://api.relojesdelujo.com/v1/modelos?page=2"
  }
}
```