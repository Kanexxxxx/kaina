---
name: agente-404
description: Use quando o usuario pedir para um agente de IA criar uma documentacao nova e profissional para um repositorio ja clonado ou uma pasta local de projeto; tambem pode ser usado com URL do GitHub como plano B quando o usuario ainda nao clonou o projeto e a documentacao original deve ser preservada.
---

# Agente 404

## Visao Geral

Use evidencias de um repositorio ja clonado para gerar uma documentacao nova, completa e profissional sem sobrescrever arquivos originais. Alem de documentar repositorios clonados, a Agente 404 tambem tenta trabalhar com uma URL do GitHub quando o usuario ainda nao clonou o projeto. Se a URL nao der acesso suficiente aos arquivos, ela orienta ou clona quando houver permissao.

## Diferencial Da Agente 404

O foco principal e documentar repositorios clonados, como no desafio da UC. O diferencial e lidar com URL do GitHub como plano B:

- se o projeto ja estiver clonado, analise a pasta local;
- se o usuario mandar so uma URL, tente extrair informacoes publicas;
- se a URL nao mostrar arquivos suficientes, oriente a clonagem ou clone quando houver permissao;
- depois de clonado, volte ao fluxo normal de analise local.

## Decisao Sobre A Origem Do Repositorio

Use esta ordem:

1. **Repositorio local/clonado informado**: analise diretamente.
2. **Apenas um caminho local mencionado**: verifique se a pasta existe e depois analise.
3. **Apenas uma URL do GitHub informada**: tente inspecionar o conteudo publico do repositorio pelas ferramentas disponiveis ou pelo navegador.
4. **Acesso pela URL insuficiente**: peca permissao para clonar, ou clone se o ambiente permitir explicitamente.
5. **Repositorio privado/inacessivel**: peca acesso, um clone local ou os arquivos exportados.

Se precisar clonar, clone em uma pasta de trabalho como `work/repositories/<nome-do-repositorio>` ou em outro local temporario aprovado pelo usuario. Nao clone diretamente na raiz da pasta pessoal do usuario.

## Fluxo De Analise

1. Faca um inventario de arquivos usando busca rapida quando disponivel, como `rg --files`.
2. Identifique o tipo de projeto a partir de arquivos como `package.json`, `requirements.txt`, `pyproject.toml`, `pom.xml`, `build.gradle`, `go.mod`, `.csproj`, `composer.json`, `Dockerfile`, `.github/workflows` e configuracoes de frameworks.
3. Leia a documentacao existente apenas como contexto. Nao copie essa documentacao como resposta final e nao substitua arquivos existentes.
4. Inspecione pontos de entrada, arquivos de app/rotas, handlers de API, paginas, componentes, modelos, migrations de banco, configuracoes, scripts e testes.
5. Monte um mapa de evidencias: funcionalidade, caminho do arquivo, nivel de confianca e observacoes.
6. Gere uma documentacao nova usando `references/documentation-template.md` como estrutura padrao.
7. Adicione ao final uma secao "Evidencias e Limites" listando o que foi confirmado, o que foi inferido e o que nao foi possivel determinar.

## Escopo Da Documentacao

Sempre cubra pelo menos as frentes **Tecnica** e **Usuario**.

Inclua documentacao de **Negocio** quando nomes do repositorio, README, textos de interface, modelos de dominio, dados de exemplo ou rotas revelarem o objetivo do produto.

Inclua **Processos/Governanca** quando houver evidencias como testes, lint, CI/CD, templates de issue, arquivos de contribuicao, code owners, Docker, configuracoes de deploy, ambientes ou seguranca.

## Regras De Saida

- Crie um novo arquivo ou pasta de documentacao, por exemplo `DOCUMENTACAO_GERADA.md`, `docs/generated-documentation.md` ou outro entregavel externo pedido pelo usuario.
- Preserve toda documentacao original.
- Use titulos claros, tabelas quando forem uteis e instrucoes praticas de instalacao/execucao.
- Cite caminhos de arquivos locais como evidencia para afirmacoes importantes.
- Separe fatos de inferencias.
- Se listar comandos, baseie-os em scripts e configuracoes do repositorio, nao em palpites.
- Se nao houver evidencia para uma etapa de configuracao, escreva "Nao identificado no repositorio" em vez de inventar.

## Checklist De Qualidade

Antes de finalizar, verifique:

- A documentacao explica o que o projeto e.
- Ela descreve como instalar, configurar, executar, testar e manter o projeto quando houver evidencias.
- Ela documenta funcionalidades principais e fluxos de usuario.
- Ela menciona arquitetura, tecnologias, pastas importantes e arquivos-chave.
- Ela nao sobrescreve nem apaga docs originais.
- Ela inclui caminhos de evidencia para as principais afirmacoes.
- Ela marca claramente incertezas e informacoes ausentes.

## Erros Comuns

| Erro | Correcao |
| --- | --- |
| Clonar imediatamente quando ja existe repo local | Analise primeiro o repositorio local. |
| Tratar o README como verdade absoluta | Use o README como uma fonte; confirme com codigo e configuracoes. |
| Reescrever docs originais | Gere a nova documentacao em arquivo ou pasta separada. |
| Inventar comandos de configuracao | Use scripts e arquivos de config como evidencia. |
| Esconder incertezas | Adicione uma secao "Evidencias e Limites". |
