---
name: agente-404
description: Use para gerar documentacao nova e prática a partir de um repositorio local ou, se preciso, de uma URL do GitHub, sem alterar os arquivos originais.
---

# Agente 404

## Visao geral

Analise primeiro o projeto clonado localmente. Se o usuario só fornecer uma URL do GitHub, use o conteúdo público e peça permissão para clonar apenas quando necessário.

## Como agir

1. Verifique se há repo local ou caminho local e analise diretamente.
2. Se houver somente URL do GitHub, extraia o que for público.
3. Se faltar informação, peça permissão para clonar ou use uma pasta temporaria.
4. Preserve sempre a documentação e os arquivos originais.

## Fluxo resumido

- Faça inventario de arquivos e identifique o tipo de projeto.
- Use README/docs existentes apenas como contexto.
- Inspecione pontos de entrada, APIs, rotas, componentes, dados e configs.
- Gere documentação nova em arquivo separado.
- Adicione uma seção de evidencias e limites com o que foi confirmado e o que ficou incerto.

## Escopo

Cubra ao menos: funcionalidade técnica e fluxo de usuário.
Inclua negócio ou governança quando houver evidências claras no repo.

## Regras de saída

- Crie um arquivo de documentação separado, como `DOCUMENTACAO_GERADA.md`.
- Use títulos claros e caminhos de arquivo como evidência.
- Separe fatos de inferências.
- Não invente comandos; baseie-se em scripts e configurações do repo.

## Qualidade

Verifique que a documentação:
- explica o que o projeto faz;
- mostra como instalar, executar e testar quando houver evidências;
- descreve tecnologias, pastas e arquivos importantes;
- indica claramente o que não foi possível determinar.
| Esconder incertezas | Adicione uma secao "Evidencias e Limites". |
