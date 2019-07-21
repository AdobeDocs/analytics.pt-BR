---
description: Instruções sobre como executar a Análise ad hoc com Java 11.
seo-description: Instruções sobre como executar a Análise ad hoc com Java 11.
seo-title: Análise ad hoc e Java 11
title: Executar análise ad hoc com Java 11
translation-type: tm+mt
source-git-commit: 23bdb0c24416c376ec1df7b609a5794dbf8886f2

---


# Executar análise ad hoc com Java 11

É necessário seguir etapas adicionais ao executar a Ad Hoc Analysis com o Java 11, em comparação com a execução com o Java 8.

## Pré-requisitos

Trabalhe com sua equipe de TI para garantir que o seguinte esteja em vigor:

* Java 11 must be installed, with *JAVA_HOME* environment variable set
* JavaFX deve ser instalado, com a variável de ambiente *PATH_TO_FX_SDK* apontada para o diretório do JavaFX SDK. Por exemplo, *PATH_TO_FX_SDK=/homedir/javafx-sdk-11.0.2* em um Mac ou *PATH_TO_FX_SDK=C:\Users\username\javafx-sdk-11.0.2* em um PC.

## Instalar a Ad Hoc Analysis para o Java 11

1. Acesse **[!UICONTROL Analytics &gt; Ferramentas &gt; Ad Hoc Analysis]**.
1. Clique em **[!UICONTROL Ad Hoc Analysis (Java 11)]**. Um arquivo zip será baixado.
1. Descompacte o arquivo baixado.
1. **Selecione o arquivo .bat (PC) ou .sh (Mac)**. Selecione o arquivo do data center apropriado, observando o número após “sc” no URL do Adobe Analytics. (3 = LON, 4 = SIN, 5 = PNW) Se você usar um PC, verifique se você está executando um sistema operacional de 32 bits ou de 64 bits ao acessar «Sobre seu PC». Em seguida, selecione o arquivo .bat apropriado.
1. **Execute o arquivo selecionado**. Para PC: clique duas vezes no arquivo .bat. Para Mac: clique com o botão direito do mouse no arquivo .sh e selecione **[!UICONTROL Abrir com &gt; Outros...  &gt; Utilidades &gt; (Habilitar todos os aplicativos) &gt; selecione Terminal &gt; Abrir]**.
1. Faça logon na Ad Hoc Analysis.

>[!Note]
>
> Métodos de autenticação Federated e Enterprise ID não são compatíveis com a versão do Java 11 da Análise ad hoc.

## Recursos não suportados na Ad Hoc Analysis (Java 11)

Há algumas limitações conhecidas na versão do Java 11 compatível com a Análise ad hoc:

* Os métodos de autenticação Federated ID e Enterprise ID não são suportados.
* Sistemas operacionais Linux não são suportados.
* When using a Mac, do not use the Mac application menu (including *cmd + Q*). Isso pode fazer com que a Ad Hoc Analysis seja fechada sem aviso. Em vez disso, use o menu dentro da Ad Hoc Analysis.
* A visualização de Análise do site não é suportada ao executar a Ad Hoc Analysis no MacOS.

## Perguntas frequentes

**P: Eu recebi um erro «Não é possível encontrar\ bin\ javaw» (exemplo abaixo) - o que devo fazer?**

![](/help/analyze/ad-hoc-analysis/assets/error-java.png)

R: Se você receber esse erro, trabalhe com sua equipe de TI para definir a variável de ambiente *JAVA_HOME*, que é necessária para executar a Ad Hoc Analysis no Java 11.