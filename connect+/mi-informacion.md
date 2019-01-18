# Mi Información

{% api-method method="get" host="https://qa.api.peakly.co" path="/MiInformacion/Financiera/{cuit}/{claveFiscal}" %}
{% api-method-summary %}
Get Mi Información - Financiera
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite obtener toda la información financiera disponible del contribuyente que esta en la página de AFIP.  
Recupera la información de Compra/Venta automotores, consumos de tarjeta de crédito, depósitos en pesos y dólares, compras de divisas extranjeras e información de comprobantes emitidos y recibidos a tu nombre.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="cuit" type="string" required=true %}
CUIT del usuario contribuyente
{% endapi-method-parameter %}

{% api-method-parameter name="claveFiscal" type="string" required=true %}
Clave fiscal del usuario contribuyente
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Token de autorización obtenido previamente en el formato: **Bearer** ACCESS\_TOKEN
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="periodo" type="string" required=true %}
Periodo/Año a averiguar \(formato aaaa\), desde el 2017
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Información recuperada correctamente
{% endapi-method-response-example-description %}

```javascript
{
  "automotor": [
    {
      "fecha": "string",
      "fechaVenta": "string",
      "porcentaje": 0,
      "valorFactura": 0,
      "valuacion": 0,
      "descripcion": "string",
      "marca": "string",
      "modelo": "string",
      "modeloFecha": "string",
      "operacion": "string",
      "patente": "string"
    }
  ],
  "depositos": [
    {
      "tipoCuenta": "string",
      "cbu": "string",
      "importe": 0,
      "caracter": "string",
      "percepciones": 0
    }
  ],
  "compraDolares": 0,
  "ventaDolares": 0,
  "emitidos": [
    {
      "cantidad": 0,
      "tipoComprobante": "string",
      "importeNeto": 0,
      "importeGravado": 0,
      "iva": 0,
      "total": 0
    }
  ],
  "recibidos": [
    {
      "cantidad": 0,
      "tipoComprobante": "string",
      "importeNeto": 0,
      "importeGravado": 0,
      "iva": 0,
      "total": 0
    }
  ],
  "consumoTitular": 0,
  "consumoAdicional": 0,
  "consumoTotal": 0
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Inicio de sesión no permitido
{% endapi-method-response-example-description %}

```javascript
{
    "message": "Usuario/Clave fiscal invalida"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



