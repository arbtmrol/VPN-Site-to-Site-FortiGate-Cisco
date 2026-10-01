# Documentación del Laboratorio: VPN Site-to-Site FortiGate - Cisco

## 1. Datos del laboratorio


**Estudiante:** Albert Morel  

**Matrícula:** 2025-0833  

**Asignatura:**  Seguridad de Redes

**Laboratorio:** VPN Site-to-Site FortiGate - Cisco  

**Plataforma utilizada:** GNS3  

---

## 2. Propósito del laboratorio

El propósito de este laboratorio es implementar una comunicación segura entre una red de usuarios y un servidor web utilizando una VPN Site-to-Site.

La VPN fue configurada entre un firewall FortiGate y un router Cisco. La comunicación entre ambas redes se realiza a través de un enlace IPsec, permitiendo que el usuario pueda acceder al servidor que se encuentra en la red remota.

Además, se realizaron pruebas de conectividad para comprobar que el túnel VPN está funcionando y que el tráfico entre las redes puede ser transportado mediante IPsec.

---

## 3. Objetivos

Los objetivos principales de la práctica son:

- Comunicar el usuario con el servidor a través del enlace VPN.
- Comprobar que la comunicación solo fluye si el enlace VPN está activo.

---

## 4. Topología

La infraestructura utilizada está compuesta por:

- 1 FortiGate.
- 2 routers Cisco.
- 1 switch.
- 1 equipo de usuario.
- 1 servidor web.
- Un enlace que representa el ISP.

El router R1 funciona como parte de la infraestructura intermedia entre el FortiGate y R2.

### Diagrama de la topología

<img width="738" height="616" alt="Topologia" src="https://github.com/user-attachments/assets/052a112f-f3d9-4b0a-8397-3e2b6dfa3f7e" />


---

## 5. Direccionamiento IP

El direccionamiento utilizado en la práctica se organizó de la siguiente manera:

| Dispositivo | Interfaz | Dirección IP | Máscara |
|---|---|---|---|
| FortiGate | port1 | 200.83.33.2 | 255.255.255.252 |
| FortiGate | port2 | 192.168.10.1 | 255.255.255.128 |
| R2 | FastEthernet0/0 | 200.83.34.2 | 255.255.255.252 |
| R2 | FastEthernet1/0 | 192.168.33.1 | 255.255.255.240 |
| Web Server | eth0 | 192.168.33.2 | 255.255.255.240 |

La red de usuarios utiliza una máscara `/25`, mientras que la red del servidor utiliza una máscara `/28`.

---

## 6. Redes utilizadas en la VPN

La comunicación protegida por la VPN se estableció entre:

**Red de usuarios:**

`192.168.10.0/25`

**Red del servidor:**

`192.168.33.0/28`

En R2 se utilizó una ACL para identificar el tráfico que debe ser protegido por IPsec:

```text
192.168.33.0/28 → 192.168.10.0/25
