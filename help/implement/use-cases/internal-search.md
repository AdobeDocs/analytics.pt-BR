---
title: Capturar termos de pesquisa interna
description: Use uma variável personalizada para capturar termos de pesquisa interna.
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: ht
source-wordcount: '372'
ht-degree: 100%

---


# Capturar termos de pesquisa interna

O relatório de pesquisa interna é integral para muitas organizações e não é uma dimensão predefinida com o Adobe Analytics. No entanto, com o mínimo de esforços de implementação, os relatórios de termos de pesquisa interna podem ser facilmente capturados.

## Pré-requisitos

[Validar uma implementação de desenvolvimento e publicar na produção](../launch/validate-publish-prod.md): essa página supõe que você tenha uma implementação de trabalho básica e veja uma solicitação de imagem do Adobe Analytics no depurador da Adobe.

## Criar uma eVar para acomodar a pesquisa interna

Siga [Administrador de variáveis de conversão](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) para criar uma nova eVar dedicada à pesquisa interna. Dê à eVar um nome facilmente reconhecível (como &quot;Termo de pesquisa interna&quot;) e registre a nova eVar no [Documento de design da solução](../prepare/solution-design.md) de sua organização.

## Determinar palavra-chave de pesquisa interna

A maioria das pesquisas internas usa sequências de consulta para transmitir dados de palavra-chave entre páginas. Use a pesquisa interna de seu site e observe o URL na página de resultados da pesquisa:

`https://example.com/search.html?q=kittens`

Se a pesquisa interna do site não usar o URL, procure o termo de pesquisa em outros locais, como uma camada de dados ou cookie. Trabalhe com a equipe de desenvolvimento do site se não tiver certeza de onde encontrar um termo de pesquisa interna.

## Atribuir o parâmetro da sequência de consulta a um elemento de dados

Siga [Mapear objetos de camada de dados para elementos de dados](../launch/layer-to-elements.md). Ao selecionar o **[!UICONTROL Tipo de elemento de dados]**, selecione **[!UICONTROL Parâmetro da sequência de consulta]** em vez de **[!UICONTROL Variável JavaScript]**. Coloque o parâmetro da sequência de consulta desejada (normalmente `q`) no campo de texto.

## Mapear o elemento de dados na eVar

Siga [Mapear elementos de dados para variáveis do Analytics](../launch/elements-to-variable.md). Selecione a mesma eVar que você criou nas configurações do Conjunto de relatórios.

## Começar a implantar tags

Siga [Fazer uma implementação do Analytics em um ambiente de desenvolvimento](../launch/deploy-dev.md). Depois de confirmar que está trabalhando no ambiente de desenvolvimento, você pode [Validar uma implementação de desenvolvimento e publicar na produção](../launch/validate-publish-prod.md).

## Relatórios no Workspace

Dê algum tempo à implementação para coletar dados e, em seguida, comece a usar a dimensão no Analysis Workspace.

1. Faça logon em [experiencecloud.adobe.com](https://experiencecloud.adobe.com) usando as credenciais da Adobe ID.
2. Se você não estiver conectado automaticamente ao Adobe Analytics, clique no ícone de nove linhas de grade na parte superior direita e selecione **[!UICONTROL Analytics]**.
3. Clique na guia **[!UICONTROL Workspace]** e crie um novo projeto.
4. Localize o nome da eVar criado em Dimensões e arraste-o para a tela do espaço de trabalho.
