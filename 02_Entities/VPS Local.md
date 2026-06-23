---
type: entity
status: active
created: 2026-06-23
updated: 2026-06-23
tags: [homelab, vps, infraestrutura]
aliases: [10.0.0.90]
related: [Infraestrutura Homelab, Uptime Kuma, VPS Remota]
---

# VPS Local

Host local do homelab do Lucas.

## Identificação

- IP: `10.0.0.90`
- Área relacionada: [[Infraestrutura Homelab]]
- Monitoramento: [[Uptime Kuma]]

## Serviços bare-metal

- WireGuard;
- Hermes Agent / James.

## Serviços Docker

- Uptime Kuma;
- Nginx;
- Homepage;
- Portainer;
- Watchtower;
- CrowdSec;
- Pi-hole secundário;
- Unbound secundário;
- Hermes Signer Proxy.

## Observação operacional

Quando um alerta do [[Uptime Kuma]] mencionar o IP `10.0.0.90`, James deve investigar esta VPS. Para serviços Docker, começar verificando containers, logs, portas e dependências. Para serviços bare-metal, verificar serviço/processo no host.

Procedimento relacionado: [[Resposta a Alertas do Uptime Kuma]].
