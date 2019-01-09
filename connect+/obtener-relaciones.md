---
description: >-
  Este endpoint permite recuperar las relaciones autorizadas para el usuario
  enviado (CUIT / Clave Fiscal) que fueron delegadas y confirmadas anterior a la
  llamada.
---

# Obtener Relaciones

{% api-method method="get" host="https://qa.api.peakly.co" path="/Relaciones/{cuit}/{claveFiscal}" %}
{% api-method-summary %}
Obtener relaciones
{% endapi-method-summary %}

{% api-method-description %}
Obtiene todas las relaciones autorizadas sobre terceros para el usuario enviado
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="claveFiscal" type="string" required=true %}
Clave fiscal del usuario
{% endapi-method-parameter %}

{% api-method-parameter name="cuit" type="string" required=true %}
CUIT del usuario
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Token de autorización obtenido previamente en el formato: **Bearer** ACCESS\_TOKEN
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Relaciones listadas correctamente
{% endapi-method-response-example-description %}

```javascript
[
  {
    "value": "2012345671",
    "name": "Demo SRL"
  }
]
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Usuario/Clave fiscal invalida
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



