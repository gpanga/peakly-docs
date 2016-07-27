---
date: 2016-07-25T23:31:10-03:00
title: Alta de punto de venta
weight: 32
---

El objetivo de este paso es definir en AFIP el punto de venta (o prefijo) que se va a utilizar para efectuar la facturación electrónica a través de Peakly.

**IMPORTANTE (RI)**: Si la empresa ya emite facturas electrónicas desde el sistema "Comprobante en línea" de la web de AFIP (RCEL) , igualmente debe cumplir este paso ya que se trata de otro sistema de facturación (RECE). Es necesario generar un nuevo Punto de Venta diferente al utilizado para "Comprobante en Línea" 

1. Ingresar con Clave Fiscal en el sitio web de la AFIP.  
![Login en la AFIP](/images/factura-electronica/fe-login-afip.png)

2. Click en "Servicios Administrativos Clave Fiscal" e ingresar en el "Administrador de Relaciones de Clave Fiscal" y hacer click en el botón "Nueva Relación". Hacer click en "Buscar" para seleccionar el servicio, click en "AFIP" y "Servicios Interactivos" y elegir "Administración de puntos de venta y domicilios".  

3. Ingresar desde la pantalla principal en el servicio "Administración de puntos de venta y domicilios".  
![Login en la AFIP](/images/factura-electronica/fe-ptovta-entrar-servicio.png)

4. Ingresar en la Opción "A/B/M Puntos de Venta".  
![Login en la AFIP](/images/factura-electronica/fe-ptovta-abm.png)  

5. La siguiente pantalla nos mostrara los puntos de venta que tenemos creados, y podremos crer uno nuevo en lla opción "Agregar".  
![Login en la AFIP](/images/factura-electronica/fe-ptovta-abm-listado.png)  

6. Ingresar el Código de Punto de Venta que es el prefijo que se desea para los comprobantes electrónicos, el Nombre de Fantasía, seleccionar la opción  "Factura electronica - Web services" como Sistema de facturación asociado e ingresar el Domicilio. Luego click en "Aceptar".  
![Login en la AFIP](/images/factura-electronica/fe-ptovta-abm-alta.png)  

7. Al presionar "Aceptar", ver que el punto de venta se haya creado correctamente en el listado.
