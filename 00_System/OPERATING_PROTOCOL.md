# Protocolo Operacional da Memória

Este protocolo orienta como James deve usar `/opt/james-memory`.

## Orientação inicial

Antes de modificar o Vault, James deve se orientar lendo ou consultando:

1. [[BOOTSTRAP]]
2. [[SCHEMA]]
3. [[01_Index/HOME]]
4. [[07_Context/CURRENT]]

Quando o assunto envolver uma área, projeto ou entidade específica, procurar notas existentes antes de criar novas.

## Fluxo de captura e consolidação

1. Capturar material bruto em [[08_Raw]] apenas quando necessário.
2. Avaliar se a informação tem valor futuro.
3. Procurar notas existentes relacionadas.
4. Atualizar conhecimento existente antes de criar nova nota.
5. Criar nova nota somente quando houver identidade ou utilidade própria.
6. Adicionar links internos relevantes.
7. Atualizar [[01_Index/HOME]], [[01_Index/MAPS]] ou [[07_Context/CURRENT]] quando necessário.
8. Registrar marcos em [[10_History/TIMELINE]] apenas quando forem importantes.

## Consulta

Ao responder perguntas com base na memória:

1. começar por [[01_Index/HOME]];
2. verificar [[07_Context/CURRENT]] se houver contexto ativo;
3. buscar notas relacionadas;
4. sintetizar a resposta citando as notas usadas quando útil;
5. salvar nova síntese apenas se ela tiver valor futuro.

## Manutenção

Periodicamente, James deve verificar:

- notas órfãs;
- links quebrados;
- duplicações;
- notas grandes demais;
- conteúdo preso em `08_Raw`;
- contexto ativo obsoleto;
- projetos encerrados ainda marcados como ativos.

## Quando atualizar MEMORY.md

MEMORY.md deve conter apenas contexto ativo e ponteiros úteis para o Vault.

Se um conhecimento precisar durar, ele deve ser consolidado aqui no Vault e MEMORY.md deve apontar para a nota, não copiar seu conteúdo.

## Quando criar Skills

Procedimentos repetíveis, comandos, workflows e soluções operacionais devem virar Skills, não notas longas no Vault.

O Vault pode explicar o que uma Skill representa e quando usá-la, mas a execução procedural pertence à camada de Skills.
