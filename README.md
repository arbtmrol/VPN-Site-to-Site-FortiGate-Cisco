# VPN Site-to-Site FortiGate - Cisco

## Video de demostración

> Video de la demostración del laboratorio:
>
> **[ENLACE DEL VIDEO — SE AGREGARÁ AL FINAL]**

---

## Datos del laboratorio

**Estudiante:** Albert Morel  
**Matrícula:** 2025-0833  
**Asignatura:** Infraestructura 2  
**Tema:** VPN Site-to-Site entre FortiGate y Cisco  
**Plataforma:** GNS3  

---

## Propósito del laboratorio

Implementar una VPN Site-to-Site entre un FortiGate y un router Cisco para permitir la comunicación segura entre la red de usuarios y el servidor web.

## Objetivos

- Comunicar el usuario con el servidor a través del enlace VPN.
- Comprobar que la comunicación solo fluye cuando el enlace VPN está activo.

## Topología

La topología está compuesta por un FortiGate, routers Cisco, un switch, un equipo de usuario y un servidor web.

## Direccionamiento IP

| Dispositivo | Interfaz | Dirección IP | Red |
|---|---|---|---|
| FortiGate | port1 | 200.83.33.2/30 | WAN |
| FortiGate | port2 | 192.168.10.1/25 | LAN |
| R2 | Fa0/0 | 200.83.34.2 | WAN |
| R2 | Fa1/0 | 192.168.33.1/28 | Servidor |
| Web Server | eth0 | 192.168.33.2/28 | Servidor |

## Configuración

La configuración completa del FortiGate y Cisco se encuentra en la carpeta `configuraciones/`.

## Evidencias

Las capturas de la configuración y las pruebas de conectividad se encuentran en la carpeta `capturas/`.

## Documentación

La documentación detallada del laboratorio se encuentra en `DOCUMENTACION.md`.
