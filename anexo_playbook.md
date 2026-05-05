## Playbook de Respuesta Operativa

**Caso:** SecureLogistics S.A.

**Amenaza analizada:** Intrusión por Fuerza Bruta SSH y Riesgo de Ejecución de Código en `/tmp`.

**Agente Afectado:** 002 (Ubuntu-Server) -> Intrusión por Fuerza Bruta SSH y Riesgo de Ejecución de Código en _/tmp_.

| Etapa del Playbook | Indicaciones Técnicas a Ejecutar |
| :--- | :--- |
| **1. Detección y Análisis** | - **Reglas Wazuh disparadas:** ID 5551, 5712, 2502 (Nivel 10).<br>- **Vector:** `tty=ssh`, apuntando a `user=root`.<br>- **Origen malicioso:** IP: 213.209.159.158 (Alemania), 92.118.39.197 (Romania).<br>- **Escalamiento:** Notificar inmediatamente al CISO y Administrador de Red. |
| **2. Contención Inicial** | - **Corto Plazo:** Ingresar las IP mencionadas a la lista negra del Firewall perimetral y de AWS/Azure (Network Security Group).<br>- **Corto Plazo:** Detener temporalmente el servicio `sshd` si los intentos persisten desde otras IPs. |
| **3. Erradicación** | - **Acción 1 (Identidad):** Modificar `/etc/ssh/sshd_config` para establecer `PermitRootLogin no` y `PasswordAuthentication no` (forzando uso de llaves RSA/Ed25519).<br>- **Acción 2 (Hardening Sistema):** Modificar `/etc/fstab` para montar el directorio `/tmp` con las directivas `nodev`, `nosuid`, y `noexec` para mitigar las alertas SCA 35510, 35512 y 35513. Reiniciar el demonio `systemd`. |
| **4. Recuperación** | - **Validación:** Ejecutar un nuevo escaneo manual de "Configuration Assessment" en el agente 002 (Ubuntu-Server) para verificar que el Score suba del 49% actual y las reglas del `/tmp` marquen "Passed".<br>- **Monitoreo:** Crear regla personalizada en Wazuh para notificar por email si se detectan más de 5 fallos SSH en 1 minuto. |
| **5. Lecciones Aprendidas** | - **Reflexión Estratégica:** Ningún servidor debe ser expuesto a WAN sin un checklist de seguridad previo. Se debe redactar una política de control de acceso que estipule la obligatoriedad de VPN o conexiones Zero Trust para la administración remota de infraestructura crítica. |