---
description: >-
  Los artículos son productos o servicios que se registran dentro de Peakly y se
  asocian tanto a la facturación como al movimiento de stock.
---

# Articulos

#### Probar desde el [explorador ](https://api.peakly.co/swagger/ui/index#!/Articulos/Articulos_Get)de API 

{% api-method method="get" host="https://api.peakly.co" path="/api/Stock/Articulos/Page" %}
{% api-method-summary %}
Buscar artículos
{% endapi-method-summary %}

{% api-method-description %}
Busca todos los Artículos que estén activos \(no hayan sido eliminados\), que coincidan con el criterio de búsqueda en el campo **where**.  
El campo **rows** indica la cantidad de registros por pagina y el campo **page** la pagina recuperar.  
La respuesta devuelve la cantidad de registros totales y la cantidad de paginas.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="where" type="string" required=false %}
Texto a buscar
{% endapi-method-parameter %}

{% api-method-parameter name="page" type="number" required=true %}
Número de página
{% endapi-method-parameter %}

{% api-method-parameter name="rows" type="number" required=true %}
Tamaño de página
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Artículos recuperados
{% endapi-method-response-example-description %}

```javascript
{
  "totalPages": 1,
  "page": 1,
  "totalRecords": 1,
  "userdata": null,
  "records":[
    {
      "id": 9047,
      "descripcion": "Mi Articulo",
      "unidadMedida_id": 155,
      "unidadMedida_value": "Packs",
      "alicuotaIVA_id": 90,
      "alicuotaIVA_value": "No Gravado",
      "tipo": 0,
      "rubro_id": 7009,
      "rubro_value": "Sin Rubro",
      "precio": 0
    }
  ]
}Pro
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://api.peakly.co" path="/api/Stock/Articulos" %}
{% api-method-summary %}
Crear Articulo
{% endapi-method-summary %}

{% api-method-description %}
Crea el Articulo enviado en el body  
  
El campo **UnidadMedida\_id** o **UnidadMedida\_value** debe llevar valor. El mismo debe ser obtenido desde el listado de _Tipos_ del combo **UnidadesMedidas**.   
  
El campo **AlicuotaIVA\_id** o **AlicuotaIVA\_value** debe llevar valor. El mismo debe ser obtenido desde el listado de _Tipos_ del combo **TipoIVA**.  
  
El campo tipo debe ser "Producto" o "Servicio", los mismos pueden ser obtenidos desde el listado de _Tipos_ del combo **TipoArticulo**.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="descripcion" type="string" required=true %}
Nombre del Producto/Servicio
{% endapi-method-parameter %}

{% api-method-parameter name="unidadMedida\_id" type="string" required=false %}
Unidad de medida, id
{% endapi-method-parameter %}

{% api-method-parameter name="unidadMedida\_value" type="string" required=false %}
Unidad de medida, valor
{% endapi-method-parameter %}

{% api-method-parameter name="alicuotaIVA\_id" type="number" required=false %}
Alícuota de IVA, id
{% endapi-method-parameter %}

{% api-method-parameter name="alicuotaIVA\_value" type="string" required=false %}
Alícuota de IVA, valor
{% endapi-method-parameter %}

{% api-method-parameter name="tipo" type="string" required=true %}
"Producto" o "Servicio"
{% endapi-method-parameter %}

{% api-method-parameter name="precio" type="number" required=false %}
Precio unitario
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Articulo creado correctamente
{% endapi-method-response-example-description %}

```
{
  "rubro_value": "Sin Rubro",
  "id": 9058,
  "descripcion": "asd",
  "unidadMedida_id": 140,
  "unidadMedida_value": "Unidades",
  "alicuotaIVA_id": 94,
  "alicuotaIVA_value": "21%",
  "tipo": 0,
  "rubro_id": 7009,
  "precio": 0
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Algún campo es invalido
{% endapi-method-response-example-description %}

```
{
  "message": "The request is invalid.",
  "modelState": {
    "articulo.Descripcion": [
      "La Descripción es requerida"
    ]
  }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
No se encontró alícuota o unidad de medida.
{% endapi-method-response-example-description %}

```
Alícuota IVA inexistente para el articulo
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



