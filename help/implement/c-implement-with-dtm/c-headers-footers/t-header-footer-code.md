---
description: Use o Dynamic Tag Management para adicionar o código de cabeçalho e rodapé que determina o carregamento do JavaScript e do conteúdo da página no site. Você deve instalar o código do cabeçalho e do rodapé em cada página do site, independentemente do método de hospedagem usado.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;code;page code;header code;footer code;embed code;embed tab;embed
title: Adicionar o código do cabeçalho e do rodapé
topic: Developer and implementation
uuid: 23d89ae0-340a-4b12-91d1-953b4613c98e
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Adicionar o código do cabeçalho e do rodapé

Use o Dynamic Tag Management para adicionar o código de cabeçalho e rodapé que determina o carregamento do JavaScript e do conteúdo da página no site. Você deve instalar o código do cabeçalho e do rodapé em cada página do site, independentemente do método de hospedagem usado.

Como o Dynamic Tag Management inclui um trecho de código no cabeçalho e no rodapé, você pode executar regras no início ou no final de uma página. Essa capacidade permite implementar ferramentas de teste e outras tecnologias, além de manter o controle sobre o rastreamento das páginas.

O Dynamic Tag Management cria códigos de incorporação para teste e produção, de modo que você possa testar as alterações em seu ambiente de testes antes de aplicá-las ao ambiente de produção.

>[!IMPORTANT]
>
>Para uma implementação bem-sucedida, é importante seguir as instruções à medida que elas são exibidas na seção de Ajuda. Você deve colocar o código do cabeçalho na seção `<head>` dos modelos do documento. Além disso, você deve colocar o código do rodapé antes de fechar a tag `</body>`. Colocar esses códigos de incorporação em qualquer outro lugar na marcação, usar métodos assíncronos para adicionar os códigos de incorporação ou quebrar os códigos de incorporação de qualquer maneira *não* são implementações compatíveis com o Dynamic Tag Management. Os códigos incorporados devem ser implementados exatamente como são fornecidos.
>
>Uma implementação não suportada criará resultados inesperados e impedirá que o Atendimento ao cliente e a Engenharia auxiliem durante a sua implementação.

1. Na interface do Dynamic Tag Management, abra a guia [!UICONTROL Incorporar] e selecione sua opção de hospedagem (por exemplo, Akamai) e alterne a opção para "Ativado".

   Resultado da etapa 1.  Copie o código do cabeçalho de produção fornecido na guia Incorporar do Dynamic Tag Management e coloque-o na seção [!DNL HEAD] do HTML do site.

   ![](assets/dtm-embed.png)

   Coloque o código o mais próximo possível do [!DNL <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">] tag o mais possível. Esse trecho de código deve ser colocado em cada página do site de produção ativo.

   >[!NOTE]
   >
   >O código de incorporação da produção reflete somente os itens publicados nessa [propriedade](/help/implement/c-implement-with-dtm/t-create-web-property.md). No entanto, o código de incorporação para preparo reflete todos os itens na propriedade associada, independentemente do estado publicado ou não. Para testar itens não publicados no site de produção, habilite localmente o preparo no console seguindo as instruções em [Testar regras não publicadas para a hospedagem do Akamai](/help/implement/c-implement-with-dtm/c-rules/t-test-rules-akamai.md).

1. Copie o código do rodapé de produção e coloque-o na seção [!DNL BODY] do HTML do site.

   Coloque o código o mais próximo possível do [!DNL </body>] tag o mais possível.
1. Copie o código do cabeçalho e do rodapé de armazenamento temporário e repita as etapas acima no site de armazenamento temporário.

   >[!NOTE]
   >
   >A diferença entre os trechos de código de preparo e produção é a adição de [!DNL -staging] ao nome do arquivo na versão de preparo. O código do rodapé permanece o mesmo no armazenamento temporário e na produção.

