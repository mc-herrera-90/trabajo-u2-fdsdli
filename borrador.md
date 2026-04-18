### 5. ¿Existió sabotaje, daño, alteración o eliminación de datos?

Si, existió un _sabotaje_, un _daño en el sistema informático_ y además una _alteración_ de este, ya que el ataque DDoS ejecutado en el quinto día paralizó por completo la logística de la cadena fría, afectando directamente los sistemas de despacho. Según la Ley N°21.459, se estarían infringiendo los siguientes artículos: __Artículo 1__, __Artículo 2__ y __Artículo 3__.

### 6. ¿Podría aplicarse la figura de “daño informático” aunque los datos solo hayan sido copiados?

Puede aplicarse la figura de _"daño informático"_ al caso, ya que de todos modos el atacante decidió usar su influencia en el sistema para detener el funcionamiento normal del mismo, además de subir las muestras de las fórmulas y datos sensibles en la dark web a modo de respuesta a la empresa por no recibir el pago de la extorsión.

### 7. ¿El correo exigiendo criptomonedas constituye “extorsión”?

Según el _Inciso 1_ del __Artículo 7__ de la __Ley N° 21.459__, el correo enviado por el atacante hacia la gerencia de la empresa exigiendo 15 bitcoins (14.375 UTM, 1.004.666.507 pesos chilenos aproximados) si constituye como extorsión y la condena es presidio menor en sus grados medio a máximo con multas de 11 a 15 UTM (768.779 a 1.048.335 pesos chilenos).

### 8. ¿Qué fallos de seguridad permitieron el ataque?

Dentro de la empresa, nunca se implementaron distintos métodos de seguridad para proteger tanto la _integridad del sistema_ como la _información sensible almacenada_, asímismo, faltaban los protocolos a seguir según la __Ley N° 21.663__ como entregar los reportes a la __ANCI__, detallando el ataque detectado, las medidas de seguridad practicadas y un informe sobre los efectos negativos que tuvo la empresa. Entre ellas, tampoco se detectaron _segmentaciones en el servidor_, lo que hace que cualquier usuario tenga _privilegios excesivos_, además de acceder al sistema sin la _autentificación de doble factor_. Las _capacitaciones sobre seguridad_ no se realizaban periódicamente, no se realizaron _auditorías_ en los __últimos 18 meses__ y finalmente la empresa tampoco notificó a las autoridades ni a los usuarios sobre el ataque, el argumento que entregaron es que todavía estaban evaluando su alcance.

### 9. ¿Existían políticas de control de acceso y cifrado de datos?

Haciendo énfasis en la pregunta anterior, la empresa no contaba con políticas de control de acceso y cifrado de datos formales que regulen el acceso a información sensible y la protección de datos en tránsito y reposo. Debido a la falta de presencia de los métodos mencionados, se le facilitó la entrada ilícita del atacante al sistema informático, además de irrumpir el funcionamiento normal de este y la filtración de datos.

### 10. ¿Se cumplían los estándares mínimos de ciberseguridad exigidos por la ley?

Logística Austral Ltda. no cumplía con los estándares mínimos de ciberseguridad exigidos por las __leyes N° 21.459, N° 19.628 y los estándares ISO/IEC 27001__. --porque durante el ataque no se han protegido los datos de los clientes, tampoco la integridad del sistema y no se han seguido las cláusulas del SGSI para controlar el problema.--

### 11. ¿La empresa realizaba auditorías de seguridad periódicas?

Según el relato del caso, la empresa no realizaba auditorías de seguridad periódicas, la última auditoría notificada y registrada fue hace 18 meses (1 año y 6 meses).

### 12. ¿Existía un plan de respuesta ante incidentes?

La organización no contaba con un plan de respuesta formal ante incidentes, en el relato menciona que la empresa solo se excusó de _evaluar el alcance del ataque_ y no notificó a las autoridades sobre el incidente.

### 13. ¿Cómo debería responder la empresa ante el incidente según la ley?

Según los __Artículos 4, 9, 27 y 32__ de la __Ley N° 21.663__, la empresa debería responder con reportes inmediatos del incidente con un plazo obligatorio de _3 horas desde que se tiene en conocimiento_. _Dentro de 72 horas posterior_ a la primera notificación, se debe _entregar una actualización_ que incluye la evaluación inicial del incidente, su gravedad e impacto, debe incluir indicadores de compromiso (si están disponibles). Finalmente, si la empresa es considerada Operador de Importancia Vital, deben entregar en un _plazo máximo de 15 días_ un informe detallado sobre el incidente, incluyendo gravedad e impacto, el tipo de amenaza que se presentó, las medidas de mitigación aplicadas y en curso, y si procede se deben mencionar las repercusiones transfronterizas.

### 14. ¿Qué acciones urgentes debe tomar para contener el daño?

Como propuesta(s) urgentes para la empresa, se debe aislar el/los sistema(s) afectados desconectando físicamente los equipos comprometidos, aislar el/los servidor(es), backups realizados y bases de datos. También se recomienda preservar la(s) evidencia(s) para la colaboración de la investigación, realizar análisis forenses, notificar a las autoridades correspondientes (CSIRT Nacional) junto a los clientes y socios sobre el ataque detectado, además de implementar nuevas medidas de seguridad como recomendar cambiar de contraseña a una más robusta.

### 15. ¿A qué autoridades debe notificar?

Tras la vigencia de la __Ley N° 21.663__ "Ley Marco de Ciberseguridad" desde 1 de marzo de 2025, los organismos están obligados a reportar los incidentes principalmente a la __Agencia Nacional de Ciberseguridad__ _(ANCI)_. Dentro de la ley, las empresas tienen 3 --oficinas-- en donde recurrir, dependiendo del contexto del ataque y el motivo del mismo _(CSIRT Nacional, CSIRT de la Defensa Nacional, Brigada Investigadora del Cibercrimen - PDI)_. En el caso de Logística Austral Ltda., debe reportar directamente a la __ANCI__.

### 16. ¿Se vulneró el principio de confidencialidad y seguridad de los datos?

Según el __Artículo 2__ _inciso G_, __Artículo 7__, __Artículo 10__ y __Artículo 11__ que forman parte de la __Ley N° 19.628__, si se confirma que Logística Austral Ltda. ha vulnerado los principios de confidencialidad y seguridad de los datos al no implementar los métodos de seguridad obligatorios mencionados en la __Ley N° 21.663__ y la __Norma ISO/IEC 27001__.

### 17. ¿Se protegieron los datos personales de acuerdo con la ley?

Se menciona explícitamente que la empresa no ha protegido los datos personales con las medidas técnicas y organizacionales suficientes. El servidor junto la base de datos no contaban con cifrado de datos, segmentación, autenticación de doble factor y la empresa no contaba con un protocolo para actuar bajo un ataque cibernético.

### 18. ¿Qué responsabilidad tiene la empresa por la filtración?

La _responsabilidad civil, administrativa y penal_ que están fundamentadas por ambas __Leyes N° 19.628 y N° 21.459__ castigan severamente a la empresa Logística Austral Ltda. y obligan a pagar una indemnización por la causal de dañar el patrimonio y/o la moral del usuario, las multas van dependiendo de la gravedad del caso, aunque generalmente se decreta pagar entre 1 a 10 UTM, incluso la autoridad puede imponer medidas de seguridad para subsanar las brechas de seguridad detectadas. Finalmente se considera a la empresa como responsable de los daños causados, además implican sanciones por incumplir los protocolos de seguridad y protección de datos, pérdida total o parcial de beneficios fiscales, prohibición temporal o perpetua de contratar con el estado y disolución o cancelación de la personalidad jurídica (si aplica en casos extremos).

### 19. ¿Incumplió su deber de proteger los datos?

Logística Austral Ltda. si omitió/incumplió las implementaciones de los principios de seguridad, proporcionalidad y necesidad. Al no contar con protocolos fundamentales en el momento del ataque, se infiere que la empresa, y por lo tanto la gerencia, no supo que hacer en el momento y decidieron tratar de ocultar los hechos.

### 20. ¿Omitió notificar a los afectados y a la autoridad de control? 

La empresa si omitió notificar a los afectados, a las autoridades y a la prensa en el momento de sufrir el ataque. Según los _Artículos 7, 8 y 9_ de la __Ley N° 21.663__ exigen que se activen los protocolos de aviso hacia los organismos correspondientes en tiempos acotados, además de cumplir con las normas de protección de los datos.

### 21. ¿Qué tipos de datos personales fueron comprometidos que están específicamente protegidos por el GDPR?

Según el __Reglamento General de Protección de Datos__, se vieron comprometidos los siguientes aspectos de la empresa Logística Austral Ltda.: Datos personales básicos (Nombres, Apellidos, Números de teléfonos, Correos Electrónicos) y Datos sensibles (Información clasificada de la Salud, como los expedientes médicos de los pacientes e información médica oncológica).

### 22. Si Logística Austral tuviera clientes/laboratorios en la Unión Europea, ¿qué obligaciones tendría bajo el GDPR tras detectar la filtración? 

Si la empresa estuviera bajo el seno del __Reglamento General de Protección de Datos__, tendría la obligación de seguir estrictamente _los incisos del Artículo 33_ que dictan lo siguiente: En caso de violación de datos personales, el responsable del tratamiento notificará sin demora indebida y, cuando sea posible, a más tardar 72 horas después de haber tenido conocimiento de ella. Cuando la notificación a la autoridad no se realice dentro del plazo estimado, deberá ir acompañada de los motivos del retraso. El contenido de la notificación debe mencionar la naturaleza de la violación de datos personales, comunicar el nombre y datos de contacto del Delegado de Protección de Datos, las posibles consecuencias de la violación de datos personales y describir las medidas propuestas por el responsabe para abordar la problemática, incluidas las medidas de mitigación los posibles efectos adversos, si aplica. Finalmente, el responsable del tratamiento documentará cualquier violación de datos personales, incluyendo los hechos relacionados con la violación de datos personales, sus efectos y las medidas correctivas adoptadas.

### 23. ¿Qué elementos de la base de datos comprometida podrían ser considerados "Protected Health Information (PHI)" bajo la normativa HIPAA? 

Los elementos de la base de datos de la empresa que están comprometidos y son considerados Protected Health Information serían los Nombres, Apellidos, RUT, Direcciones, Contacto (tanto número de teléfono como correo electrónico), Tipo de Afiliaciones en la Salud, Historial Médico, Resultados Emitidos de Laboratorios y Diagnósticos.

### 24. Si brindara servicios a entidades de salud en EE. UU., ¿qué consecuencias podría enfrentar por la filtración de datos médicos bajo HIPAA?

Si la empresa brindara servicios a entidades de salud en Estados Unidos e infringe las normas HIPAA, se enfrenta a dos principales sanciones. La primera sanción le cobra una multa económica por parte de la Oficina de Derechos Civiles (OCR) del Departamento de Salud y Servicios Humanos (HSS), el valor de la multa puede variar desde los $100 dólares hasta más de $60,000 dólares por infracción detectada, con un tope máximo anual de $2.000.000 dólares para violaciones reiteradas. La segunda sanción proviene del Departamento de Justicia y determina si la información de información protegida fue obtenida y/o divulgada con intención maliciosa o para beneficio personal, en el caso de tener conocimiento sobre esta información se decreta hasta máximo 1 año de prisión, entregar falsos pretextos ante el jurado se decreta hasta 5 años de prisión, finalmente si se corrobora una intención maliciosa o de lucro se decreta hasta 10 años de prisión. Se pueden recurrir a acuerdos de resolución con planes supervisados por el gobierno, pero a cambio se daña la reputación de la empresa, perdiendo pacientes y credibilidad en el mercado, y se limitan las acciones profesionales como una suspensión de licencias.

### 25. ¿Qué lecciones pueden aprender las empresas de logística crítica del cumplimiento de normativas internacionales tras un incidente como este? 

Las empresas de logística crítica pueden aprender como principal lección que el cumplimiento normativo no debe considerarse como un aspecto opcional, sino como un componente esencial de la continuidad operacional y de la gestión de riesgo. Incidentes como la situación de Logística Austral Ltda. evidencian la necesidad de adoptar y mantener estándares y marcos regulatorios internacionales aplicables, como el __Reglamento General de Protección de Datos__ _(GDPR)_, la __Ley de Portabilidad y Responsabilidad de Seguros de Salud__ _(HIPAA)_ y la __Norma ISO/IEC 27001__. 

En este contexto, la protección de datos sensibles, en especial la información médica y propiedad intelectual, se considera crítica ya que su exposición puede generar consecuencias reputacionales severas, pérdida de confianza de los clientes y socios estratégicos, sanciones administrativas y económicas significativas. 

Para prevenir incidentes similares, las organizaciones deben implementar controles técnicos y organizacionales adecuados, como la _autenticación multifactor_ en accesos remotos, segmentación de redes, aplicación del principio de mínimo privilegio, monitoreo continuo de logs, auditorías periódicas y capacitaciones recurrentes frente a amenazas como smishing y phishing. 

Asimismo, resulta indispensable contar con un plan formal de respuesta a incidentes que permita contener el ataque, evaluar el impacto y ejecutar procesos de notificación según las obligaciones establecidas en la norma aplicable. Finalmente, estas medidas deben complementarse con el cumplimiento de la legislación nacional vigente, asegurando una gestión integral de la seguridad de la información y la protección en contextos tanto locales como internacionales.
