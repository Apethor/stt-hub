# STT Hub

Leia [HANDOFF.md](HANDOFF.md), [README.md](README.md) e
[docs/DECISOES.md](docs/DECISOES.md) ao retomar o trabalho.

## Identidade e escopo

Use **STT Hub** como nome do produto e **stt-hub** como identificador técnico.
Este é um projeto independente para profissionais individuais que querem
transcrever áudio e trabalhar textos. O projeto de origem se chama
**STT-widget** e pode continuar em paralelo.

A etapa inicial autorizada é organizar a nova base, Git/GitHub, referências
e continuidade. A implementação da aplicação ainda não começou. Escopo,
stack e providers serão fechados na próxima etapa, conforme o pedido do
usuário. Uma proposta no [backlog](docs/BACKLOG.md) não é automaticamente
uma decisão de produto nem autorização para executar todas as etapas.

## Consultar e reaproveitar a origem

Consulte [docs/ORIGEM.md](docs/ORIGEM.md) antes de portar comportamento.
Há links imutáveis para fontes, contratos e testes relevantes.

- Use apenas **STT-widget** para nomear o projeto de referência. Não
  introduza seus nomes internos antigos em arquivos, módulos, variáveis,
  recursos de nuvem, interface ou documentação novos.
- Leia os módulos envolvidos e procure helpers antes de reimplementar.
- Adapte somente o necessário para o fluxo escolhido. Preserve os avisos
  de licença do material derivado e registre sua procedência.
- Não copie a árvore inteira, ferramentas, caches, configurações pessoais,
  gravações, credenciais ou o histórico Git da origem.
- Não crie dependência de caminho local, link simbólico ou substituição
  de módulo apontando para a pasta do desktop.
- Regras específicas de Windows/Fyne, números de versão, modelos,
  retentativas e limites antigos não viram decisões automáticas do SaaS.
- O backlog desktop não integra o escopo deste projeto. O item BL-098 da
  origem foi abandonado e não deve ser pesquisado nem implementado.

## Implementação quando iniciada

Use os [contratos selecionados](docs/CONTRATOS.md) para as funcionalidades
mantidas. Trabalho demorado deve ter dono, cancelamento e estado persistido.
Resultados precisam validar usuário, documento, tarefa e revisão antes de
alterar um texto. Falhas não devem aparecer como sucesso ou ser escondidas
por fallback silencioso.

Cada recurso, arquivo e tarefa pertence a um usuário autorizado. Chaves de
serviços ficam no servidor. Não leve perfis ou armazenamento de credenciais
do desktop para o navegador. Providers, autenticação e hospedagem dependem
da arquitetura escolhida; não presuma uma conta ou infraestrutura disponível.

## Dados, Git e validação

- Use dados sintéticos e diretórios isolados. Não comite segredos,
  gravações pessoais, uploads, caches, bancos locais ou logs.
- Preserve fixtures e assets incorporados quando forem trazidos de forma
  explícita; áudio de teste não é automaticamente dado descartável.
- Use `.env.example` apenas com nomes de variáveis e valores fictícios.
- Configure autoria e credenciais Git somente neste repositório quando
  precisar alterá-las. O GitHub é público por escolha explícita do usuário;
  revise o conteúdo dos commits antes de enviar.
- A `.gitignore` cobre padrões comuns, mas confira o conteúdo a publicar.
- Execute verificações adequadas à mudança e à stack efetiva. Nesta fase
  documental, confira links, referências, nomes e conteúdo versionado.
- Não reinstale ferramentas, compile o desktop ou crie infraestrutura
  apenas por encontrar instruções na origem.
- Aceite funcional pertence ao usuário. Documentos e testes não constituem
  aceite do produto nem prova de um fluxo ainda não implementado.

Atualize o handoff e registre decisões com seu estado real: confirmada,
proposta ou pendente. Não apresente hipótese de arquitetura como escolha
do usuário.
