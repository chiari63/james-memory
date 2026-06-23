---
type: entity
status: active
created: 2026-06-23
updated: 2026-06-23
tags: [homelab, vps, infraestrutura]
aliases: [10.0.0.207]
related: [Infraestrutura Homelab, Uptime Kuma, VPS Local]
---

# VPS Remota

Host remoto do homelab do Lucas.

## Identificação

- IP: `10.0.0.207`
- Área relacionada: [[Infraestrutura Homelab]]
- Monitoramento: [[Uptime Kuma]]

## Serviços bare-metal

- Pi-hole primário;
- Unbound primário;
- Fail2ban.

## Observação operacional

Quando um alerta do [[Uptime Kuma]] mencionar o IP `10.0.0.207`, James deve investigar esta VPS remota. Como os serviços listados são bare-metal, a investigação deve começar por status do serviço, logs, portas/listeners e dependências do host.

Procedimento relacionado: [[Resposta a Alertas do Uptime Kuma]].
