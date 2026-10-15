# Backlog — STT Hub

Iniciado em **15 de outubro de 2026**. IDs próprios, independentes do
backlog do STT-widget. Registrar uma etapa não autoriza executar todas.

| ID | Etapa | Estado |
| --- | --- | --- |
| HUB-001 | Preparar identidade, pasta/repo próprios, referências e handoff. | Concluída; GitHub público e clone independente conferidos. |
| HUB-002 | Registrar recorte e decisões de produto. | Rodada concluída: decisões atuais em DECISOES.md; sequência de entrega a detalhar. |
| HUB-003 | Preparar Angular/Orquestra e avaliar backend/reaproveitamento. | Frontend definido; obter skills/componentes no ambiente de destino. Backend aberto. |
| HUB-004 | Scaffoldar a aplicação e documentar execução local. | Próxima etapa de implementação, conforme arquitetura e pedido do usuário. |
| HUB-005 | Transcrever e processar texto com AWS. | Bedrock e Amazon Transcribe confirmados; preservar opções para comparação e contratos de retomada. |
| HUB-006 | Gravar somente o microfone no navegador, com pausas/interrupções. | Funcionalidade confirmada; definir navegadores e limites. |
| HUB-007 | Detalhar importação, histórico, reprodução e exportação. | Alcance e prioridade pendentes; não fixar upload como primeira fatia. |
| HUB-008 | Investigar Entra ID e definir autorização/isolamento. | Login real aberto; mock somente para desenvolvimento. Necessário antes de abrir o serviço a terceiros. |
| HUB-009 | Validar com usuários e definir planos/cobrança. | Pendente de produto e custos conhecidos. |
| HUB-010 | Implementar abas/grupos, Juntar/Mesclar, Teams/instruções e opções visuais. | Escopo confirmado; preservar regras de origem e adaptar a Angular/Orquestra. |
| HUB-011 | Adaptar screenshots e vínculos temporais ao navegador. | Escopo confirmado; aquisição/editor ainda precisam de investigação. |
| HUB-012 | Trazer bypass opcional do pré-processamento, de BL-099. | Escopo confirmado, ainda não implementado na origem; filtros e conversões devem ser separados. |
| HUB-013 | Investigar Whisper inteiramente no navegador. | Viabilidade documental identificada; runtime, modelo e fallback não aprovados. |
| HUB-014 | Investigar S3 e desenhar persistência de arquivos/metadados. | Preferência por S3; validar conta, região, buckets, permissões, concorrência e custos. |

## HUB-001 — Organização inicial

Pedido do usuário: preparar a transição para uma nova sessão, usando
**STT Hub** desde o início, sem encerrar o desktop. A base leva contexto,
procedência e um mapa de consulta, sem importar fontes ou dados em bloco.
O usuário definiu GitHub público e pediu continuidade em outra máquina.
O histórico começa neste novo repositório; referências ao desktop usam URLs
do GitHub, sem depender da pasta local da preparação.

## HUB-002 e HUB-003 — Próxima etapa

Usar [ESCOPO.md](ESCOPO.md) e [DECISOES.md](DECISOES.md) como referência atual.
Angular/Orquestra e a direção AWS já foram escolhidos. Obter os artefatos de
Orquestra no ambiente de destino e detalhar limites, backend e persistência.
Avaliar Go no servidor a partir de [ORIGEM.md](ORIGEM.md), sem assumir
portabilidade imediata do núcleo. As investigações estão em
[INVESTIGACOES.md](INVESTIGACOES.md).

Fora desta versão: Equipe, áudio do sistema, vídeo, botoneira e conectores
de IA por API genérica/OpenAI/OpenRouter/Azure. Outros itens desktop não
foram selecionados automaticamente. BL-098 permanece abandonado.

As etapas de produto são uma ordem de discussão, não uma ordem que permita
adiar autorização e isolamento até depois de publicar o serviço.
