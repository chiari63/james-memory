# Schema da Memória do James

Este schema define como o Vault `/opt/james-memory` deve crescer e ser mantido.

## Domínio

Memória semântica persistente do James/Hermes para Lucas Chiari: projetos, infraestrutura, automações, casa inteligente, estudos, ferramentas, decisões, entidades relevantes e conhecimento reutilizável.

## Estrutura

```text
00_System/      regras, princípios e protocolo da memória
01_Index/       mapas centrais e navegação
02_Entities/    pessoas, sistemas, tecnologias, dispositivos e conceitos nomeados
03_Projects/    esforços com objetivo, escopo e entregáveis
04_Areas/       responsabilidades contínuas
05_Knowledge/   conhecimento consolidado e reutilizável
06_Resources/   ferramentas, APIs, documentação e referências
07_Context/     foco atual e ponteiros ativos
08_Raw/         capturas temporárias e fontes brutas
09_Reflections/ aprendizados sobre a própria memória e modo de trabalho
10_History/     marcos importantes, não logs operacionais
99_Archive/     itens inativos, obsoletos ou substituídos
```

## Tipos de nota

Use o campo `type` no frontmatter quando uma nota representar conhecimento semântico, não apenas um README de pasta.

```yaml
---
type: entity | project | area | knowledge | resource | context | reflection | history
status: active | stable | draft | archived
created: YYYY-MM-DD
updated: YYYY-MM-DD
tags: []
---
```

Campos opcionais:

```yaml
aliases: []
related: []
confidence: high | medium | low
sources: []
```

## Convenções de nomes

- Pastas principais usam prefixo numérico para ordenação.
- Arquivos centrais podem usar nomes em maiúsculas: `HOME.md`, `CURRENT.md`, `SCHEMA.md`.
- Notas comuns devem usar nomes claros em português ou nomes próprios reconhecíveis.
- Evite nomes genéricos como `Notas.md`, `Diversos.md` ou `Coisas.md`.
- Uma nota deve ter um motivo claro para existir.

## Links

- Use wikilinks do Obsidian: `[[Nome da Nota]]`.
- Toda nota semântica deve buscar ter links para notas relacionadas.
- Relações importantes devem ser explícitas no texto, não apenas implícitas no nome do arquivo.
- Ao criar uma nota central, atualizar mapas ou índices relevantes.

## Política de criação

Crie uma nova nota apenas quando pelo menos uma condição for verdadeira:

- representa uma entidade recorrente;
- representa um projeto ativo ou histórico importante;
- representa uma área contínua de responsabilidade;
- consolida conhecimento reutilizável;
- registra uma decisão arquitetural relevante;
- preserva um marco histórico importante;
- evita que MEMORY.md fique grande demais.

Não crie nota para:

- menção passageira;
- pergunta simples;
- resposta temporária;
- conversa completa;
- log bruto sem síntese;
- informação redundante.

## Política de atualização

Antes de criar uma nota nova:

1. consulte [[01_Index/HOME]];
2. consulte [[07_Context/CURRENT]] se o assunto for ativo;
3. procure nomes relacionados no Vault;
4. atualize a nota existente se ela já representar o assunto.

Quando atualizar uma nota semântica:

- revise o campo `updated`;
- preserve decisões anteriores quando ainda forem relevantes;
- explicite contradições em vez de sobrescrevê-las silenciosamente;
- adicione links para entidades, projetos e áreas relacionados.

## Política para `08_Raw`

`08_Raw` é área de captura, não destino final.

Material bruto deve ser:

- temporário;
- claramente nomeado;
- consolidado depois em notas semânticas;
- descartado ou arquivado quando perder utilidade.

Conversas completas não devem ser armazenadas por padrão.

## Política para histórico

`10_History` registra marcos, não atividades rotineiras.

Registre apenas eventos com valor futuro, como:

- criação ou reestruturação da memória;
- decisões arquiteturais importantes;
- mudanças significativas de infraestrutura;
- início ou encerramento de projetos relevantes.

## Política de arquivamento

Use `99_Archive` para conteúdo que perdeu função ativa mas ainda tem valor histórico.

Ao arquivar:

- marque `status: archived` quando houver frontmatter;
- mantenha uma breve razão do arquivamento;
- substitua links ativos se necessário;
- não apague sem justificativa clara.

## Baixa entropia

A saúde do Vault depende de poucas notas boas, não de muitas notas vazias.

Prefira:

- síntese a transcrição;
- links a duplicação;
- atualização a proliferação;
- marcos a logs;
- clareza a taxonomias excessivas.
