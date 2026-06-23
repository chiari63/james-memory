---
type: entity
status: active
created: 2026-06-23
updated: 2026-06-23
tags: [homelab, monitoramento, uptime-kuma]
related: [Infraestrutura Homelab, VPS Local, VPS Remota, Resposta a Alertas do Uptime Kuma]
---

# Uptime Kuma

Sistema de monitoramento do homelab do Lucas.

## Função

O Uptime Kuma monitora aplicações e serviços do homelab e envia alertas para o James/Hermes via webhook.

## Localização

- Roda em Docker na [[VPS Local]] (`10.0.0.90`).

## Payload operacional esperado

Os alertas enviados ao James incluem pelo menos:

- nome da aplicação/monitor;
- IP da VPS onde a aplicação está rodando.

## Encaminhamento para Hermes

O envio passa pelo Hermes Signer Proxy, que traduz/assina o webhook do Uptime Kuma para o Hermes.

## Expectativa de resposta

Quando receber um alerta, James deve investigar o erro, tentar levantar novamente a aplicação/serviço com segurança e verificar recuperação.

Procedimento relacionado: [[Resposta a Alertas do Uptime Kuma]].
