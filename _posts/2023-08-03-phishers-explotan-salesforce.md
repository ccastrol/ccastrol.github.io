---
title: Los phishers explotan los servicios de correo electrónico de Salesforce Zero-Day en una campaña de Facebook dirigida
date: 2023-08-04 6:33:00 +0800
categories: [ciberseguridad]
tags: [facebook, salesforce, phishin]
math: true
mermaid: true
image:
  path: /assets/images/Alerta-seguridad-phishers-salesforce/1.png
---

Guardio's Email Protección ha detectado una sofisticada campaña de phishing de correo electrónico que explota una vulnerabilidad de día cero en los servicios de correo electrónico legítimos y servidores SMTP de Salesforce. El equipo de investigación de Guardio Labs ha descubierto una vulnerabilidad explotada activamente que permite a los actores de amenazas crear correos electrónicos de phishing dirigidos bajo el dominio y la infraestructura de Salesforce. Esas campañas de phishing evaden hábilmente los métodos de detección convencionales al encadenar la vulnerabilidad de Salesforce y las peculiaridades heredadas en la plataforma de juegos web de Facebook. Guardio Labs ha divulgado estos hallazgos y ha trabajado con Salesforce y Meta para cerrar las vulnerabilidades y el mal uso.

Se ha observado una sofisticada campaña de phishing en Facebook que explota una falla de día cero en los servicios de correo electrónico de Salesforce, lo que permite a los actores de amenazas crear mensajes de phishing dirigidos utilizando el dominio y la infraestructura de la empresa.

### Correos electrónicos maliciosos enviados por pasarelas de correo electrónico de confianza

Desde los primeros días de Internet, hemos estado plagados de correos electrónicos maliciosos, que van desde el molesto spam hasta intentos de phishing personalizados y altamente dirigidos. A pesar de los avances significativos en la detección y el bloqueo de correo electrónico a lo largo de los años, los delincuentes siempre lograrán estar un paso por delante, ideando nuevas técnicas para evadir las reglas de filtrado y otras medidas legales diseñadas para limpiar nuestras bandejas de entrada.

![](/assets/images/Alerta-seguridad-phishers-salesforce/1.png){}

### Explotación de Salesforce para obtener la propiedad de la marca

Profundizar en el proceso de validación de correo electrónico de Salesforce permitió encontrar un flujo vulnerable. El truco está en la posibilidad de recibir correos electrónicos que se envían a @salesforce [.]com direcciones específicas y acceder a su contenido mediante el sistema de tickets del propio Salesforce. Ese contenido, en su caso, puede incluir el enlace de verificación que buscas.

![](/assets/images/Alerta-seguridad-phishers-salesforce/2.png){}

### Conclusión

La prevalencia de los ataques de phishing y las estafas sigue siendo alta, y los malhechores prueban continuamente los límites de la infraestructura de distribución de correo electrónico y las medidas de seguridad existentes. Un aspecto preocupante de esta batalla en curso es la explotación de servicios aparentemente legítimos, como CRM, plataformas de marketing y espacios de trabajo basados ​​en la nube, para llevar a cabo actividades maliciosas. Esto representa una brecha de seguridad significativa, donde los métodos tradicionales a menudo tienen dificultades para mantenerse al día con las técnicas avanzadas y en evolución empleadas por los actores de amenazas.

### Recomendaciones

### Dominios
lucafaioni[.]com
g5e[.]tech
carlogamesaqol[.]com
panthergrandpa[.]com
metaoperations-inc[.]com
operaciones-ntfaccounts[.] com
case-report-1883849[.]com
page-account-restricted68540.firebaseapp.com
meta-complain-copyright[.]com
business-request-review127989[.]web[.]app
business-account-15781759289[.]web[.]app
metabusiness-10930909301[.]web[.]app
meta-business-appeal89[.]web[.]app
gulaqkogames[.]com

### Fuente.
     Fuente 1: https://thehackernews.com/2023/08/phishers-exploit-salesforces-email
