:::portada
![Logo](assets/logo.png)
# Caso de estudio
## Operación cadena Fría | Logística Austral Ltda.

__Marco Contreras__  
&nbsp;&nbsp;[marco.contreras11@inacapmail.cl](mailto:marco.contreras11@inacapmail.cl)

__Benjamín Caba__  
&nbsp;&nbsp;[benjamin.caba@inacapmail.cl](mailto:benjamin.caba@inacapmail.cl)

<br/>

__Docente__: Marcos Nathanael Rodríguez Cerda
:::

<div class="page"/>

## Paso 1: Activos TI criticos (Hospital)


**1\. Historia Clinica Electronica**: Sistema central de registros medicos, datos de pacientes, prescripciones y resultados de laboratorio.

2. **Sistema de Monitoreo de Pacientes** : Dispositivos IoT medico (monitores de signos vitales, bombas de infusion conectadas).

3. **Infraestructura de Red Hospitalaria**: Switches, routers, firewalls, segmentos LAN/WLAN que conectan equipos criticos.

## Pasos 2, 3 y 4: Vulnerabilidades, Riesgo y Controles de Mitigacion

| ID | Activo Asociado | Vulnerabilidad Especifica | Tipo | CVSS | Prob | Impacto | Riesgo (PxI) | Zona | Control de Mitigacion | Funcion NIST CSF |
|----|----------------|---------------------------|------|------|------|---------|--------------|------|------------------------|------------------|
| A | EHR (Historia Clinica) | SQL Injection en portal de pacientes | Aplicacion | 8.6 (Alto) | 4 | 5 | 20 | Rojo | Validacion de entradas + consultas parametrizadas + WAF | Proteger (PR.IP) |
| B | EHR (Historia Clinica) | Autenticacion debil / politicas de contrasenas inseguras | Aplicacion/Host | 7.5 (Alto) | 3 | 4 | 12 | Amarillo | Implementar MFA + politicas robustas de contrasenas | Proteger (PR.AC) |
| C | Sistema de Monitoreo de Pacientes | Firmware desactualizado en dispositivos medicos IoT | Host | 9.0 (Critico) | 2 | 5 | 10 | Amarillo | Gestion centralizada de parches, escaneo periodico | Identificar (ID.RA) + Proteger (PR.IP) |
| D | Sistema de Monitoreo de Pacientes | Falta de segmentacion de red (dispositivos medicos en red general) | Red | 8.2 (Alto) | 3 | 4 | 12 | Amarillo | Segmentacion de red mediante VLANs dedicadas + firewalls internos | Proteger (PR.AC) |
| E | Infraestructura de Red Hospitalaria | Credenciales por defecto en switches/routers | Host | 9.8 (Critico) | 4 | 5 | 20 | Rojo | Cambio obligatorio de credenciales, implementar AAA y hardening | Proteger (PR.AC) |
| F | Infraestructura de Red Hospitalaria | Protocolos de cifrado obsoletos (TLS 1.0, SSHv1) | Red | 7.4 (Alto) | 2 | 4 | 8 | Amarillo | Deshabilitar TLS 1.0/1.1, actualizar a TLS 1.3 y SSHv2 | Proteger (PR.DS) |

## Matriz de Riesgos 5x5 (Probabilidad vs Impacto)

**Zonas:** Verde (Riesgo 1-4), Amarillo (Riesgo 5-12), Rojo (Riesgo 13-25)

| Probabilidad \ Impacto | Impacto 1 | Impacto 2 | Impacto 3 | Impacto 4 | Impacto 5 |
|------------------------|-----------|-----------|-----------|-----------|-----------|
| **Prob. 1** | 1 | 2 | 3 | 4 | 5 |
| **Prob. 2** | 2 | 4 | 6 | 8 (F) | 10 (C) |
| **Prob. 3** | 3 | 6 | 9 | 12 (B, D) | 15 |
| **Prob. 4** | 4 | 8 | 12 | 16 | 20 (A, E) |
| **Prob. 5** | 5 | 10 | 15 | 20 | 25 |

> Cada celda muestra el valor Riesgo = Probabilidad x Impacto. Las letras (A,B,C,D,E,F) indican las vulnerabilidades ubicadas en esa coordenada.

## Controles de mitigacion y funciones NIST CSF

- **Identificar (ID.RA):** Evaluacion de vulnerabilidades y parches (vulnerabilidad C).
- **Proteger (PR.AC):** Control de accesos, MFA, segmentacion, hardening (B, D, E).
- **Proteger (PR.DS):** Cifrado de comunicaciones (F).
- **Proteger (PR.IP):** Proteccion de aplicaciones y datos (A, C).

Cada riesgo ha sido mitigado con controles especificos: WAF + parametrizacion (A), MFA (B), parches (C), VLANs (D), cambio credenciales (E), TLS actualizado (F).
