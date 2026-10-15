# Decisões — STT Hub

Registro inicial: **15 de outubro de 2026**.

## Confirmadas

| ID | Decisão | Consequência |
| --- | --- | --- |
| D-001 | Produto chamado STT Hub. | Identificadores novos usam `stt-hub`; referências à origem usam STT-widget. |
| D-002 | Público inicial: profissionais individuais, para transcrever e trabalhar textos. | Colaboração de equipes não orienta o primeiro recorte. |
| D-003 | Pasta e repositório independentes. | Sem worktree, fork ou dependência permanente da pasta desktop. |
| D-004 | STT-widget pode continuar em paralelo. | O pivot não remove nem encerra o desktop. |
| D-005 | Organizar origem e continuidade antes de migrar a sessão. | Entregar mapa de módulos, contratos, decisões e handoff próprios. |

## Organização aplicada nesta preparação

| ID | Escolha | Motivo |
| --- | --- | --- |
| O-001 | Pasta `STT-Hub`, repo `Apethor/stt-hub`, branch `main`. | Aplicar o nome escolhido com identificadores convencionais. |
| O-002 | GitHub inicialmente privado. | Seguir a proposta de organização aceita nesta sessão. |
| O-003 | Histórico novo, com commits focados. | Registrar a evolução do SaaS sem importar o histórico desktop. |
| O-004 | Revisão fixa da origem: `361788018f841637d09c3931f64e8b2819d16347`. | Manter referências rastreáveis mesmo se o desktop evoluir. |
| O-005 | Levar documentação selecionada e uma referência de prompt; adiar cópia de código. | Avaliar o código junto do recorte e da arquitetura escolhidos. |
| O-006 | Preservar aviso MIT da origem para o material derivado. | Registrar procedência sem escolher a licença de todo o SaaS. |

## Propostas e decisões abertas

| Tema | Estado |
| --- | --- |
| Fluxo enviar/gravar, transcrever, revisar e preparar texto | Proposta de primeira versão. |
| Upload antes da gravação como primeira fatia | Proposta de sequência de implementação. |
| Cortes funcionais de `ESCOPO.md` | Propostos, sem aceite funcional. |
| Go no backend | Opção para avaliação; não é decisão final. |
| Framework de frontend e ferramentas | A escolher antes do scaffold. |
| Providers e modelos | A escolher; não herdar o catálogo do desktop. |
| Autenticação, banco, armazenamento e hospedagem | A escolher conforme o fluxo e os dados. |
| Limites, retenção, planos e cobrança | A definir antes de disponibilizar a terceiros. |
| Domínio, identidade visual e licença do código futuro | Pendentes. |

Acrescente decisões conforme forem tomadas, registrando o impacto e a
origem da escolha. A conclusão da preparação documental não valida as
hipóteses de produto nem encerra as decisões abertas.
