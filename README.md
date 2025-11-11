# Lab 1.5: Users and Services Management

**Student:** Iván Ramos de la Torre  
**Date:** 11/11/2025  
**Course:** Operating Systems  

---

## 🧩 Executive Summary

Este laboratorio tuvo como objetivo aplicar los conceptos fundamentales de administración de sistemas Linux, incluyendo la gestión de usuarios y grupos, el control de servicios mediante **systemd**, la configuración de permisos y sudoers, así como el monitoreo del sistema y el análisis de logs.  
Durante la práctica, se implementaron tareas reales de administración, como la creación de usuarios con roles específicos, configuración de servicios del sistema (Apache2 y uno personalizado), y la generación de reportes de rendimiento para evaluar la salud general del sistema.

---

## ✅ Tasks Completed

- Creación y configuración de usuarios y grupos personalizados  
- Administración de permisos y configuración de sudo  
- Instalación y control de servicios con **systemctl**  
- Creación de un servicio personalizado administrado por systemd  
- Análisis de logs del sistema con **journalctl**  
- Monitoreo de recursos con **htop**, **df**, **ss** y **neofetch**  
- Automatización mediante scripts para gestión y monitoreo del sistema  

---

## 👥 Users and Groups Created

| User     | Groups                     | Home Directory  | Shell       | Purpose             |
|-----------|----------------------------|------------------|-------------|---------------------|
| alice     | developers, administrators | /home/alice      | /bin/bash   | Lead Developer      |
| bob       | developers                 | /home/bob        | /bin/bash   | Junior Developer    |
| charlie   | testers                    | /home/charlie    | /bin/bash   | QA Tester           |
| temp_user | (default)                  | /home/temp_user  | /bin/bash   | Temporary account   |
| service_account | (system user)        | N/A              | /usr/sbin/nologin | System process account |

---

## ⚙️ Services Configured

- **Apache2 web server:** instalado, habilitado y probado con `curl localhost`  
- **Custom simple-service:** servicio creado manualmente con script y unit file  
- **SSH service:** analizado mediante `systemctl status ssh`  
- **Systemd dependencies:** exploradas con `systemctl list-dependencies`  

El servicio personalizado (`simple-service.service`) genera registros periódicos en `/tmp/simple-service.log`, demostrando la ejecución continua y reinicio automático tras fallos.

---

## 🔐 Security Measures Implemented

- Configuración de grupo **developers** con permisos específicos sobre `/shared/projects`  
- Configuración de grupo **testers** con permisos sobre `/shared/testing`  
- Reglas de sudoers personalizadas que permiten a los developers reiniciar servicios web sin contraseña  
- Creación de usuarios con shells seguras y expiración de cuenta para usuarios temporales  
- Uso de `chmod` y `chgrp` para aplicar el principio de mínimo privilegio  

---

## 📊 System Monitoring and Analysis

- Análisis de logs del sistema con `journalctl`, `last` y `lastlog`  
- Revisión de servicios activos y dependencias mediante `systemctl`  
- Evaluación del rendimiento y consumo de recursos con `htop`, `df`, y `free -h`  
- Generación automática de reporte de rendimiento con `system-performance.sh`, que incluye CPU, memoria, disco y procesos principales  

El reporte final se guardó como `performance-report.txt` dentro de la carpeta `logs/`.

---

## 🧠 Key Learnings

- Comprensión práctica del manejo de usuarios y grupos en sistemas Linux  
- Uso de **systemd** como herramienta moderna para administrar servicios  
- Importancia del control de permisos y políticas sudo para la seguridad  
- Procedimientos de diagnóstico ante fallos de configuración en servicios  
- Automatización de tareas administrativas mediante scripts Bash  

---

## 🧩 Repository Structure

lab1.5-users-services/
├── README.md
├── docs/
│ ├── user-management-report.md
│ ├── service-configuration.md
│ ├── system-analysis.md
│ └── troubleshooting-log.md
├── configs/
│ ├── users-created.txt
│ ├── groups-configuration.txt
│ ├── permissions-matrix.txt
│ └── sudoers-changes.txt
├── services/
│ ├── simple-service.service
│ ├── service-status-report.txt
│ └── service-dependencies.txt
├── scripts/
│ ├── user-creation-script.sh
│ ├── service-monitoring.sh
│ ├── system-performance.sh
│ └── cleanup-script.sh
├── logs/
│ ├── initial-system-state.txt
│ ├── performance-report.txt
│ ├── service-logs-analysis.txt
│ └── troubleshooting-steps.txt
└── screenshots/
├── 01-user-creation-process.png
├── 02-group-memberships.png
├── 03-service-status-overview.png
├── 04-custom-service-running.png
├── 05-log-analysis.png
└── 06-system-monitoring.png

---

## 🧰 Scripts Implemented

- **user-creation-script.sh:** automatiza la creación de usuarios y grupos con validaciones  
- **service-monitoring.sh:** supervisa el estado de servicios críticos  
- **system-performance.sh:** genera reportes de rendimiento detallados  
- **cleanup-script.sh:** elimina usuarios y servicios de prueba de forma segura  

---

## 🧾 Reports Generated

- `user-management-report.md`: estructura de usuarios y grupos  
- `service-configuration.md`: servicios configurados y pruebas realizadas  
- `system-analysis.md`: análisis de rendimiento y logs  
- `troubleshooting-log.md`: procedimientos de resolución de errores  

---

## 🧮 Grading Rubric (Summary)

| Category | Weight | Description |
|-----------|---------|-------------|
| User Management | 25% | Creación correcta de usuarios, grupos y permisos |
| Service Administration | 25% | Configuración completa y funcional de servicios |
| System Analysis | 20% | Análisis detallado de logs y rendimiento |
| Automation & Scripts | 15% | Scripts funcionales y documentados |
| Documentation | 15% | Documentación clara, organizada y profesional |

---

## 🏁 Conclusion

Este laboratorio fortaleció las competencias prácticas en administración de sistemas Linux, combinando la gestión de usuarios, grupos y servicios con prácticas de seguridad y automatización. Además, permitió aplicar conceptos de **systemd**, control de permisos y análisis de rendimiento, fundamentales para el rol de administrador o ingeniero de sistemas.

---
