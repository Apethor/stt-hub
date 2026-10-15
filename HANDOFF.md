# Handoff — STT Hub

Atualizado em **15 de outubro de 2026**.

## Pedido e decisões confirmadas

O usuário iniciou um pivot para web/SaaS voltado a **profissionais
individuais que querem transcrever áudio e trabalhar textos**. Escolheu o
nome **STT Hub** e autorizou a organização inicial em pasta/repositório
próprios, com contexto suficiente para continuar em outra sessão.
Na mesma preparação, pediu explicitamente GitHub **público** e continuidade
em outra máquina, consultando a origem por URLs do GitHub, sem caminho local.

O projeto desktop **STT-widget** pode ser retomado e desenvolvido em
paralelo. O SaaS não o substitui obrigatoriamente. O nome do produto novo
deve ser usado desde o início, inclusive nos identificadores que forem
criados; a origem é referenciada como STT-widget.

## Estado desta base

- Pasta irmã independente chamada `STT-Hub`.
- Git próprio, branch `main`, autoria pública com alias e e-mail `noreply`
  configurados somente neste repositório.
- GitHub: [Apethor/stt-hub](https://github.com/Apethor/stt-hub), público por
  escolha explícita do usuário, substituindo a proposta inicial privada.
- Documentação de escopo, decisões, contratos, origem e backlog próprios.
- Uma referência de prompt de redação, adaptada da origem e identificada
  como referência, sem integração com serviço externo.
- Aviso MIT preservado para o material derivado do STT-widget.

Ainda não há aplicação, framework escolhido, servidor, dependências
instaladas, recursos cloud, conta de cliente ou cobrança. Não foram
copiados fontes Go, interface, assets de desktop ou dados de usuário.

A revisão de referência do desktop é
`361788018f841637d09c3931f64e8b2819d16347`. Os links de
[docs/ORIGEM.md](docs/ORIGEM.md) funcionam sem depender da pasta local da
sessão anterior. Consulte `git log` para o histórico desta nova base.

## Retomar em outra máquina

Siga os comandos de clone do [README](README.md#em-outra-máquina) e abra a
pasta clonada. Todos os documentos e o prompt de referência estão versionados.
As referências ao código do desktop usam URLs do GitHub na revisão fixada;
não é preciso ter a pasta original, suas ferramentas ou dados pessoais.

O scaffold preparado nesta etapa é a estrutura do repositório e de seu
contexto. O scaffold executável de frontend/backend fica para a escolha de
stack. Nenhum ambiente de uma máquina anterior é requisito implícito.

## Verificações da preparação

Foram conferidos links locais, 28 caminhos de arquivos/diretórios na revisão
de origem e a existência desse commit no GitHub. O aviso MIT foi comparado
integralmente com o da origem. A revisão do conteúdo não encontrou nomes
internos antigos, caminhos pessoais nem padrões comuns de credenciais.

A `.gitignore` foi conferida com exemplos de segredos, dados e artefatos,
preservando a possibilidade de versionar exemplos de configuração, fixtures
e assets próprios. O GitHub é um repositório independente, sem vínculo de
fork. Essas verificações são da base documental, não de uma aplicação web.

## Próximo passo

Comece por [docs/ESCOPO.md](docs/ESCOPO.md) e
[docs/DECISOES.md](docs/DECISOES.md). O fluxo proposto é enviar ou gravar
áudio, transcrever, revisar, preparar um texto e copiar/exportar.

Antes do scaffold da aplicação, fechar com o usuário o recorte da primeira
entrega e a stack. Go no backend é uma opção de reaproveitamento, ainda
sem decisão final. Uma interface web nova será necessária se esse caminho
for escolhido. Não é necessário trazer todo o código antigo para começar.

Para avaliar o reaproveitamento, ler primeiro `internal/processing` e os
contratos de transcrição indicados no mapa. O serviço de transcrição ainda
depende de configuração, arquivos locais e recursos de plataforma. Não
assumir que copiá-lo já produz um serviço multiusuário.

O [backlog](docs/BACKLOG.md) propõe como primeira fatia executável o envio
de um arquivo, transcrição, revisão, processamento explícito e cópia.
Providers reais, autenticação, persistência e limites precisam de decisões
antes de disponibilizar o serviço a outras pessoas.

## Texto para a próxima sessão

> Estamos iniciando o STT Hub, um SaaS para profissionais individuais
> transcreverem áudio e trabalharem seus textos. Leia AGENTS.md, HANDOFF.md
> e docs/DECISOES.md. A organização inicial e o Git já foram preparados;
> a aplicação ainda não foi scaffoldada. Quero fechar o escopo da primeira
> entrega e escolher a stack, consultando o mapa de origem para aproveitar
> regras, prompts e código úteis do STT-widget. O desktop pode continuar
> em paralelo. Use STT Hub como identidade do projeto novo. Distinga
> decisões confirmadas de propostas antes de iniciar a implementação.
> O GitHub é público e as referências à origem devem usar os links do GitHub
> em docs/ORIGEM.md, sem depender de arquivos de outra máquina.
