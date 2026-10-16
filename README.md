# 📅 Enjunin Turnos

> **Vitrina pública** del proyecto *enjunin Turnos* — SaaS multitenant de
> gestión de turnos para consultorios y clínicas. Acá vas a encontrar
> descripción, stack y roadmap; **el código fuente es privado**.
> Hermana del portal [enjunin Autos](https://github.com/GuCHoGaRCia/enjunin-motors).

![PHP](https://img.shields.io/badge/PHP-8.2-777BB4?logo=php&logoColor=white)
![Laravel](https://img.shields.io/badge/Laravel-12-FF2D20?logo=laravel&logoColor=white)
![Livewire](https://img.shields.io/badge/Livewire-3-FB70A9?logo=livewire&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL%2FMariaDB-4479A1?logo=mysql&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-CDN-38B2AC?logo=tailwindcss&logoColor=white)

## ¿Qué es?

SaaS multitenant de turnos para consultorios: cada cuenta recibe su
subdominio **`{cuenta}.enjunin.com.ar`** con su propia base de
datos, y administra agenda, pacientes, caja y reportes; un panel central
(super-admin) gestiona cuentas, planes, auditoría e impersonación
firmada. Laravel con despliegue por FTP a hosting cPanel compartido —
**convive en el mismo servidor/ecosistema de enjunin.com.ar**.

## Funcionalidades

- 📅 **Agenda y turnos** — agenda semanal por profesional con bloqueos y
  reglas en la base de datos (un solo turno activo por profesional/hora;
  cancelar libera el hueco).
- 🏥 **Consulta e historia clínica** — historia clínica *append-only* por
  paciente, accesible desde la agenda.
- ⏳ **Lista de espera y sala de espera** — tablero en vivo con estados y
  avance de pacientes.
- 💵 **Caja y comprobantes** — apertura/cierre diario, movimientos y
  comprobantes inmutables (emitido → anulado con motivo, por trigger).
- 📊 **Reportes** — turnos por profesional y estado, facturación y
  métricas del consultorio.
- 🔔 **Recordatorios** — avisos por mail encolados (queue en base de
  datos) con envío programado.
- 👥 **Pacientes, profesionales y obras sociales** — fichas con datos
  personales bajo **Ley 25.326** (consulta, rectificación y borrado).
- 🔐 **Multitenant database-per-tenant** — cada cuenta con su BD y
  subdominio (`stancl/tenancy`), roles por sede (admin, recepción,
  profesional) e impersonación HMAC trazable desde la central.
- 📜 **Auditoría** — bitácora de cada acción (usuario, IP, cambios) en
  cada cuenta y en el panel central.
- 🧾 **Planes, suscripciones y pagos** — control de módulos por cuenta.

## Capturas

_Próximamente: acá van capturas reales de la aplicación._

## Roadmap

- [x] **Etapas 1–16** — núcleo completo: agenda, lista de espera, caja,
      facturación, reportes, historia clínica, planes y pagos
- [x] **Suite de calidad** — Pint + PHPUnit + 10 smokes (305 checks) +
      E2E HTTP (38 checks)
- [ ] **Despliegue a producción** — hosting cPanel sin SSH: empaquetado
      en 2 zips + inicialización por cron
- [ ] **Capturas reales** de la app desplegada

## Stack

PHP 8.2 · Laravel 12 · Livewire 3 · MySQL/MariaDB · Tailwind CSS y
FullCalendar por CDN (sin Node en producción) · queue en base de datos ·
PHPUnit + smokes + E2E · Git
