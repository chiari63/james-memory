---
type: area
status: active
created: 2026-06-23
updated: 2026-06-23
tags: [homelab, infraestrutura, monitoramento]
related: [VPS Local, VPS Remota, Uptime Kuma, Resposta a Alertas do Uptime Kuma]
---

# Infraestrutura Homelab

Área contínua que reúne a infraestrutura do homelab do Lucas monitorada pelo [[Uptime Kuma]].

## Hosts principais

| Host | IP | Papel |
|---|---:|---|
| [[VPS Local]] | `10.0.0.90` | Host principal local; roda serviços bare-metal, Docker e o próprio James/Hermes. |
| [[VPS Remota]] | `10.0.0.207` | Host remoto; roda serviços essenciais de DNS e segurança. |

## Monitoramento

O [[Uptime Kuma]] monitora as aplicações do homelab e envia alertas via webhook para o James/Hermes.

O webhook inclui pelo menos:

- nome da aplicação/monitor;
- IP da VPS onde a aplicação está rodando.

Quando receber esse webhook, James deve tratar como incidente operacional: identificar host e aplicação, investigar a causa provável, tentar restaurar o serviço com segurança e verificar recuperação.

Procedimento relacionado: [[Resposta a Alertas do Uptime Kuma]].

## Inventário resumido

### VPS Local — `10.0.0.90`

Bare-metal:

- WireGuard;
- Hermes Agent / James.

Docker:

- Uptime Kuma;
- Nginx;
- Homepage;
- Portainer;
- Watchtower;
- CrowdSec;
- Pi-hole secundário;
- Unbound secundário;
- Hermes Signer Proxy.

### VPS Remota — `10.0.0.207`

Bare-metal:

- Pi-hole primário;
- Unbound primário;
- Fail2ban.
