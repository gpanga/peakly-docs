# Autenticación

Una vez que este confirmado se le devolverá la información de autenticación, esta incluye el token y su vencimiento. Todos los siguientes request que necesiten autenticación, ósea que no son públicos, deben llevar el header de Authorization.

{% api-method method="post" host="https://api.peakly.co" path="/token" %}
{% api-method-summary %}
Get Token
{% endapi-method-summary %}

{% api-method-description %}
Esta solicitud permite generar un token de acceso "accessToken" que permitirá acceder al resto de los recursos utilizando el header "Autorization".
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="username" type="string" required=true %}
Usuario de acceso
{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=true %}
Contraseña de acceso
{% endapi-method-parameter %}

{% api-method-parameter name="grant\_type" type="string" required=true %}
Enviar password
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Login autorizado correctamente
{% endapi-method-response-example-description %}

```javascript
{
    .expires: "Mon, 19 Nov 2018 18:16:31 GMT"
    .issued: "Mon, 05 Nov 2018 18:16:31 GMT"
    access_token: "4dpCfWf9rRJut_TUYiwgF6F22f4s5jhDN7ZvEE2_KyhIgzU_Gv4gRu0rA6xQmWggubAnaFhs_YabceeryuCTG8eW81cTX2AwQS3CUp534wVmm2GOsZG9ezOr123jRXmk6IJWpPydB4QxOw9RBzIuEOFEd-LQe5_O0dOAN5-V1pQ7S0wK7UHii0VxvwSZx_iqlJBzdhKZFT86ulLsCsiV-M4nKRcxF-1awbSW5jvCYGTsv_8-DxRw0AfMm3z4CEs5jBQDHsdWxLNOnRteKHEIyAOMQ82Xm212b5HRU6gOADECQJovsLr2-WM444HuZyOTXB4M0L1KJwt0NXdXM_fMDIE5s0YISwfTffpauJJZS754IIpUDI0F3n3aZpTPLj5rgcREDIVvPKw1OijjWlQdReZN108iGxgFalR3btgDbMdddc2I_c1jJGLowZSZStqMhG6-oZpglMw3npIlKKXW1wMBmsToFRQWUdKgQtsPL8c7NDUpt31otkKfasqpPyitiiWh26WEasKBjeva6uxvvv3UlE9V9_sn5HrGFhasE1MGw"
    expires_in: 1209599
    organizacionActual: "Peakly"
    token_type: "bearer"
    userName: "Administrador"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "message": "Usuario/Contraseña invalidos"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

