# Escopo inicial — STT Hub

## Público e problema

**Confirmado:** profissionais individuais que querem transcrever áudio e
trabalhar textos. O STT Hub é um produto web/SaaS com identidade e
repositório próprios.

**Proposta de valor a validar:** transformar uma gravação ou arquivo de
áudio em um texto pronto para usar, preservando a transcrição original
para revisão. Casos próximos da origem incluem mensagens profissionais,
organização de ideias e instruções personalizadas de escrita.

Ainda não foram definidos nicho profissional específico, disposição a
pagar, preço, franquia ou metas comerciais. Esses pontos não devem ser
tratados como validados.

## Fluxo proposto

1. Enviar um arquivo ou gravar pelo microfone.
2. Acompanhar a transcrição e eventuais partes pendentes.
3. Revisar e editar a transcrição.
4. Pedir explicitamente a preparação de um texto.
5. Revisar o resultado e copiar/exportar.
6. Encontrar novamente o documento e o áudio no histórico.

O fluxo é uma proposta inicial; a lista final de funcionalidades ainda
depende do recorte escolhido com o usuário.

## Recorte sugerido

| Funcionalidade | Proposta inicial | Observação |
| --- | --- | --- |
| Envio de arquivo | Primeira fatia executável | Definir duração, formatos e tamanho máximo. |
| Gravação de microfone | Primeira versão, após validar o envio | Definir navegadores, pausas, recuperação e limite de duração. |
| Transcrição revisável | Primeira fatia | Preservar original, edições e estados incompletos. |
| Processamento de texto | Primeira fatia | Ação explícita; começar com poucas opções. |
| Copiar resultado | Primeira fatia | Preservar texto e URLs exatos. |
| Exportação e histórico | Primeira versão proposta | Formatos, retenção e exclusão ainda pendentes. |
| Reprodução de áudio | Primeira versão proposta | Controles e relação com o texto a definir. |
| Abas, grupos e mesclagem | Adiar layout e regras avançadas | Não reproduzir a interface desktop por padrão. |
| Captura do áudio do sistema/reuniões | Adiar | Não prometer equivalência com a captura nativa. |
| Screenshots e vídeo | Adiar | Sem captura ou editor de imagens nesta primeira proposta. |
| Conversa ao vivo, TTS e Painel de sons | Adiar | Fluxos distintos do objetivo inicial. |
| Whisper na máquina do usuário | Adiar | Não pressupor processo local acessível pelo site. |
| Muitos providers/modelos e chaves do usuário | Adiar | Política de modelos, custos e credenciais ainda aberta. |
| Colaboração entre membros de uma equipe | Adiar | Público inicial é individual. |

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

- Qual caso de uso orienta a primeira entrega e quais linhas da tabela
  entram nela.
- Arquitetura e stack, considerando reaproveitamento seletivo de Go.
- Provider e modelos iniciais de transcrição e texto.
- Estratégia de autenticação, persistência e tarefas demoradas.
- Limites de arquivo, duração, concorrência e consumo.
- Navegadores/dispositivos prioritários e política de dados.

Escolher hospedagem depois de entender essas necessidades. A preparação
do GitHub não cria infraestrutura nem significa que já existe um site.
