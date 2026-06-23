---
type: entity
status: active
created: 2026-06-23
updated: 2026-06-23
tags: [homelab, webhook, hermes, uptime-kuma]
related: [Uptime Kuma, VPS Local, Resposta a Alertas do Uptime Kuma]
---

# Hermes Signer Proxy

Proxy que traduz/assina webhooks do [[Uptime Kuma]] para o Hermes/James.

## Localização

- Roda em Docker na [[VPS Local]] (`10.0.0.90`).

## Função

O Uptime Kuma envia alertas para este proxy, que adapta o webhook para o formato esperado pelo Hermes.

## Importância operacional

Se alertas do Uptime Kuma deixarem de chegar ao James, este proxy é uma das primeiras dependências a verificar, junto com o próprio [[Uptime Kuma]], rede Docker e endpoint do Hermes.
