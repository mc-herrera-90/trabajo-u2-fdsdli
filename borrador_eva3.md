## I. Arquitectura y Responsabilidad

* Análisis Sectorial y Legal: El equipo justificará el nivel de impacto de una vulneración considerando los requerimientos del sector farmacéutico y la Ley 19.628.

El impacto de cualquier vulneración a un sistema informático que cuente con los requisitos vigentes de la __Ley N° 21.663__ _(Ley Marco de Ciberseguridad)_ para ser considerado como un _Operador de Importancia Vital_ es de un nivel muy alto ya que, a parte de afectar directamente al funcionamiento del mismo, puede llegar a generar pérdidas de __$15.000 USD por cada hora de inactividad__, recibir penalizaciones por parte de la justicia chilena y finalmente, como empresa, corren el riesgo de ruptura de la cadena de frío en medicamentos oncológicos críticos. Según la __Ley N° 19.628__ _(Protección de la Vida Privada)_, la sanción puede aplicarse como indemnización por el daño patrimonial por el tratamiento indebido de datos, el precio es establecido por el juez dependiendo de la gravedad del caso y el impacto, también se expresa que la empresa es la responsable de almacenar confidencialmente los datos de sus clientes.

https://www.bcn.cl/leychile/navegar?idNorma=141599&idParte=8642708 art. 23 19.628
https://www.bcn.cl/leychile/navegar?idNorma=141599&idParte=8642683 art. 2, inciso g 19.628
https://www.bcn.cl/leychile/navegar?idNorma=1202434&idParte=10496166 art. 4 21.663
https://www.bcn.cl/leychile/navegar?idNorma=1202434&idParte=10496167 art. 5 21.663



* Tríada CIA: Los estudiantes definirán las consecuencias operativas específicas en caso de verse
comprometida la Confidencialidad, Integridad o Disponibilidad de la plataforma.

En caso de que la empresa se viera comprometida con la Triada CIA, tendría las siguientes consecuencias operativas:

1. __Confidencialidad (Brecha de datos)__
* Filtración de historial médico: Un acceso no autorizado a la plataforma expondría historiales médicos y datos sensibles de pacientes oncológicos.

* Sanciones legales: Al vulnerarse la Ley N° 19.628, la empresa se expone a severas multas e indemnizaciones por daño patrimonial debido al tratamiento indebido de la información.

* Daño reputacional: Destrucción total de la confianza comercial con los laboratorios farmacéuticos y los centros hospitalarios a nivel nacional.

2. __Integridad (Alteración de datos)__
* Decisiones erróneas: El uso de inventarios manipulados podría resultar en el envío de dosis incorrectas o medicamentos equivocados a los hospitales, poniendo vidas en riesgo.

* Registros fraudulentos: Un atacante podría alterar los registros de temperatura, ocultando una ruptura en la cadena de frío de medicamentos críticos.

* Corrupción del sistema: Malware modificando la lógica de negocio del servidor Ubuntu, imposibilitando la correcta conexión entre los laboratorios y el sistema central.

3. __Disponibilidad (Interrupción de servicios)__
* Tiempo de inactividad: La paralización de la infraestructura IaaS genera pérdidas directas de $15.000 USD por cada hora que el sistema no opere.

* Ataques de ransomware: El secuestro de los servidores de contingencia impediría por completo la coordinación de los despachos logísticos vitales.

* Pérdidas financieras: Al no poder gestionar los tiempos de entrega, se produce la pérdida inminente de los medicamentos oncológicos por fallas en su refrigeración.

Empleando la siguiente tabla, el grupo delimitará las responsabilidades técnicas según el modelo IaaS:

| Capa del Stack | Responsable (Proveedor / Cliente / Compartida) | Justificación Técnica |
| :--- | :--- | :--- |
| Infraestructura Física (Data Center) | Proveedor | El proveedor es el dueño físico de las instalaciones y del hardware. |
| Red y Virtualización | Proveedor | El proveedor aloja, mantiene y actualiza las redes y virtualizaciones para dejarlos operativos 24/7. |
| Sistema Operativo (Ubuntu) | Cliente | El cliente es aquel que decide que SO usar en la máquina virtual y también es responsable del parcheo, hardening y protección de datos alojados en él. |
| Aplicación y Lógica de Negocio | Cliente | El cliente desarrolla, instala, configura y mantiene el software de la plataforma. |
| Datos y Gobernanza | Cliente | El cliente debe garantizar el cifrado de datos, el control de acceso y el cumplimiento normativo de las _leyes N° 19.628 y N° 21.663_. |


## IV. Gobernanza y Controles

**Política 1: Hardening**

| Elemento | Descripción |
| :--- | :--- |
| **Objetivo** | Prevenir la exposición de servicios vulnerables y mitigar accesos no autorizados mediante fuerza bruta en servidores de contingencia. |
| **Alcance** | Todos los servidores con sistema operativo Ubuntu desplegados en la infraestructura IaaS bajo la responsabilidad técnica del cliente. |
| **Control Técnico** | Obligatoriedad de acceso administrativo exclusivo mediante autenticación de llaves SSH (deshabilitando contraseñas planas) y cierre predeterminado de todos los puertos de red no esenciales mediante firewall. |

<br>

**Política 2: Continuidad Operativa y Gestión de Respaldos**

| Elemento | Descripción |
| :--- | :--- |
| **Objetivo** | Garantizar la disponibilidad e integridad de los datos logísticos y médicos ante incidentes críticos de secuestro de información. |
| **Alcance** | Todas las bases de datos de laboratorios farmacéuticos y repositorios de información almacenados en la plataforma logística central. |
| **Control Técnico** | Ejecución de respaldos automatizados con una frecuencia estrictamente alineada al RPO definido, almacenados en una ubicación de Disaster Recovery aislada de la red principal. |

Mapeo NIST CSF v2.0 __BASE__

| Control Propuesto | Función NIST CSF | Justificación de la Clasificación |
| :--- | :--- | :--- |
| Implementación de un Firewall de Aplicaciones Web (WAF) | Proteger (PR) | Actúa como una barrera defensiva para bloquear tráfico malicioso antes de que llegue al servidor Ubuntu. |
| Monitoreo de alertas 24/7 con el SIEM Wazuh | Detectar (DE) | Permite identificar anomalías en tiempo real y accesos no autorizados en la plataforma. |
| Ejecución de respaldos automatizados en Cloud DR | Recuperar (RC) | Permite restaurar los servicios logísticos y datos médicos tras un incidente para cumplir con el RTO. |

## V. Resiliencia y Disaster Recovery

| Métrica | Valor (Tiempo) | Justificación Financiera y Operativa |
| :--- | :--- | :--- |
| RTO (Recovery Time Objective) | 7 minutos | Si no se controla a tiempo (en minutos y máximo una hora) habrán pérdidas de $15.000 USD por hora y la medicina oncológica queda en riesgo logístico |
| RPO (Recovery Point Objective) | 2 minutos | Cada backup debe realizarse cada cierta cantidad mínima de minutos para no perder información crítica. |

Teniendo en cuenta las severas penalizaciones financieras y operativas a las que se enfrenta SecureLogistics S.A., se propone el uso de un Hot Site. Esta estrategia permite una conmutación por error en cuestión de segundos, garantizando que la empresa cumpla estrictamente con su agresivo RTO de 7 minutos y protegiendo así la integridad de los medicamentos oncológicos.
