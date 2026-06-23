---
type: knowledge
status: active
created: 2026-06-23
updated: 2026-06-23
tags: [homelab, monitoramento, incident-response, uptime-kuma]
related: [Infraestrutura Homelab, Uptime Kuma, VPS Local, VPS Remota, Hermes Signer Proxy]
---

# Resposta a Alertas do Uptime Kuma

Procedimento consolidado para quando James receber um webhook do [[Uptime Kuma]] informando que uma aplicação ou serviço do homelab caiu.

## Significado do alerta

O webhook traz pelo menos:

- nome da aplicação/monitor;
- IP da VPS onde ela está rodando.

Esse alerta deve ser tratado como incidente operacional, não apenas como notificação.

## Inventário de referência

| IP | Host | Serviços |
|---:|---|---|
| `10.0.0.90` | [[VPS Local]] | WireGuard, Hermes Agent/James, Uptime Kuma, Nginx, Homepage, Portainer, Watchtower, CrowdSec, Pi-hole secundário, Unbound secundário, Hermes Signer Proxy |
| `10.0.0.207` | [[VPS Remota]] | Pi-hole primário, Unbound primário, Fail2ban |

## Processo de resposta

1. Identificar o host pelo IP informado.
2. Identificar a aplicação pelo nome do monitor.
3. Verificar se o serviço é Docker ou bare-metal.
4. Investigar causa provável:
   - status do container ou serviço;
   - logs recentes;
   - portas/listeners;
   - uso de disco, memória ou CPU se relevante;
   - dependências como DNS, proxy reverso ou rede Docker.
5. Tentar restauração segura:
   - reiniciar container ou serviço quando apropriado;
   - evitar ações destrutivas;
   - nunca apagar ou sobrescrever `.env`;
   - pedir autorização antes de mudanças privilegiadas ou arriscadas fora da confiança operacional já dada por Lucas.
6. Verificar recuperação com status, health check ou teste de porta/endpoint.
7. Reportar resumo curto:
   - o que caiu;
   - host/IP;
   - causa provável;
   - ação executada;
   - status atual;
   - próximo passo se não resolveu.

## Observações

- Serviços Docker da [[VPS Local]] devem ser investigados primeiro via containers/logs.
- Serviços bare-metal da [[VPS Remota]] devem ser investigados via serviço/processo do host.
- Se o problema for ausência de alerta, verificar [[Hermes Signer Proxy]], [[Uptime Kuma]] e conectividade com o Hermes.
