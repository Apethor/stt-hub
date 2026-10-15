# Backlog — STT Hub

Iniciado em **15 de outubro de 2026**. IDs próprios, independentes do
backlog do STT-widget. Registrar uma etapa não autoriza executar todas.

| ID | Etapa | Estado |
| --- | --- | --- |
| HUB-001 | Preparar identidade, pasta/repo próprios, referências e handoff. | Organização inicial preparada; ver HANDOFF.md. |
| HUB-002 | Fechar caso de uso e recorte da primeira entrega. | Próxima decisão com o usuário. |
| HUB-003 | Escolher stack e avaliar reaproveitamento seletivo. | Pendente de HUB-002. |
| HUB-004 | Scaffoldar a aplicação e documentar como executar localmente. | Pendente das decisões anteriores. |
| HUB-005 | Implementar primeira fatia: arquivo → transcrição → revisão → processamento → cópia. | Proposta; exige detalhamento. |
| HUB-006 | Implementar gravação de microfone e tratamento de pausas/interrupções. | Proposta para a primeira versão. |
| HUB-007 | Histórico, reprodução e exportação. | Proposta; definir retenção e formatos. |
| HUB-008 | Contas, autorização, dados privados, consumo e limites. | Definir na arquitetura; necessário antes de abrir o serviço a terceiros. |
| HUB-009 | Validar com usuários e definir planos/cobrança. | Pendente de produto e custos conhecidos. |

## HUB-001 — Organização inicial

Pedido do usuário: preparar a transição para uma nova sessão, usando
**STT Hub** desde o início, sem encerrar o desktop. A base leva contexto,
procedência e um mapa de consulta, sem importar fontes ou dados em bloco.
O GitHub inicial é privado e o histórico começa neste novo repositório.

## HUB-002 e HUB-003 — Próxima etapa

Usar [ESCOPO.md](ESCOPO.md) e [DECISOES.md](DECISOES.md) para separar escolhas
confirmadas de propostas. Selecionar o fluxo e os limites antes de criar
dependências de framework ou de provider. Avaliar Go no servidor a partir
de [ORIGEM.md](ORIGEM.md), sem assumir portabilidade imediata do núcleo.

As etapas de produto são uma ordem de discussão, não uma ordem que permita
adiar autorização e isolamento até depois de publicar o serviço.
