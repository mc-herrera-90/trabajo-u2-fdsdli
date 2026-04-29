:::portada
![Logo](assets/logo.png)
# Actividad de Clase
## Taller práctico | Industria: Hospital

__Marco Contreras__  
&nbsp;&nbsp;[marco.contreras11@inacapmail.cl](mailto:marco.contreras11@inacapmail.cl)

__Benjamín Caba__  
&nbsp;&nbsp;[benjamin.caba@inacapmail.cl](mailto:benjamin.caba@inacapmail.cl)

<br/>

__Docente__: Marcos Nathanael Rodríguez Cerda
:::

<div class="page" />


## PASO 1: Selección de Industria
* **Industria seleccionada:** Hospital.
* **Justificación:** Los activos en este sector son de criticidad máxima; un incidente de seguridad no solo genera pérdidas financieras o de datos, sino que impacta directamente en la vida de los pacientes (ej. secuestro de sistemas en UCI).

---

## PASO 2: Identificación de Activos y Vulnerabilidades
Se han identificado 2 activos TI críticos para esta industria y 2 vulnerabilidades para cada uno:

### Activo 1: Sistema de Expedientes Médicos (EHR - Base de Datos)
Este activo almacena historiales clínicos, diagnósticos y datos personales de los pacientes.
1. **Vulnerabilidad 1A:** Autenticación débil o rota.
   * **Clasificación:** Nivel de Aplicación.
   * **CVSS Aproximado:** 8.1 (Alto).
2. **Vulnerabilidad 1B:** Exposición directa de base de datos a Internet.
   * **Clasificación:** Nivel de Red / Host.
   * **CVSS Aproximado:** 9.8 (Crítico).

### Activo 2: Red de Monitoreo de Signos Vitales (Dispositivos IoT en UCI)
Equipos médicos conectados a la red que transmiten telemetría vital en tiempo real.
1. **Vulnerabilidad 2A:** Software y Sistemas Operativos desactualizados (Legacy).
   * **Clasificación:** Nivel de Host.
   * **CVSS Aproximado:** 9.8 (Crítico).
2. **Vulnerabilidad 2B:** Protocolos no cifrados transmitiendo datos de salud.
   * **Clasificación:** Nivel de Red.
   * **CVSS Aproximado:** 7.5 (Alto).

---

## PASO 3 y 4: Estimación de Riesgo, Matriz y Controles NIST CSF

Para el cálculo, utilizamos la fórmula: _RIESGO = PROBABILIDAD × IMPACTO_.

### Leyenda de Zonas de Riesgo
* 🔴 **INACEPTABLE (15-25):** Acción inmediata.
* 🟠 **SIGNIFICATIVO (8-14):** Mitigación planificada.
* 🟡 **MODERADO (4-7):** Controles preventivos.
* 🟢 **ACEPTABLE (1-3):** Monitorización básica.

<div class="page"/>

### Matriz de Riesgo 5x5 (Heatmap)
Ubicación de los riesgos identificados en la matriz:

| Probabilidad \ Impacto | 1 (Insignificante) | 2 (Menor) | 3 (Moderado) | 4 (Mayor) | 5 (Catastrófico) |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **5 (Casi Seguro)** | 5 🟢 | 10 🟠 | 15 🔴 | 20 🔴 | 25 🔴 |
| **4 (Probable)** | 4 🟡 | 8 🟠 | 12 🟠 | 16 🔴 <br>**`[1B]`** | 20 🔴 <br>**`[1A]`**, **`[2A]`** |
| **3 (Posible)** | 3 🟢 | 6 🟡 | 9 🟠 | 12 🟠 <br>**`[2B]`** | 15 🔴 |
| **2 (Poco Prob.)** | 2 🟢 | 4 🟡 | 6 🟡 | 8 🟠 | 10 🟠 |
| **1 (Raro)** | 1 🟢 | 2 🟢 | 3 🟢 | 4 🟡 | 5 🟡 |

### Tabla de Mitigación y Framework NIST CSF
Propuestas de control de mitigación y su aplicación en las funciones del NIST CSF:

| ID | Vulnerabilidad Evaluada | Cálculo de Riesgo | Zona | Control Propuesto de Mitigación (Paso 3) | Función NIST CSF (Paso 4) |
| :---: | :--- | :--- | :--- | :--- | :--- |
| **`[1A]`** | **EHR:** Autenticación débil o rota | Prob. Alta (4) × Impacto Catastrófico (5) = **20** | 🔴 INACEPTABLE | Implementar Política de Contraseñas estricta y forzar MFA (Multi-Factor Authentication) en sistemas críticos. | **PROTEGER** (Controles de acceso). |
| **`[1B]`** | **EHR:** Exposición a Internet | Prob. Alta (4) × Impacto Mayor (4) = **16** | 🔴 INACEPTABLE | Implementar firewall de Base de Datos, listas de acceso (ACL) y requerir VPN. | **PROTEGER** (Protección de infraestructura). |
| **`[2A]`** | **IoT UCI:** SO desactualizado | Prob. Alta (4) × Impacto Catastrófico (5) = **20** | 🔴 INACEPTABLE | Aplicar segmentación de red estricta (VLANs), aislando los equipos de la UCI del resto de la red hospitalaria. | **PROTEGER** (Mantenimiento y arquitectura). |
| **`[2B]`** | **IoT UCI:** Protocolos no cifrados | Prob. Media (3) × Impacto Mayor (4) = **12** | 🟠 SIGNIFICATIVO | Forzar el uso de cifrado en tránsito (TLS/HTTPS) para proteger la telemetría. | **PROTEGER** (Protección de datos en tránsito). |