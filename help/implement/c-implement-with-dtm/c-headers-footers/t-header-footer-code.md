---
description: Use o Dynamic Tag Management para adicionar o código de cabeçalho e rodapé que determina o carregamento do JavaScript e do conteúdo da página no site. Você deve instalar o código do cabeçalho e do rodapé em cada página do site, independentemente do método de hospedagem usado.
keywords: Implementação do Analytics; método de implementação; gerenciamento dinâmico de tags; dtm; code; código de página; código do cabeçalho; código do rodapé; código incorporado; tabulação incorporada; embed
seo-description: Use o Dynamic Tag Management para adicionar o código de cabeçalho e rodapé que determina o carregamento do JavaScript e do conteúdo da página no site. Você deve instalar o código do cabeçalho e do rodapé em cada página do site, independentemente do método de hospedagem usado.
seo-title: Adicionar o código do cabeçalho e do rodapé
solution: Analytics
title: Adicionar o código do cabeçalho e do rodapé
topic: Desenvolvedor e implementação
uuid: 23 d 89 ae 0-340 a -4 b 12-91 d 1-953 b 4613 c 98 e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Adicionar o código do cabeçalho e do rodapé

Use o Dynamic Tag Management para adicionar o código de cabeçalho e rodapé que determina o carregamento do JavaScript e do conteúdo da página no site. Você deve instalar o código do cabeçalho e do rodapé em cada página do site, independentemente do método de hospedagem usado.

Como o Dynamic Tag Management inclui um trecho de código no cabeçalho e no rodapé, você pode executar regras no início ou no final de uma página. Essa capacidade permite implementar ferramentas de teste e outras tecnologias, além de manter o controle sobre o rastreamento das páginas.

O Dynamic Tag Management cria códigos de incorporação para teste e produção, de modo que você possa testar as alterações em seu ambiente de testes antes de aplicá-las ao ambiente de produção.

>[!IMPORTANT]
>
>Para uma implementação bem-sucedida, é importante seguir essas instruções conforme aparecem na Ajuda da Adobe. Specifically, you must place the header code in the `<head>` section of your document templates. Also, you must place the footer code just before the closing `</body>` tag. Colocar esses códigos de incorporação em qualquer outro lugar na marcação, usar métodos assíncronos para adicionar os códigos de incorporação ou quebrar os códigos de incorporação de qualquer maneira *não* são implementações compatíveis com o Dynamic Tag Management. Os códigos incorporados devem ser implementados exatamente como são fornecidos.
>
>Uma implementação não suportada criará resultados inesperados e impedirá que o Atendimento ao cliente e a Engenharia auxiliem durante a sua implementação.

1. Na interface do Dynamic Tag Management, abra a guia [!UICONTROL Incorporar] e selecione sua opção de hospedagem (por exemplo, Akamai) e alterne a opção para "Ativado".

   Resultado da etapa 1.  Copie o código do cabeçalho de produção fornecido na guia Incorporar do Dynamic Tag Management e coloque-o na seção [!DNL HEAD] do HTML do site.

   ![](assets/dtm-embed.png)

   Place the code as close to the [!DNL <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">] possível. Esse trecho de código deve ser colocado em cada página do site de produção ativo.

   >[!NOTE]
   >
   >Production embed code reflects only the published items in that [property](../../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123). No entanto, o código de incorporação para preparo reflete todos os itens na propriedade associada, independentemente do estado publicado ou não. Para testar itens não publicados no site de produção, habilite localmente o preparo no console seguindo as instruções em [Testar regras não publicadas para a hospedagem do Akamai](../../../implement/c-implement-with-dtm/c-rules/t-test-rules-akamai.md#task_B397167F9E9B4487957AD6CE2AD47259).

1. Copie o código do rodapé de produção e coloque-o na seção [!DNL BODY] do HTML do site.

   Place the code as close to the [!DNL </body>] possível.
1. Copie o código do cabeçalho e do rodapé de armazenamento temporário e repita as etapas acima no site de armazenamento temporário.

   >[!NOTE]
   >
   >The difference between production and staging code snippets is the addition of [!DNL -staging] to the filename in the staging version. O código do rodapé permanece o mesmo no armazenamento temporário e na produção.

