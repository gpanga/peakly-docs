# Comprobantes en Linea

{% api-method method="post" host="https://qa.api.peakly.co" path="/FacturasEnLinea/{cuit}/{claveFiscal}" %}
{% api-method-summary %}
Get Comprobantes
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite obtener todos los comprobantes efectuados dentro de la aplicación "Comprobantes en Linea" de AFIP, pudiendo filtrar por fechas el mismo.  
  
Para iniciar una búsqueda de comprobantes sera necesario primero autenticarse en Peakly y luego realizar una solicitud con CUIT y Clave Fiscal, estos datos serán utilizados para hacer el inicio de sesión en AFIP. **La contraseña no sera guardada en ningún momento.**  
  
En caso de querer acceder a información de algun contribuyente que le haya delegado el permiso deberá especificar el campo **CUIT \(cuitDatos\)** o en caso contrario obtener la razón social desde la búsqueda de relaciones, enviando el dato recuperado tal cual como fue recibido ingresándolo en el campo **razonSocial.**  
  
El campo **Cache** agiliza los tiempos de búsqueda sin recuperar los comprobantes ya recuperados en alguna búsqueda anterior, sin importar los filtros de fecha. Si busque enero en una búsqueda inicial, y en la nueva busco todo el año, solo ira a buscar los meses faltantes.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="claveFiscal" type="string" required=true %}
Clave fiscal del contribuyente a buscar
{% endapi-method-parameter %}

{% api-method-parameter name="cuit" type="string" required=true %}
CUIT del contribuyente a iniciar sesión y a buscar datos si no se especifica
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Token de autorización obtenido previamente en el formato: **Bearer** ACCESS\_TOKEN
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="razonSocial" type="string" required=false %}
Razón Social a buscar datos, debe ser idéntica a la devuelta por la búsqueda de relaciones.
{% endapi-method-parameter %}

{% api-method-parameter name="cuitDatos" type="string" required=false %}
CUIT a buscar datos, en caso de no enviar usara el de login
{% endapi-method-parameter %}

{% api-method-parameter name="cache" type="boolean" required=false %}
Si los resultados ya fueron buscados anteriormente responde con ellos.
{% endapi-method-parameter %}

{% api-method-parameter name="start" type="string" %}
Fecha de comienzo de búsqueda en formato \(aaaa-mm-dd\). 
{% endapi-method-parameter %}

{% api-method-parameter name="end" type="string" %}
Fecha de finalización de búsqueda en formato \(aaaa-mm-dd\). cake should be gluten-free or not.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Listado de comprobantes
{% endapi-method-response-example-description %}

```javascript
[
  {
    "tipoDocumento": "CUIT",
    "documento": "string",
    "razonSocial": "string",
    "numero": "string",
    "puntoVenta": 0,
    "fecha": "2018-11-12T14:37:38.205Z",
    "items": [
      {
        "cantidad": 0,
        "bonificacion": 0,
        "ajuste": 0,
        "precioUnitario": 0,
        "total": 0,
        "descripcion": "string",
        "anulado": true,
        "tipoOperacion": "string"
      }
    ],
    "tipoComprobante": "Factura",
    "letra": "string",
    "cotizacion": 0,
    "moneda": "string",
    "iva": 0,
    "netoGravado": 0,
    "otrosConceptos": 0,
    "total": 0,
    "percepciones": 0,
    "percepcionesIIBB": 0,
    "percepcionesMunicipales": 0,
    "percepcionesInternos": 0,
    "transporte": 0,
    "tipoResponsable": "string",
    "cantidadAlicuotas": 0,
    "codigoOperacion": "string",
    "cae": "string",
    "vencimientoCAE": "2018-11-12T14:37:38.206Z"
  }
]
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Acceso no autorizado a AFIP
{% endapi-method-response-example-description %}

```javascript
{
    "message": "CUIT / Clave fiscal incorrecta"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
No se encontró Comprobantes En Linea delegado
{% endapi-method-response-example-description %}

```javascript
{
    "message": "Serivicio no habilitado"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



