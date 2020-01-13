---
title: Criar um documento de design de solução
description: Saiba o que é um documento de design da solução e como usá-lo na sua empresa.
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Criar um documento de design de solução

Um documento de design da solução (também conhecido como referência de design da solução ou documento de requisitos comerciais) é, basicamente, o projeto da implementação do Analytics. Ele define os critérios identificados pelas partes interessadas em toda a empresa e traduz em variáveis no Adobe Analytics. Sem ele, as empresas têm dificuldades em coordenar as necessidades de relatórios e tendem a perder a coleta de dados importantes.

## Pré-requisitos

[Validar a implementação do Analytics e publicar na produção](../implement-with-launch/validate-publish-prod.md) - embora não seja diretamente necessária, a Adobe recomenda implantar uma implementação básica para que os dados críticos sejam coletados, enquanto os requisitos comerciais adicionais são estabelecidos e implementados.

## Propriedade e localização do documento de projeto

* **Determine quem na empresa será responsável pela manutenção do documento de design da solução.** Essa função pode ser de um funcionário ou uma equipe. Preserve a manutenção de design da solução independentemente das alterações de função ou reestruturações da empresa. Este é um documento dinâmico e deve ser devidamente mantido.
* **Determine onde ficará o documento da solução.** Não existe o melhor lugar para colocar os documentos de design da solução, mas normalmente eles ficam em um local interno amplamente acessível. Os exemplos incluem uma planilha compartilhada ou um espaço de trabalho colaborativo como o SharePoint ou um wiki interno. Não precisa ser editável para todos, mas é útil para quem podem acessar os relatórios para, pelo menos, poder visualizá-los.

## Definir requisitos comerciais

Ao determinar quais dados coletar, é fácil dizer "tudo", no entanto, isso pode se tornar rapidamente difícil de gerenciar e pode até fornecer menos valor do que coletar quantidades mais concisas de dados.

1. **Determine os indicadores-chave de desempenho.** O que você deseja que os visitantes façam? A resposta dessa pergunta varia de acordo com o setor e a vertical, podendo ser várias. Os exemplos incluem compras, registros ou cliques em anúncios.
1. **Descubra os dados mais importantes a coletar.** Faça perguntas comerciais para as quais você deseja obter respostas específicas. As respostas dessas perguntas fornecem informações sobre como melhorar os KPIs.
1. **Faça essas perguntas e determine quais são as necessidades de rastreamento.** Agrupe-as em dimensões e métricas.
   * Dimensões são variáveis que contêm texto. Os exemplos incluem o termo de pesquisa interna, a categoria do produto ou o nome de uma área em que um visitante clicou.
   * As métricas são eventos específicos que você deseja que um visitante faça - quando eles realizam uma ação desejada, o número aumenta em um. Os exemplos incluem enviar um pedido, assinar um boletim informativo ou enviar uma resposta de pesquisa.
1. **Mapeie dimensões e métricas em uma página ou planilha.** Esta página ou tabela torna-se, em última análise, o documento de design da solução. Algumas colunas ou marcadores úteis a incluir:
   * Status da implementação: planejado, ativo, inativo, problemas, etc. Isso informará os visualizadores do documento sobre o status da variável, se ela foi implementada ou se há problemas na coleta de dados.
   * Nome da variável: por exemplo, "Termos de pesquisa interna". Esse valor seria o que os analistas veem ao trabalhar no Analytics.
   * Variável do Analytics mapeada para: a qual variável padrão ou personalizada do Analytics você escolhe para atribuir valores. As dimensões normalmente se enquadram em eVars, enquanto as métricas se enquadram nos eventos.
   * Lógica: uma descrição de como a variável é definida e o que determina seu valor. Por exemplo, "Definido somente nas páginas de pesquisa internas. Obtém o valor do parâmetro da sequência de consulta q."
   * Quaisquer outras observações que você deseja incluir referentes à variável

## Recursos adicionais

A definição de um documento de design da solução é um projeto bastante complexo, especialmente para empresas que não criaram um antes. Se desejar assistência adicional, a Adobe fornece consultoria especializada para ajudar a colocar sua empresa em funcionamento com o Adobe Analytics. Entre em contato com o Gerente de contas, se desejar se inscrever nos serviços profissionais da Adobe. Um [questionário técnico de pré-implementação](assets/technical-pre-implementation-questionnaire.pdf) pode ser preenchido para que a Adobe saiba exatamente como ajudar, com base nas necessidades da empresa.

Também existem vários parceiros da Adobe especializados em ajudar na criação de um documento de design da solução, bem como na implementação do Adobe Analytics no site.

> [!NOTE] Embora os membros da comunidade do Analytics tenham considerado os seguintes links úteis, eles não são de propriedade da Adobe. Leve isso em consideração ao exibir o conteúdo.

* [ Etapas para configurar o Design da solução de análise da Web](https://resources.observepoint.com/blog/7-steps-solution-design-data-governance)/7- de ObservePoint
* [Uma estrutura para o Processo de análise digital](https://analyticsdemystified.com/analytics-strategy/framework-digital-analytics-process/) de Analytics Demystified
* [Na verdade, a Referência de design da solução é a sua BFF](http://numericanalytics.com/why-a-simple-piece-of-documentation-is-the-key-to-analytics-success-the-solution-design-reference-is-actually-your-bff/) de Numeric Analytics
* [Como elaborar o mapa de marcação do Adobe Analytics](http://www.anttikoski.fi/how-to-make-adobe-analytics-tagging-map-aka-solution-design-requirements-for-sitecatalyst-implementation/) de Antti Koski
* [A importância do Documento de design da solução](https://www.ebiquity.com/news-insights/analytics/the-importance-of-the-solution-design-document) de Ebiquity

## Próximas etapas

Implemente as variáveis no documento de design da solução.

* Introdução às eVars: saiba o que é uma eVar, como ela funciona e como usá-la na implementação
* Introdução aos eventos: saiba o que é um evento bem-sucedido, como ele funciona e como usá-lo na implementação
