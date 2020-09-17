---
title: Capturar termos de pesquisa interna
description: Use uma variável personalizada para capturar termos de pesquisa interna.
translation-type: tm+mt
source-git-commit: a94b8e090b9a3c75a57fd396cac8486bba2e5d79
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 2%

---


# Capturar termos de pesquisa interna

O relatórios de pesquisa interno é parte integrante de muitas organizações e não é uma dimensão predefinida com o Adobe Analytics. No entanto, com o mínimo de esforços de implementação, o relatórios de termos de pesquisa interna pode ser facilmente capturado.

## Pré-requisitos

[Validar uma implementação de desenvolvimento e publicar na produção](../launch/validate-publish-prod.md): Esta página supõe que você tenha uma implementação de trabalho básica e veja uma solicitação de imagem do Adobe Analytics no depurador de Adobe.

## Criar um eVar para acomodar a pesquisa interna

Siga o administrador [das variáveis de](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) conversão para criar um novo eVar dedicado à pesquisa interna. Dê ao eVar um nome facilmente reconhecível (como &quot;Termo de pesquisa interna&quot;) e registre o novo eVar no documento [de design da](../prepare/solution-design.md)Solução da sua organização.

## Determinar palavra-chave de pesquisa interna

A maioria das pesquisas internas usa sequências de caracteres de query para transmitir dados de palavras-chave entre páginas. Use a pesquisa interna do site e observe o URL na página de resultados da pesquisa:

`https://example.com/search.html?q=kittens`

Se a pesquisa interna do site não usar o URL, procure o termo de pesquisa em outros locais, como uma camada de dados ou um cookie. Trabalhe com a equipe de desenvolvimento do site se não tiver certeza de onde encontrar o termo de pesquisa interno.

## Atribuir o parâmetro da string de query a um elemento de dados

Follow [Map data layer objects to data elements](../launch/layer-to-elements.md). Ao selecionar o Tipo **[!UICONTROL de elemento de]** dados, selecione o parâmetro **[!UICONTROL da string de]** Query em vez da variável **** JavaScript. Coloque o parâmetro de string de query desejado (normalmente `q`) no campo de texto.

## Mapeie o elemento de dados para o eVar

Follow [Map Launch data elements to Analytics variables](../launch/elements-to-variable.md). Certifique-se de selecionar o mesmo eVar que você criou nas configurações do conjunto de relatórios.

## Start do processo de implantação Iniciar

Follow [Deploy an Analytics implementation to a development environment](../launch/deploy-dev.md). Depois de confirmar que está funcionando no ambiente dev, é possível [Validar uma implementação de desenvolvimento e publicar na produção](../launch/validate-publish-prod.md).

## Relatórios no Workspace

Dê à sua implementação algum tempo para coletar dados e, em seguida, você poderá fazer start usando a dimensão no Analysis Workspace.

1. Faça logon em [experiencecloud.adobe.com](https://experiencecloud.adobe.com) usando as credenciais da Adobe ID.
2. Se você não estiver conectado automaticamente ao Adobe Analytics, clique no ícone de grade de 9 na parte superior direita e selecione **[!UICONTROL Analytics]**.
3. Clique na guia **[!UICONTROL Espaço de trabalho]** e crie um novo projeto.
4. Localize o nome do eVar criado em Dimension e arraste-o para a área de trabalho.
