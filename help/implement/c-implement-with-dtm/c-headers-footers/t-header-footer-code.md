---
description: Use o Dynamic Tag Management para adicionar o código de cabeçalho e rodapé que determina o carregamento do JavaScript e do conteúdo da página no site. Você deve instalar o código do cabeçalho e do rodapé em cada página do site, independentemente do método de hospedagem usado.
keywords: Implementação do Analytics, método de implementação, Dynamic Tag Management, dtm, código, código de página, código de cabeçalho, código de rodapé, código de incorporação, guia incorporar, incorporar
seo-description: Use o Dynamic Tag Management para adicionar o código de cabeçalho e rodapé que determina o carregamento do JavaScript e do conteúdo da página no site. Você deve instalar o código do cabeçalho e do rodapé em cada página do site, independentemente do método de hospedagem usado.
seo-title: Adicionar o código do cabeçalho e do rodapé
solution: Analytics
title: Adicionar o código do cabeçalho e do rodapé
topic: Desenvolvedor e implementação
uuid: 23d89ae0-340a-4b12-91d1-953b4613c98e
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

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
   >O código de incorporação da produção reflete somente os itens publicados nessa [propriedade](../../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123). No entanto, o código de incorporação para preparo reflete todos os itens na propriedade associada, independentemente do estado publicado ou não. Para testar itens não publicados no site de produção, habilite localmente o preparo no console seguindo as instruções em [Testar regras não publicadas para a hospedagem do Akamai](../../../implement/c-implement-with-dtm/c-rules/t-test-rules-akamai.md#task_B397167F9E9B4487957AD6CE2AD47259).

1. Copie o código do rodapé de produção e coloque-o na seção [!DNL BODY] do HTML do site.

   Coloque o código o mais próximo possível do [!DNL </body>] tag o mais possível.
1. Copie o código do cabeçalho e do rodapé de armazenamento temporário e repita as etapas acima no site de armazenamento temporário.

   >[!NOTE]
   >
   >A diferença entre os trechos de código de preparo e produção é a adição de [!DNL -staging] ao nome do arquivo na versão de preparo. O código do rodapé permanece o mesmo no armazenamento temporário e na produção.

