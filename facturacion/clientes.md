---
description: >-
  Un Cliente es un consumidor del producto o servicio que ofrece tu organización
  y por lo tanto estará asociado a tu facturación.
---

# Clientes

## Probar desde el [explorador ](https://api.peakly.co/swagger/ui/index#!/Clientes/Clientes_Get)de API

{% api-method method="get" host="https://api.peakly.co" path="/api/Ventas/Clientes/Page" %}
{% api-method-summary %}
Buscar clientes
{% endapi-method-summary %}

{% api-method-description %}
Busca todos los Clientes que estén activos \(no hayan sido eliminados\), que coincidan con el criterio de búsqueda en el campo **where**.  
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
Clientes recuperados
{% endapi-method-response-example-description %}

```javascript
{
  "totalPages": 1,
  "page": 1,
  "totalRecords": 1,
  "userdata": null,
  "records":[
    {
      "id": 16207,
      "activo": true,
      "razonSocial": "Consumidor Final sin identificar",
      "domicilio": null,
      "codigoPostal": null,
      "localidad": null,
      "localizacion_id": null,
      "localizacion_value": null,
      "telefono": null,
      "email": null,
      "categoriaIva_id": 8,
      "categoriaIva_value": "Consumidor Final",
      "cuit": null,
      "condicionVenta_id": 10,
      "condicionVenta_value": "Contado",
      "master_id": null,
      "master_nombre": null,
      "tipoDocumento_id": 182,
      "observaciones": null
    }
  ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.peakly.co" path="/api/Ventas/Clientes/:id" %}
{% api-method-summary %}
Buscar cliente por id
{% endapi-method-summary %}

{% api-method-description %}
Busca el cliente por el identificador enviado como parametro. 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="number" required=true %}
Identificador del cliente
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cliente encontrado
{% endapi-method-response-example-description %}

```
{
  "id": 140,
  "activo": true,
  "razonSocial": "Mi nuevo cliente",
  "domicilio": "Av. Santa Fe 1234",
  "codigoPostal": "1400",
  "localidad": "Palermo",
  "localizacion_id": 2,
  "localizacion_value": "Buenos Aires",
  "telefono": "string",
  "email": null,
  "categoriaIva_id": 1,
  "categoriaIva_value": "Responsable Inscripto",
  "cuit": "20-35961444-7",
  "condicionVenta_id": 13,
  "condicionVenta_value": "30 Dias",
  "master_id": null,
  "master_nombre": null,
  "tipoDocumento_id": 180,
  "observaciones": "Observaciones sobre cliente"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Cliente no encontrado
{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://api.peakly.co" path="/api/Ventas/Clientes" %}
{% api-method-summary %}
Crear Cliente
{% endapi-method-summary %}

{% api-method-description %}
Crea el Cliente enviado en el body  
Para los valores de **Localizacion\_id** y **Localizacion\_value** utilizar el endpoint de información de Localizaciones.   
Para los valores de **CategoriaIVA\_id** y **CategoriaIVA\_value** utilizar el endpoint de información de Categorías.   
Para los valores de **CondicionVenta\_id** y **CondicionVenta\_value** utilizar el endpoint de información de ComboItems, el combo **CondicionCompraVenta**.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="tipoDocumento\_id" type="number" required=false %}
Tipo de documento
{% endapi-method-parameter %}

{% api-method-parameter name="cuit" type="string" required=false %}
CUIT / DNI, documento legal
{% endapi-method-parameter %}

{% api-method-parameter name="razonSocial" type="string" required=false %}
Razón Social / Nombre legal
{% endapi-method-parameter %}

{% api-method-parameter name="domicilio" type="string" required=false %}
Domicilio, dirección principal
{% endapi-method-parameter %}

{% api-method-parameter name="localidad" type="string" required=false %}
Localidad, dirección principal
{% endapi-method-parameter %}

{% api-method-parameter name="codigoPostal" type="string" required=false %}
Código postal, dirección principal
{% endapi-method-parameter %}

{% api-method-parameter name="telefono" type="string" required=false %}
Telefono principal
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=false %}
Email del cliente. Pueden ser multiples separados por ;
{% endapi-method-parameter %}

{% api-method-parameter name="condicionVenta\_id" type="number" required=false %}
Condición de Venta, id
{% endapi-method-parameter %}

{% api-method-parameter name="condicionVenta\_value" type="string" required=false %}
Condición de Venta, valor
{% endapi-method-parameter %}

{% api-method-parameter name="localizacion\_id" type="number" required=false %}
Localización, id
{% endapi-method-parameter %}

{% api-method-parameter name="localizacion\_value" type="string" required=false %}
Localización, valor
{% endapi-method-parameter %}

{% api-method-parameter name="categoriaIVA\_id" type="number" required=false %}
Categoria de IVA, id
{% endapi-method-parameter %}

{% api-method-parameter name="categoriaIVA\_value" type="string" required=false %}
Categoria de IVA, valor
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cliente creado correctamente
{% endapi-method-response-example-description %}

```text
{
  "id": 140,
  "activo": true,
  "razonSocial": "Mi nuevo cliente",
  "domicilio": "Av. Santa Fe 1234",
  "codigoPostal": "1400",
  "localidad": "Palermo",
  "localizacion_id": 2,
  "localizacion_value": "Buenos Aires",
  "telefono": "string",
  "email": null,
  "categoriaIva_id": 1,
  "categoriaIva_value": "Responsable Inscripto",
  "cuit": "20-35961444-7",
  "condicionVenta_id": 13,
  "condicionVenta_value": "30 Dias",
  "master_id": null,
  "master_nombre": null,
  "tipoDocumento_id": 180,
  "observaciones": "Observaciones sobre cliente"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Algún campo es invalido
{% endapi-method-response-example-description %}

```text
{
  "message": "The request is invalid.",
  "modelState": {
    "cliente.CUIT": [
      "El cuit es invalido"
    ]
  }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
No se encontró algún dato relacionado.
{% endapi-method-response-example-description %}

```text
Condición de venta inexistente para el cliente
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://api.peakly.co" path="/api/Ventas/Clientes/CUIT/:cuit" %}
{% api-method-summary %}
Crear cliente 
{% endapi-method-summary %}

{% api-method-description %}
Crea si no existe en base al CUIT enviado, solo soporta el envío de CUIT cualquier otro documento no se reconocerá.  
Se cargaran los datos traídos desde AFIP para la creación del cliente y luego podrá ser personalizado realizando actualizaciones.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="cuit" type="string" required=true %}
CUIT del contribuyente
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cliente creado correctamente
{% endapi-method-response-example-description %}

```
{
  "id": 140,
  "activo": true,
  "razonSocial": "Mi nuevo cliente",
  "domicilio": "Av. Santa Fe 1234",
  "codigoPostal": "1400",
  "localidad": "Palermo",
  "localizacion_id": 2,
  "localizacion_value": "Buenos Aires",
  "telefono": "string",
  "email": null,
  "categoriaIva_id": 1,
  "categoriaIva_value": "Responsable Inscripto",
  "cuit": "20-35961444-7",
  "condicionVenta_id": 13,
  "condicionVenta_value": "30 Dias",
  "master_id": null,
  "master_nombre": null,
  "tipoDocumento_id": 180,
  "observaciones": "Observaciones sobre cliente"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
CUIT no encontrado en AFIP
{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="https://api.peakly.co" path="/api/Ventas/Clientes" %}
{% api-method-summary %}
Actualizar cliente
{% endapi-method-summary %}

{% api-method-description %}
Actualiza el **Cliente** enviado en el body  
Para los valores de **Localizacion\_id** y **Localizacion\_value** utilizar el endpoint de información de Localizaciones.   
Para los valores de **CategoriaIVA\_id** y **CategoriaIVA\_value** utilizar el endpoint de información de Categorías.   
Para los valores de **CondicionVenta\_id** y **CondicionVenta\_value** utilizar el endpoint de información de ComboItems, el combo **CondicionCompraVenta**.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="delete" host="https://api.peakly.co" path="/api/Ventas/Clientes/{id}" %}
{% api-method-summary %}
Eliminar cliente
{% endapi-method-summary %}

{% api-method-description %}
Elimina el cliente indicado por id en la solicitud. El borrado es lógico por lo cual se puede recuperar en caso de haber sido borrado.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="number" required=true %}
Cliente Id
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cliente eliminado correctamente
{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

