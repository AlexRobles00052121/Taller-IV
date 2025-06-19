# Preguntas Frecuentes ❓

## Autenticación y Acceso

??? question "¿Cómo obtengo mi API Key?"
    1. Inicia sesión en tu [panel de desarrollador](https://api.relojesdelujo.com/dev)
    2. Ve a "Claves API"
    3. Haz clic en "Generar nueva clave"
    4. ¡Cópiala inmediatamente! (solo se muestra una vez)

!!! warning
    Si pierdes tu clave, deberás generar una nueva y actualizar todas tus integraciones.

## Uso de la API

??? question "¿Cómo filtro por modelos disponibles?"
    Usa el parámetro `disponible=true`:
    ```http
    GET /v1/modelos?disponible=true&marca=Rolex
    ```

??? question "¿Los precios incluyen IVA?"
    | Región          | Incluye Impuestos |
    |----------------|------------------|
    | UE            | Sí (21%)         |
    | USA           | No               |
    | Suiza         | Sí (7.7%)        |

## Problemas Comunes

??? bug "Error 429: Too Many Requests"
    **Solución:**
    - Espera 1-2 minutos
    - Implementa retry con backoff exponencial:
    ```python
    import time
    from tenacity import retry, stop_after_attempt, wait_exponential

    @retry(stop=stop_after_attempt(3), wait=wait_exponential(multiplier=1))
    def get_modelos():
        return api.get_modelos()
    ```

??? bug "Modelos que no aparecen en búsquedas"
    **Causas posibles:**
    1. El modelo está marcado como "edición limitada"
    2. Filtros demasiado restrictivos
    3. Necesitas permisos "premium"

## Facturación y Planes

??? question "¿Puedo cambiar de plan?"
    ```mermaid
    graph LR
        Free --> Professional
        Professional --> Enterprise
        Enterprise --> Custom
    ```
    Siempre puedes **upgrade** inmediatamente, los **downgrades** aplican en el próximo ciclo.

??? question "¿Ofrecen descuentos para volúmenes altos?"
    Contacta a [ventas@relojesdelujo.com](mailto:ventas@relojesdelujo.com) con:
    - Volumen estimado de requests/mes
    - Caso de uso específico
    - Requerimientos técnicos

## Soporte Técnico

??? question "¿Dónde reporto bugs?"
    Abre un issue en nuestro [GitHub](https://github.com/relojes-api/issues) con:
    1. Endpoint usado
    2. Código de error
    3. Timestamp (UTC)
    4. Tu request ID (encabezado `X-Request-ID`)

!!! success "Horario de Soporte"
    ```text
    Lunes-Viernes: 08:00-22:00 CET
    Sábados: 10:00-18:00 CET
    Urgencias: +41 22 418 76 28 (24/7)
    ```

## Datos y Actualizaciones

??? question "¿Cada cuánto actualizan los datos?"
    | Dataset          | Frecuencia     |
    |----------------|---------------|
    | Precios retail | Cada 24h      |
    | Subastas       | Tiempo real   |
    | Boutiques      | Cada 15min    |

??? question "¿Los datos históricos son completos?"
    Tenemos datos desde 2015 para:
    - 100% de modelos Patek Philippe
    - 92% de Rolex
    - 85% de marcas independientes

[Contactar al equipo →](mailto:soporte@relojesdelujo.com) Aqui