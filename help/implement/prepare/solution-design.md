---
title: Criar um documento de design de solução
seo-title: Criar um documento de design de solução
description: Saiba o que é um documento de design da solução e como você pode usá-lo em sua organização.
seo-description: Saiba o que é um documento de design da solução e como você pode usá-lo em sua organização.
translation-type: tm+mt
source-git-commit: d195fb85711f58383577bf1d7b4da4078b909427

---


# Criar um documento de design de solução

Um documento de design de solução (também conhecido como referência de design de solução ou documento de requisitos de negócios) é basicamente o blueprint da sua implementação de análise. Ele define critérios identificados pelas partes interessadas em toda a organização e os traduz para variáveis dentro do Adobe Analytics. Sem um, as organizações têm um tempo difícil de coordenar as necessidades de relatórios e tendem a falhar na coleta de dados importantes.

## Pré-requisitos

[Validar sua implementação do Analytics e publicar na produção](../implement-with-launch/validate-publish-prod.md) - embora não seja necessário, a Adobe recomenda ter uma implementação básica em vigor para que dados críticos sejam coletados e implementados e implementados.

## Propriedade e localização do documento de design

* **Determine quem em sua organização será responsável por manter o documento de design da solução.** Esta função pode ser uma pessoa individual ou uma equipe. Assegure-se de que manter o design da solução seja preservado mesmo por alterações de função ou reestruturas de organização. É um documento ao vivo e deve ser mantido corretamente.
* **Determine onde o documento da solução ficará.** Não há um local melhor para que os documentos de design da solução residam, mas geralmente vivem em um local interno amplamente acessível. Exemplos incluem uma planilha compartilhada ou uma área de trabalho colaborativa como sharepoint ou uma wiki interna. Ele não precisa ser editável a todos, mas é vantajoso para aqueles que podem acessar o relatório para que seja possível visualizá-lo.

## Definir requisitos de negócios

Ao determinar quais dados coletar, é fácil dizer "tudo", no entanto, que pode tornar-se rapidamente impossível de administrar e fornecer menos valor do que coletar quantidades mais concisas de dados.

1. **Determine seus indicadores-chave de desempenho.** O que você deseja que os visitantes façam? A resposta a essa pergunta varia de acordo com a indústria e a vertical, e pode ser várias coisas. Exemplos incluem compras, registros ou cliques em anúncios.
1. **Descobrir os dados mais importantes para coletar.** Faça perguntas empresariais para as quais deseja obter respostas específicas. Respostas a essas perguntas fornecem informações sobre como melhorar o seu KPI.
1. **Faça essas perguntas e determine suas necessidades de rastreamento.** Agrupe-os em dimensões e métricas.
   * Dimensões são variáveis que contêm texto. Os exemplos incluiriam termo interno de pesquisa, categoria de produto ou o nome de uma área que um visitante clicou.
   * As métricas são eventos específicos que você deseja que um visitante faça - quando executam uma ação desejada, o número aumentará uma. Os exemplos incluem envio de um pedido, assinatura de um boletim informativo ou envio de uma resposta da pesquisa.
1. **Mapeie dimensões e métricas em uma página ou planilha.** Esta página ou tabela se torna o documento de design da solução. Algumas colunas ou pontos de marcador úteis para incluir:
   * Status da implementação: Planejado, ativo, inativo, problemas etc. Isso informa aos visualizadores do documento o status da variável, se ela foi implementada, ou se há problemas com a coleta de dados.
   * Nome da variável: Por exemplo, "Termos de pesquisa internos". Esse valor seria o que analistas veem ao trabalhar no Analytics.
   * A variável do Analytics mapeada para: A variável padrão ou personalizada do Analytics escolhida para atribuir valores. Normalmente, as dimensões caem em evars, enquanto as métricas se enquadram em eventos.
   * Lógica: Uma descrição de como a variável é definida e o que determina seu valor. Por exemplo, "Somente definido em páginas de pesquisa internas. Assume o valor do parâmetro da string de consulta q ".
   * Quaisquer outras observações que você deseja incluir pertencem à variável

## Recursos adicionais

Definir um documento de design de solução é um projeto bastante complexo, especialmente para organizações que não criaram um antes. Se for necessária mais assistência, a Adobe fornecerá consultoria especializada para ajudar a tornar sua organização compatível com o Adobe Analytics. Entre em contato com seu Gerente de contas se desejar codificar os serviços profissionais da Adobe. A [Technical pre-implementation questionnaire](assets/technical-pre-implementation-questionnaire.pdf) can be filled out so Adobe knows exactly how to help based on your organization's needs.

Também há vários parceiros da Adobe que se especializada em ajudar com a criação de um documento de design de solução, bem como a implementação do Adobe Analytics em seu site.

> [!NOTE] Embora os membros da comunidade do Analytics tenham localizado os seguintes links, eles não são da parte da Adobe. Considere essa observação ao visualizar seu conteúdo.

* [7 Etapas para configurar o Design de soluções da Web Analytics](https://resources.observepoint.com/blog/7-steps-solution-design-data-governance) por seguvepoint
* [Uma estrutura para processo de análise digital](https://analyticsdemystified.com/analytics-strategy/framework-digital-analytics-process/) pelo Analytics Demystified
* [A Referência de design da solução é, na verdade, a BFF](http://numericanalytics.com/why-a-simple-piece-of-documentation-is-the-key-to-analytics-success-the-solution-design-reference-is-actually-your-bff/) do Analytics
* [Como fazer o mapeamento de tags do Adobe Analytics por](http://www.anttikoski.fi/how-to-make-adobe-analytics-tagging-map-aka-solution-design-requirements-for-sitecatalyst-implementation/) Antti Koski
* [A importância do documento de design da solução](https://www.ebiquity.com/news-insights/analytics/the-importance-of-the-solution-design-document) por Ebiquity

## Próximas etapas

Implemente as variáveis no documento de design da solução.

* Introdução a evars: Saiba o que é uma evar, como funciona e como usá-la em sua implementação
* Introdução aos eventos: Saiba como é um evento bem-sucedido, como funciona e como usá-lo em sua implementação
