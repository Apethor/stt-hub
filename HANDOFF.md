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

Ainda não há aplicação, servidor, dependências instaladas, recursos cloud,
conta de cliente ou cobrança. Não foram copiados fontes Go, interface,
assets de desktop ou dados de usuário. O frontend já está escolhido:
**Angular com Orquestra**. Backend e infraestrutura ainda não estão definidos.

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
contexto. Para o scaffold executável, usar os artefatos/skills Angular/Orquestra
do ambiente de destino e definir backend/persistência. Nenhum ambiente de
uma máquina anterior é requisito implícito.

## Verificações da preparação

Na organização inicial, foram conferidos links locais, 28 caminhos na revisão
de origem e a existência desse commit no GitHub. O aviso MIT foi comparado
integralmente com o da origem. A revisão do conteúdo não encontrou nomes
internos antigos, caminhos pessoais nem padrões comuns de credenciais.

A `.gitignore` foi conferida com exemplos de segredos, dados e artefatos,
preservando a possibilidade de versionar exemplos de configuração, fixtures
e assets próprios. O GitHub é um repositório independente, sem vínculo de
fork. Essas verificações são da base documental, não de uma aplicação web.

O commit `fb7d934` foi clonado anonimamente do GitHub, sem a pasta da origem
ao lado: os 12 arquivos versionados e os 28 links internos foram conferidos,
com árvore limpa. A API pública confirmou o repositório público, habilitado
e com branch padrão `main`. O envio normal de Git também passou na conferência
`--dry-run`, usando o helper GitHub CLI configurado somente neste repo.

## Rodada de produto — 15 de outubro

**Confirmado:** microfone da própria pessoa pelo navegador; Bedrock e
Amazon Transcribe como opções de transcrição para comparar; processamento
de texto por Bedrock; screenshots; abas/grupos; Juntar/Mesclar; modo Teams
de redação e instruções; configurações e opções visuais. Manter a organização
funcional útil do desktop, implementando a apresentação em Angular/Orquestra.

**Fora desta versão:** modo Equipe, áudio do sistema, vídeo, conectores de IA
por API genérica/OpenAI/OpenRouter/Azure e botoneira/Painel de sons.
A retirada da botoneira foi a decisão final do usuário nesta rodada.
Teams de redação é independente do modo Equipe de captura.

**Trabalho novo confirmado:** bypass opcional do pré-processamento, vindo de
BL-099. A preferência ainda não existe na origem; manter tratamento habilitado
por padrão, persistir a opção e preservar originais. Não confundir filtros
com conversões de formato necessárias ao reconhecimento.

**Preferência:** S3 para arquivos persistidos. **Investigações:** Whisper
inteiramente no navegador, Entra ID para login, viabilidade/configuração de
S3 e persistência de metadados, aquisição/edição de screenshots no navegador.
Mock de login é uma possibilidade de desenvolvimento local, não uma decisão
de autenticação para uso público. Cada pessoa deve acessar somente seus dados.

Há pesquisa documental inicial em [docs/INVESTIGACOES.md](docs/INVESTIGACOES.md).
Whisper no navegador tem caminhos documentados por WASM/WebGPU; isso não
aprova fallback nem comprova qualidade/desempenho no hardware alvo.
Orquestra é o padrão indicado pelo usuário; suas skills/componentes serão
disponibilizados na máquina de implementação, sem pacote/versão presumidos.

A conferência documental desta rodada validou 32 links internos, três
âncoras e 38 caminhos na revisão da origem; o conteúdo foi revisado para
coerência de escopo, nomes e ausência de caminhos pessoais/credenciais.

## Próximo passo

Comece por [docs/ESCOPO.md](docs/ESCOPO.md) e
[docs/DECISOES.md](docs/DECISOES.md), que já registram frontend, direção AWS
e recorte. Não reabrir essas escolhas como se ainda estivessem indefinidas.

Obter os artefatos Angular/Orquestra no ambiente de destino e detalhar a
primeira fatia, backend, autenticação, persistência e limites. Go no backend
é uma opção de reaproveitamento, sem decisão final. Não é necessário trazer
todo o código antigo para começar. Outras funcionalidades não citadas nesta
rodada permanecem sem decisão, conforme o escopo.

Para avaliar o reaproveitamento, ler primeiro `internal/processing` e os
contratos de transcrição indicados no mapa. O serviço de transcrição ainda
depende de configuração, arquivos locais e recursos de plataforma. Não
assumir que copiá-lo já produz um serviço multiusuário.

O [backlog](docs/BACKLOG.md) separa funcionalidades confirmadas de investigações.
Não presumir upload como primeira fatia: a captura confirmada é pelo microfone.
Autenticação, persistência, acesso AWS e limites precisam ser resolvidos
antes de disponibilizar o serviço a outras pessoas.

## Texto para a próxima sessão

> Estamos iniciando o STT Hub, um SaaS para profissionais individuais
> transcreverem áudio e trabalharem seus textos. Leia AGENTS.md, HANDOFF.md
> e docs/DECISOES.md. O frontend será Angular/Orquestra, com as skills e os
> componentes deste ambiente. O recorte já inclui microfone, Bedrock e Amazon
> Transcribe, processamento, screenshots, abas/grupos, Juntar/Mesclar,
> Teams/instruções e visuais. Sem Equipe, áudio do sistema, vídeo, botoneira
> ou providers de IA por API/OpenRouter/Azure. Vamos detalhar a primeira fatia
> e o backend. S3 é preferência; Entra ID e Whisper no navegador são
> investigações. Consulte docs/INVESTIGACOES.md e o mapa de origem para
> preservar os contratos do STT-widget. O desktop pode continuar em paralelo.
> O GitHub é público e as referências à origem devem usar os links do GitHub
> em docs/ORIGEM.md, sem depender de arquivos de outra máquina.
