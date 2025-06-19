# Ejemplos Prácticos 🛠️

## Consulta Básica de Modelos

### Obtener todos los modelos Rolex

=== "JavaScript"
    ```javascript
    const RelojesAPI = require('relojes-lujo-api');
    
    const client = new RelojesAPI(process.env.API_KEY);
    
    client.getModelos({ marca: 'Rolex' })
      .then(modelos => {
        modelos.forEach(m => console.log(`${m.nombre} - $${m.precio.toLocaleString()}`));
      })
      .catch(console.error);
    ```

=== "cURL"
    ```bash
    curl -X GET "https://api.relojesdelujo.com/v1/modelos?marca=Rolex&limit=10" \
      -H "X-API-KEY: tu_api_key_123"
    ```

## Búsqueda Avanzada

### Relojes de oro con tourbillon
```python
resultados = api.busqueda_avanzada(
    materiales=["oro"],
    complicaciones=["tourbillon"],
    precio_max=500000
)

print(f"Encontrados {len(resultados)} modelos exclusivos")
```