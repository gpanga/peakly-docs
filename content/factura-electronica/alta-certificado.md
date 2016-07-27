---
date: 2016-07-25T23:31:10-03:00
title: Generación del certificado digital
weight: 34
---

1. Ingresar con Clave Fiscal en el sitio web de la AFIP.  
![Login en la AFIP](/images/factura-electronica/fe-login-afip.png)

2. Click en "Servicios Administrativos Clave Fiscal" e ingresar en el "Administrador de Relaciones de Clave Fiscal" y hacer click en el botón "Nueva Relación". Hacer click en "Buscar"  para seleccionar el servicio, click en "AFIP" y "Web Services" y elegir "Administración de Certificados digitales". Luego ingrese al servicio.  
![Login en la AFIP](/images/factura-electronica/fe-certificado-servicio.png)

3. Agregue un nuevo alias como por ejemplo “Facturacion-2016”, y adjunte el archivo CSR brindado por Peakly, es importante antes pedir el CSR a soporte@peakly.co.  
![Login en la AFIP](/images/factura-electronica/fe-certificado-alta.png)

4. Una vez realizados los pasos mencionados, podrá verificar que la creación ha sido exitosa, y viendo el detalle del mismo le dirá el periodo de validez del certificado, además de un link de descarga del mismo. Este es un archivo con extensión CRT que se utiliza para comunicar el sistema con la AFIP para las diversas interfaces brindadas. Es importante brindar lo antes posible este certificado a Peakly.  
![Login en la AFIP](/images/factura-electronica/fe-certificado-completo.png)

5. Una vez que se descargo el certificado generado, debe subir el mismo, al certificado generado en Peakly haciendo click en "Subir Certificado".   
![Login en la AFIP](/images/factura-electronica/solicitud-certificado-completo.png)
