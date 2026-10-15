# STT Hub

Produto web/SaaS para **profissionais individuais que querem transcrever
áudio e trabalhar seus textos**.

O fluxo inicial proposto é enviar ou gravar áudio, revisar a transcrição,
preparar um texto por ação explícita e copiar/exportar o resultado.
O recorte funcional ainda será fechado com o usuário.

## Estado do projeto

Organização inicial criada em **15 de outubro de 2026**. Esta base contém
documentação, referência de processamento e preparação do repositório.
Ainda não há aplicação web, API, infraestrutura ou dependências instaladas.

- Nome do produto: **STT Hub**.
- Identificador do projeto: **stt-hub**.
- Pasta de trabalho: **STT-Hub**.
- Branch principal: **main**.
- GitHub: [Apethor/stt-hub](https://github.com/Apethor/stt-hub), público.
- Stack, providers, hospedagem e cobrança: decisões pendentes.

## Continuar o trabalho

Leia [AGENTS.md](AGENTS.md) e [HANDOFF.md](HANDOFF.md). O handoff indica o
próximo passo e inclui um texto para iniciar a próxima sessão.

| Documento | Finalidade |
| --- | --- |
| [Escopo](docs/ESCOPO.md) | Público, fluxo proposto, cortes e decisões pendentes. |
| [Decisões](docs/DECISOES.md) | O que foi confirmado e o que continua sendo proposta. |
| [Origem e reaproveitamento](docs/ORIGEM.md) | Projeto de referência, revisão fixa e mapa de módulos/testes. |
| [Contratos](docs/CONTRATOS.md) | Regras úteis para orientar a implementação das funcionalidades mantidas. |
| [Backlog](docs/BACKLOG.md) | Etapas próprias do STT Hub, separadas do desktop. |

## Em outra máquina

Clone o repositório e abra essa pasta como projeto:

```shell
git clone https://github.com/Apethor/stt-hub.git STT-Hub
cd STT-Hub
```

Comece por `AGENTS.md` e `HANDOFF.md`. Nesta etapa documental, Git é o único
requisito de ferramenta; runtime, dependências e comandos da aplicação serão
definidos quando a stack for escolhida. Ainda não existe um comando para
executar o SaaS.

As referências de código e contratos da origem estão em links do GitHub
em [docs/ORIGEM.md](docs/ORIGEM.md). Não é necessário ter o desktop instalado
ou sua pasta de fontes ao lado para retomar o planejamento e consultar a base.

## Relação com o desktop

O STT Hub parte de comportamentos e conhecimento do
[STT-widget](https://github.com/Apethor/STT-widget).
Os projetos possuem repositórios e evolução independentes. O desktop pode
ser retomado e desenvolvido em paralelo; este pivot não o encerra.

As referências apontam para uma revisão fixa no GitHub, sem depender de
uma pasta local da máquina original. Código Go, interface, assets e dados
do desktop não foram copiados em bloco.

## Licenças

A licença de distribuição do código futuro do STT Hub ainda será definida.
A visibilidade pública do repositório não define a licença do produto.
Material derivado do STT-widget conserva seu aviso MIT em
[licenses/STT-widget-MIT.txt](licenses/STT-widget-MIT.txt), com o alcance
documentado em [Origem](docs/ORIGEM.md#licenças-e-material-trazido).
