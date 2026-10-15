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
| D-006 | GitHub público e continuidade em outra máquina. | Usar referências remotas da origem e instruções de clone; substitui a proposta inicial de repo privado. |
| D-007 | Captura somente do microfone da própria pessoa no navegador. | Solicitar permissão; remover modo Equipe e captura de áudio do sistema. |
| D-008 | IA cloud pela AWS: Bedrock e Amazon Transcribe. | Manter ambas as opções para comparar; Transcribe é serviço separado de Bedrock. Voxtral e o catálogo AWS da origem são referências, sujeitos à compatibilidade atual. |
| D-009 | Sem conectores de IA por API genérica, OpenAI/OpenRouter ou Azure nesta versão. | Não portar a tela/configuração desses providers. Isso não proíbe uma API própria do SaaS nem decide o login. |
| D-010 | Screenshots permanecem; vídeo sai. | Adaptar captura e vínculo temporal ao navegador, sem portar APIs nativas Windows. |
| D-011 | Painel de sons/botoneira fica fora desta primeira versão. | Decisão final da rodada, substituindo a indicação anterior de mantê-lo. |
| D-012 | Manter processamento, abas/grupos, Juntar/Mesclar, Teams de redação e instruções. | Preservar contratos úteis da origem; não confundir Teams com captura Equipe. |
| D-013 | Manter configurações e opções visuais. | Preservar organização funcional e preferências, adaptando apresentação ao padrão web. |
| D-014 | Trazer o bypass opcional do pré-processamento de BL-099. | Padrão habilitado, preferência persistida, originais preservados; distinguir filtros de conversões necessárias. Ainda não implementado na origem. |
| D-015 | Frontend Angular com padrão Orquestra. | Usar as skills/componentes do ambiente de destino; não substituir o padrão nem adivinhar dependências. |
| D-016 | Cada pessoa acessa somente seus dados, abas e grupos. | Autorizar recursos no servidor, além da tela de login; estratégia de autenticação ainda aberta. |

## Organização aplicada nesta preparação

| ID | Escolha | Motivo |
| --- | --- | --- |
| O-001 | Pasta `STT-Hub`, repo `Apethor/stt-hub`, branch `main`. | Aplicar o nome escolhido com identificadores convencionais. |
| O-002 | GitHub público. | Aplicar D-006, conforme instrução mais recente do usuário. |
| O-003 | Histórico novo, com commits focados. | Registrar a evolução do SaaS sem importar o histórico desktop. |
| O-004 | Revisão fixa da origem: `361788018f841637d09c3931f64e8b2819d16347`. | Manter referências rastreáveis mesmo se o desktop evoluir. |
| O-005 | Levar documentação selecionada e uma referência de prompt; adiar cópia de código. | Avaliar o código junto do recorte e da arquitetura escolhidos. |
| O-006 | Preservar aviso MIT da origem para o material derivado. | Registrar procedência sem escolher a licença de todo o SaaS. |
| O-007 | Manter a documentação como referência atual da sessão, independentemente da máquina usada. | Decisões ficam versionadas no GitHub, sem transcrever contexto casual da conversa. |

## Preferências e investigações

| Tema | Estado |
| --- | --- |
| S3 para áudios, screenshots e demais arquivos persistidos | Preferência explícita do usuário; validar arquitetura, buckets e permissões antes de implementar. |
| Estado de abas/grupos, preferências, índices e tarefas | Persistência e concorrência a desenhar; S3 não foi escolhido automaticamente como banco de toda a aplicação. |
| Whisper no navegador | Viabilidade documental identificada; inclusão e fallback dependem de investigação e testes alvo. Não portar o processo local Windows. |
| Login Entra ID | Investigar compatibilidade com Orquestra e ambiente de destino. Não está confirmado; é independente de Azure para IA. |
| Mock de login | Possibilidade para desenvolvimento local com usuários sintéticos; não substitui autorização real. |
| Go no backend | Opção para avaliação; não é decisão final. |
| Angular/Orquestra: versões, estrutura e componentes | Derivar dos artefatos/skills do ambiente de implementação; frontend já está escolhido. |
| Modelos, regiões e opções completas/Stream | Preservar referência AWS; validar capacidades atuais e acesso. Nenhuma chamada real foi feita nesta rodada. |
| Importação de áudio e ordem das fatias de implementação | Proposta herdada; a captura principal confirmada é pelo microfone. Upload primeiro não foi aprovado como sequência. |
| Conversa ao vivo, TTS, busca web, avaliação e limpeza avançada | Não definidos nesta rodada. Não inferir inclusão/exclusão apenas por não terem sido citados. |
| Backend, mecanismo de metadados e hospedagem | A escolher; não criar infraestrutura nesta etapa documental. |
| Limites, retenção, planos e cobrança | A definir antes de disponibilizar a terceiros. |
| Domínio, identidade visual e licença do código futuro | Pendentes. |

Acrescente decisões conforme forem tomadas, registrando o impacto e a
origem da escolha. A conclusão da preparação documental não valida as
hipóteses de produto nem encerra as decisões abertas.
