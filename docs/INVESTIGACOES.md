# Investigações antes da implementação

Atualizado em **15 de outubro de 2026**. Evidência documental não equivale
a teste no ambiente de destino. Esta rodada não instalou modelos, executou
inferência, autenticou tenant, testou hardware ou criou recursos cloud.

## HUB-013 — Whisper inteiramente no navegador

**Decisão de produto pendente:** investigar antes de incluir Whisper ou
aprová-lo como fallback. Uma SPA Angular pode hospedar o runtime/modelo no
cliente; isso não reutiliza diretamente o executável ou processo Windows.

Há duas rotas documentadas: o exemplo oficial
[stream.wasm do whisper.cpp](https://github.com/ggml-org/whisper.cpp/blob/master/examples/stream.wasm/README.md)
e a pipeline de ASR com Whisper no
[guia WebGPU do Transformers.js](https://huggingface.co/docs/transformers.js/guides/webgpu).
Elas demonstram possibilidade técnica, sem garantir qualidade, latência ou
consumo aceitável nos dispositivos do público alvo. O exemplo com modelo
em inglês não comprova qualidade para português.

O cliente precisa carregar runtime e modelo. Medir download, inicialização,
cache e memória; consultar [implantação do ONNX Runtime Web](https://onnxruntime.ai/docs/tutorials/web/deploy.html).
WASM/CPU e WebGPU têm requisitos distintos. Workers, multithreading e isolamento
da página exigem planejamento; o proxy Worker do ONNX não serve ao WebGPU.
Consultar [flags e sessões do runtime](https://onnxruntime.ai/docs/tutorials/web/env-flags-and-session-options.html).

O spike posterior deve usar modelos multilíngues e fixtures sintéticas ou
consentidas, comparar português/ruído/silêncio, tempo de transcrição e recursos
nos navegadores/dispositivos escolhidos. Cobrir gravação longa, cancelamento,
troca de documento, recarregamento, falha de GPU e conservação de pendências.
Definir os critérios de aceite antes de escolher uma rota.

Execução em servidor seria outra arquitetura, com computação e custos
próprios; não foi escolhida como substituto da investigação no cliente.
Fallback não pode ocultar falhas nem trocar de motor silenciosamente.

## HUB-008 — Login com Entra ID

**Investigar compatibilidade com Angular/Orquestra e o ambiente de destino.**
Entra ID para login permanece candidato mesmo com Azure excluído como
provider de IA. A documentação Microsoft cobre SPA com OIDC e authorization
code com PKCE; consultar o [fluxo oficial](https://learn.microsoft.com/en-us/entra/identity-platform/v2-oauth2-auth-code-flow)
e a [orientação de SPA/MSAL](https://learn.microsoft.com/en-us/entra/identity-platform/scenario-spa-overview).
Isso não comprova acesso ou compatibilidade com um tenant específico.

No ambiente de destino, obter o contrato de autenticação do padrão Orquestra
e verificar registro da aplicação, tipos de conta/tenant, redirects,
consentimento, escopos, renovação de sessão e validação no servidor.
Não publicar configurações internas, tokens ou dados de conta no repo público.

Mock é uma opção para desenvolvimento local com usuários sintéticos e dados
isolados. O serviço público precisa autenticação real e autorização de cada
aba, grupo, tarefa, áudio e screenshot no servidor. Escolher login alternativo
somente após a avaliação; nenhum provider alternativo foi escolhido aqui.

## HUB-014 — S3 e persistência

**Preferência do usuário:** S3 para arquivos, especialmente áudio e screenshots.
S3 armazena objetos; a documentação descreve buckets e controle de acesso
em [What is Amazon S3?](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html).
O repositório GitHub público não torna os dados dos usuários públicos.

Avaliar separadamente objetos de mídia e estado/indexação de abas, grupos,
preferências e tarefas. Não foi escolhido um banco de dados nem decidido que
toda a sessão será um único objeto JSON. Definir recuperação e concorrência
entre atualizações; se usar documentos no S3, estudar
[escritas condicionais](https://docs.aws.amazon.com/AmazonS3/latest/userguide/conditional-writes.html).

Na investigação prática, verificar conta/região, possibilidade de criar ou
usar buckets, permissões, acesso privado e integração com o servidor e o
Transcribe. Testar isolamento de dois usuários, leitura/escrita/exclusão,
cancelamento, vínculos de capturas e falhas de persistência com objetos
sintéticos. Nenhum bucket ou permissão foi criado nesta rodada.

Custos a levantar: armazenamento, operações e transferência, além do uso de
IA. Sem região, volume e retenção definidos, não há estimativa. Usar a
[tabela oficial de preços](https://aws.amazon.com/s3/pricing/) na análise.

## HUB-011 — Screenshots no navegador

Screenshots estão confirmadas; o mecanismo de aquisição e edição ainda
precisa de adaptação. O navegador controla seleção e permissão da superfície
compartilhada, conforme [getDisplayMedia](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getDisplayMedia).
A API fornece um fluxo que pode ser usado para obter uma imagem; isso não
acrescenta um modo de gravação de vídeo ao produto. Não prometer equivalência
com a sobreposição nativa antes de validar a experiência.

Testar permissões/cancelamento, seleção/recorte, editor, marcador temporal e
captura durante gravação contínua do microfone. O microfone tem permissão
própria, descrita em [getUserMedia](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia).
Não solicitar trilha de áudio do sistema. Upload/colar imagem como alternativa
de aquisição ainda não foi escolhido.

## Orquestra e fronteiras ainda abertas

Angular e Orquestra são decisões confirmadas. O contrato de componentes,
as versões e as skills do padrão serão obtidos no ambiente de destino.
Não inferir dependências a partir de bibliotecas públicas homônimas.
Organização funcional da origem é referência; layout e componentes devem
seguir esse padrão. Screenshots de referência visual não foram exigidas.

Backend, hospedagem, mecanismo de metadados e limites permanecem abertos.
Os providers cloud já estão escolhidos: Bedrock e Amazon Transcribe;
avaliar modelos/regiões/acesso no momento da integração, sem tratar os
identificadores históricos da origem como catálogo atual garantido.
