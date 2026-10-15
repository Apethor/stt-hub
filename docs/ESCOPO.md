# Escopo inicial — STT Hub

## Público e problema

**Confirmado:** profissionais individuais que querem transcrever áudio e
trabalhar textos. O STT Hub é um produto web/SaaS com identidade e
repositório próprios.

**Proposta de valor a validar:** transformar a fala da própria pessoa em
um texto pronto para usar, preservando a transcrição original para revisão.
Casos próximos da origem incluem mensagens profissionais,
organização de ideias e instruções personalizadas de escrita.

Ainda não foram definidos nicho profissional específico, disposição a
pagar, preço, franquia ou metas comerciais. Esses pontos não devem ser
tratados como validados.

## Fluxo de referência

1. Gravar pelo microfone da própria pessoa, com permissão do navegador.
2. Acompanhar a transcrição e eventuais partes pendentes.
3. Revisar e editar a transcrição.
4. Pedir explicitamente a preparação de um texto.
5. Revisar o resultado e copiar/exportar.
6. Encontrar novamente o documento e o áudio no histórico.

Screenshots podem acompanhar a gravação. Abas e grupos organizam os
documentos, com Juntar/Mesclar no grupo de origem. A interface preserva
essa organização funcional e usa Angular com o padrão Orquestra.
O detalhamento e a ordem de entrega ainda serão planejados.

## Recorte confirmado nesta rodada

| Funcionalidade | Decisão | Observação |
| --- | --- | --- |
| Microfone da própria pessoa | Manter | Captura pelo navegador; permissões e navegadores alvo a validar. |
| Transcrição e processamento de texto | Manter | AWS Bedrock e Amazon Transcribe para comparar; texto processado por Bedrock. |
| Teams de redação, Livre e instruções | Manter | Teams é uma instrução de escrita, não modo de captura Equipe. |
| Abas, grupos, Juntar e Mesclar | Manter | Isolamento por usuário, aba, grupo, tarefa e revisão. |
| Configurações e opções visuais | Manter | Organização funcional da origem com componentes Angular/Orquestra. |
| Screenshots | Manter | Aquisição/edição no navegador precisa de desenho; vínculo com áudio e aba deve ser preservado. |
| Bypass opcional do pré-processamento | Incluir | Levar BL-099 como trabalho novo; opção ainda não existe na origem. |
| Modo Equipe, áudio do sistema e colaboração de equipes | Fora desta versão | Grupos são organização privada dos documentos da pessoa. |
| Gravação de vídeo | Fora desta versão | Manter screenshot não cria modo de gravação de vídeo. |
| Painel de sons/botoneira | Fora desta versão | Correção final do usuário nesta rodada. |
| Providers de IA por API genérica, OpenAI/OpenRouter e Azure | Fora desta versão | A API interna do SaaS continua sendo uma possibilidade de arquitetura. |

## Preferências e pontos abertos

- S3 é a preferência para persistir arquivos, especialmente áudio e screenshots.
  Avaliar separadamente estado de abas/grupos, preferências, índices e tarefas.
- Whisper no navegador permanece em investigação antes de decidir sua inclusão
  ou uso como fallback. Não é equivalente a executar o binário desktop.
- Login com Entra ID permanece em investigação; mock é opção para desenvolvimento
  local. A exclusão de Azure como provider de IA não decide a autenticação.
- Backend, mecanismo de metadados, hospedagem, modelos/regiões e limites não
  estão fechados. Go continua como opção de reaproveitamento.
- Importação, exportação, histórico de áudio e reprodução são referências da
  proposta anterior; detalhar alcance e sequência sem presumir upload primeiro.
- Conversa ao vivo, TTS, busca web, avaliação e limpeza avançada não foram
  definidos nesta rodada. Outros itens do backlog desktop não foram selecionados.

O detalhamento das pendências e a evidência documental estão em
[INVESTIGACOES.md](INVESTIGACOES.md).

## Base de serviço a planejar

Contas e autorização, armazenamento privado, tarefas de transcrição,
cancelamento, recuperação, registro de consumo e limites por usuário.
Escolher uma política de retenção e exclusão para áudios e textos.

Cobrança automática pode entrar depois de uma validação inicial; antes de
abrir o serviço a terceiros, definir como o consumo será autorizado e
limitado. A política comercial e a licença do código futuro estão abertas.

Autenticação não é a mesma coisa que assinatura paga. Um protótipo local
com dados sintéticos pode preceder esses fluxos, desde que seja identificado
como protótipo e não exposto como SaaS multiusuário concluído.

## Decisões necessárias para começar a aplicação

- Artefatos e skills do padrão Angular/Orquestra no ambiente de destino.
- Backend e fronteiras de serviço, considerando reaproveitamento seletivo de Go.
- Modelos AWS, regiões e capacidades de transcrição completa/Stream a habilitar.
- Resultado das investigações de login, persistência e Whisper opcional.
- Ordem das fatias de implementação dentro do recorte confirmado.
- Limites de arquivo, duração, concorrência e consumo.
- Navegadores/dispositivos prioritários e política de dados.

Escolher hospedagem depois de entender essas necessidades. A preparação
do GitHub não cria infraestrutura nem significa que já existe um site.
