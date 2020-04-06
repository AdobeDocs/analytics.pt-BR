---
description: Instruções sobre como executar a Ad Hoc Analysis no Java 11.
title: Executar Ad Hoc Analysis no Java 11
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Executar Ad Hoc Analysis no Java 11

É necessário seguir etapas adicionais ao executar a Análise ad hoc com o Java 11 em comparação com a execução com o Java 8.

## Pré-requisitos

Trabalhe com sua equipe de TI para garantir que o seguinte esteja em vigor:

* O Java 11 deve ser instalado, com o conjunto de variáveis do ambiente *JAVA_HOME*
* O JavaFX deve ser instalado, com a variável de ambiente *PATH_TO_FX_SDK* apontada para o diretório JavaFX SDK. Por exemplo, *PATH_TO_FX_SDK=/homedir/javafx-sdk-11.0.2* em um Mac, ou *PATH_TO_FX_SDK=C:\Users\username\javafx-sdk-11.0.2* em um PC.

## Instale a Análise ad hoc para Java 11

1. Vá para **[!UICONTROL Analytics > Tools > Ad Hoc Analysis]**.
1. Clique em **[!UICONTROL Ad Hoc Analysis (Java 11)]**. Isso baixa um arquivo zip.
1. Descompacte o arquivo baixado.
1. **Selecione o arquivo**.bat (PC) ou .sh (Mac). Selecione o arquivo do data center apropriado, observando o número após &quot;sc&quot; no URL do Adobe Analytics. (3 = LON, 4 = SIN, 5 = PNW) Se você usa um PC, verifique se está executando um sistema operacional Windows de 32 bits ou 64 bits acessando &quot;Sobre o seu PC&quot;. Em seguida, selecione o arquivo .bat apropriado.
1. **Execute o arquivo** selecionado. Para PC: Clique duas vezes no arquivo .bat. Para Mac: Clique com o botão direito do mouse no arquivo .sh e selecione **[!UICONTROL Open With > Other... > Utilities > (Enable all applications) > select Terminal > Open]**.
1. Faça logon na Ad Hoc Analysis.

>[!NOTE] Os métodos de autenticação Federated ID e Enterprise ID não são compatíveis com a versão Java 11 da Ad Hoc Analysis.

## Recursos não suportados na Ad Hoc Analysis (Java 11)

Há algumas limitações conhecidas na versão Java 11 compatível com a Ad Hoc Analysis:

* Os métodos de autenticação Federated &amp; Enterprise ID não são suportados.
* Os sistemas operacionais Linux não são suportados.
* Ao usar um Mac, não use o menu de aplicativos do Mac (incluindo *cmd + Q*). Isso pode fazer com que a Análise Ad Hoc seja fechada sem aviso prévio. Em vez disso, use o menu dentro da Análise ad hoc.
* A visualização da Análise do site não é suportada ao executar a Análise Ad Hoc no MacOS.

## Perguntas frequentes

**P: Eu recebo um erro “Não é possível encontrar \bin\javaw” (exemplo abaixo), o que devo fazer?**

![](/help/analyze/ad-hoc-analysis/assets/error-java.png)

R: Se você receber esse erro, trabalhe com sua equipe de TI para definir a variável de ambiente *JAVA_HOME*, que é necessária para executar a Ad Hoc Analysis no Java 11.
