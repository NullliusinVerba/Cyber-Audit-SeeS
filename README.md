# Proyecto: Hardening Automatizado para Infraestructura Crítica (OIV)

> **Resumen:** Implementación de un pipeline de Hardening automatizado con Ansible para mitigar vulnerabilidades críticas (CVEs) en un servidor Ubuntu, garantizando la idempotencia y el cumplimiento normativo de la Ley 21.663.

## Contexto
Este repositorio contiene la auditoría de seguridad y la remediación automatizada para la infraestructura simulada de "Soporte Experto Educación Superior" (SEES), designada como Operador de Importancia Vital (OIV) bajo la Ley 21.663 (Chile).

## Tecnologías Utilizadas
* **OpenVAS:** Escaneo de vulnerabilidades.
* **Kali Linux:** Nodo de control.
* **Metasploitable3 (Ubuntu 14.04):** Host vulnerable.
* **Ansible:** Motor de automatización y hardening (IaC).

## ¿Qué hace este proyecto?
1. Documenta el hallazgo de 5 vulnerabilidades críticas (CVEs).
2. Automatiza la mitigación de las vulnerabilidades de configuración SSH (Algoritmos KEX débiles y bloqueo de login de root) usando Ansible.
3. Implementa *Idempotencia* mediante el uso de Handlers (reinicio de servicio seguro).

## Estructura del Repositorio
* `ansible/`: Playbooks e inventario para ejecutar el hardening.
* `docs/`: Documentación de evidencia (Auditoría inicial y proceso de conexión).

## Cómo ejecutarlo
**Requisitos previos:** 
* Ansible instalado en el nodo de control.
* Módulo `sshpass` instalado (para manejo de contraseñas SSH).

1. Clonar el repositorio y acceder a la raíz del proyecto.
2. Ejecutar el playbook (solicitará la contraseña SSH y la de `sudo`):

```bash
ansible-playbook -i ansible/inventory.ini ansible/hardening.yml -k -K
