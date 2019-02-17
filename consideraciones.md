---
description: >-
  Algunas consideraciones sobre las distintas solicitudes y respuestas que
  pueden encontrarse en nuestra API.
---

# Consideraciones

## Generales

* Los textos enviados deben ser encodeados con UTF-8
* El formato de envío y respuesta debe ser JSON.
* Siempre se debe utilizar HTTPS.

## Consulta de información

Para recuperar entidades especificas se deben realizar solicitudes GET indicando el identificador único de la entidad.

```javascript
curl 'https://api.peakly.co/ventas/clientes/1'
```

{% hint style="info" %}
 Este ejemplo muestra cómo podemos recuperar un cliente especifico con el identificador 1.
{% endhint %}

* Todas las solicitudes son respuestas en formato de JSON.
* Por defecto la búsqueda de información que es realizada correctamente tendrá una respuesta HTTP 200, caso contrario sera una respuesta HTTP 404 \(No encontrado\).

## Búsqueda paginada de información

En la mayoría de los recursos la paginación server-side esta disponible para obtener la menor cantidad de registros y solo recuperar los necesarios. No solo permite recuperar solo los registros que necesitas sino que también al buscar paginadamente los recursos estarán mas completos que cuando son recuperados en su totalidad. Para realizar una  consulta paginada debes enviar los parámetros page para pedir la pagina exacta y el parámetro rows para indicar de qué tamaño es cada pagina.

