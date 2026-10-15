# Origem e reaproveitamento

## Referência fixa

- Projeto: **STT-widget**, aplicativo desktop Windows em Go/Fyne.
- Repositório: [Apethor/STT-widget](https://github.com/Apethor/STT-widget).
- Revisão: [`361788018f841637d09c3931f64e8b2819d16347`](https://github.com/Apethor/STT-widget/tree/361788018f841637d09c3931f64e8b2819d16347).
- Consulta inicial: **15 de outubro de 2026**.

Os links deste documento usam essa revisão, não a branch em movimento.
O repositório de origem pode continuar evoluindo independentemente.
Este mapa não exige uma pasta local específica nem acesso à conversa anterior.
Todas as referências à origem usam URLs do GitHub. Links relativos apontam
somente para documentos e referências versionados no próprio STT Hub.

## O que já foi trazido

Documentação nova de escopo, decisões, continuidade e contratos selecionados,
mais uma [referência de prompt](../references/prompts/mensagem-profissional.md).
As regras foram resumidas para orientar a avaliação do SaaS, sem copiar
configurações ou a interface desktop.

Nenhum pacote Go, ferramenta, dependência, binário, ícone, áudio, configuração,
credencial ou histórico de usuário foi importado. Os nomes internos antigos
da origem não são identificadores deste projeto.

## Mapa de consulta e reaproveitamento

| Área na origem | O que consultar | Tratamento no STT Hub |
| --- | --- | --- |
| [`internal/processing`](https://github.com/Apethor/STT-widget/tree/361788018f841637d09c3931f64e8b2819d16347/internal/processing) | Prompts, instruções, pedidos, histórico e validação. | Candidato inicial a adaptação; separar política de produto e catálogo de modelos. |
| [`internal/transcript`](https://github.com/Apethor/STT-widget/tree/361788018f841637d09c3931f64e8b2819d16347/internal/transcript) | Partes, cobertura, progresso, retomada, cancelamento, cache e exportações. | Reaproveitar regras e algoritmos; adaptar estado, isolamento e persistência. |
| [`internal/audio`](https://github.com/Apethor/STT-widget/tree/361788018f841637d09c3931f64e8b2819d16347/internal/audio) | Decodificação, divisão e preparação de áudio. | Avaliar para execução no servidor; ferramentas e limites serão próprios. |
| [`internal/api`](https://github.com/Apethor/STT-widget/tree/361788018f841637d09c3931f64e8b2819d16347/internal/api) e [`internal/apiconfig`](https://github.com/Apethor/STT-widget/tree/361788018f841637d09c3931f64e8b2819d16347/internal/apiconfig) | Adaptadores HTTP, validação e opções independentes de texto/áudio. | Consultar se os providers forem escolhidos; substituir a origem das credenciais. |
| [`internal/cloud`](https://github.com/Apethor/STT-widget/tree/361788018f841637d09c3931f64e8b2819d16347/internal/cloud) | Adaptadores AWS e processamento cloud. | Condicional à escolha de provider; autenticação desktop não é arquitetura do SaaS. |
| [`internal/config`](https://github.com/Apethor/STT-widget/tree/361788018f841637d09c3931f64e8b2819d16347/internal/config) e [`internal/store`](https://github.com/Apethor/STT-widget/tree/361788018f841637d09c3931f64e8b2819d16347/internal/store) | Persistência local e validações atuais. | Referência de comportamento; não copiar como banco multiusuário. |
| [`internal/live`](https://github.com/Apethor/STT-widget/tree/361788018f841637d09c3931f64e8b2819d16347/internal/live) | Ordenação temporal e preservação de trechos. | Consultar somente se o recorte exigir linha do tempo; não importar screenshots/trilhas por padrão. |
| [`internal/desktop`](https://github.com/Apethor/STT-widget/tree/361788018f841637d09c3931f64e8b2819d16347/internal/desktop) | Orquestração dos editores e prevenção de resultados atrasados. | Usar como evidência de regras; desenhar a interface web e seus estados separadamente. |
| [`internal/recorder`](https://github.com/Apethor/STT-widget/tree/361788018f841637d09c3931f64e8b2819d16347/internal/recorder), [`internal/playback`](https://github.com/Apethor/STT-widget/tree/361788018f841637d09c3931f64e8b2819d16347/internal/playback), [`internal/platform`](https://github.com/Apethor/STT-widget/tree/361788018f841637d09c3931f64e8b2819d16347/internal/platform) e [`internal/secrets`](https://github.com/Apethor/STT-widget/tree/361788018f841637d09c3931f64e8b2819d16347/internal/secrets) | Contratos nativos e de segurança. | Não portar implementação Windows para o navegador; redesenhar captura, reprodução e segredos. |
| [`tests/fixtures`](https://github.com/Apethor/STT-widget/tree/361788018f841637d09c3931f64e8b2819d16347/tests/fixtures) | Áudios sintéticos e suas instruções de geração. | Trazer somente fixtures necessárias, com procedência e licenças. |

O [serviço compartilhado](https://github.com/Apethor/STT-widget/blob/361788018f841637d09c3931f64e8b2819d16347/internal/transcript/service.go)
já é separado da interface, mas importa configuração, armazenamento e
plataforma. A interface `Transcriber` e os resultados por partes em
[`types.go`](https://github.com/Apethor/STT-widget/blob/361788018f841637d09c3931f64e8b2819d16347/internal/transcript/types.go)
são referências para fronteiras de serviço; não constituem um contrato
HTTP nem uma implementação pronta para múltiplos usuários.

## Documentos funcionais prioritários

| Referência | Uso |
| --- | --- |
| [Recuperação de transcrição](https://github.com/Apethor/STT-widget/blob/361788018f841637d09c3931f64e8b2819d16347/docs/RETENTATIVAS-TRANSCRICAO.md) | Retomada, falhas de escrita, resultados parciais e cancelamento. |
| [Processamento de texto](https://github.com/Apethor/STT-widget/blob/361788018f841637d09c3931f64e8b2819d16347/docs/PROCESSAMENTO-TEXTO.md) | Ação explícita, preservação de edições, instruções e contexto. |
| [Reprodução e histórico](https://github.com/Apethor/STT-widget/blob/361788018f841637d09c3931f64e8b2819d16347/docs/REPRODUCAO-AUDIO.md) | Independência de reprodução, histórico e preservação de originais. |
| [APIs e providers](https://github.com/Apethor/STT-widget/blob/361788018f841637d09c3931f64e8b2819d16347/docs/APIS-PROVIDERS.md) | Separação de opções de texto/áudio e cuidados com credenciais. |
| [Links em resultados](https://github.com/Apethor/STT-widget/blob/361788018f841637d09c3931f64e8b2819d16347/docs/LINKS-RESULTADO.md) | Apresentação não pode mudar texto e URLs ao copiar/exportar. |

Detalhes de janelas, atalhos, tamanhos, instalação e caminhos Windows não
precisam acompanhar os contratos selecionados.

## Testes que ajudam a preservar comportamento

| Arquivo na revisão de referência | Exemplos úteis |
| --- | --- |
| [`internal/transcript/retry_test.go`](https://github.com/Apethor/STT-widget/blob/361788018f841637d09c3931f64e8b2819d16347/internal/transcript/retry_test.go) | Retomar só partes pendentes, cancelar durante espera e impedir novos envios. |
| [`internal/transcript/recovery_test.go`](https://github.com/Apethor/STT-widget/blob/361788018f841637d09c3931f64e8b2819d16347/internal/transcript/recovery_test.go) | Falha de cache não conta como conclusão; partes aceitas e textos parciais permanecem. |
| [`internal/transcript/retranscription_test.go`](https://github.com/Apethor/STT-widget/blob/361788018f841637d09c3931f64e8b2819d16347/internal/transcript/retranscription_test.go) | Retranscrição tem tentativa independente e retomada própria. |
| [`internal/processing/conversation_test.go`](https://github.com/Apethor/STT-widget/blob/361788018f841637d09c3931f64e8b2819d16347/internal/processing/conversation_test.go) | Validar histórico e limites sem alterar o texto exato do pedido. |

Os testes da origem orientam cenários; não validam automaticamente a
implementação web. Ao portar uma função, registrar revisão/arquivo,
dependências substituídas e quais cenários continuam aplicáveis.

## Licenças e material trazido

O STT-widget distribui seu código e documentação originais sob MIT,
Copyright (c) 2026 Apethor. O aviso completo está preservado em
[licenses/STT-widget-MIT.txt](../licenses/STT-widget-MIT.txt).

Os contratos resumidos neste repositório e a referência de prompt foram
adaptados de documentação e código dessa revisão. O aviso acima acompanha
esse material. Isso não define a licença do código futuro do STT Hub.

Assets e dependências de terceiros não foram trazidos. Antes de importar
qualquer um, consultar [THIRD-PARTY.md da origem](https://github.com/Apethor/STT-widget/blob/361788018f841637d09c3931f64e8b2819d16347/docs/THIRD-PARTY.md)
e os avisos específicos do arquivo/componente.
