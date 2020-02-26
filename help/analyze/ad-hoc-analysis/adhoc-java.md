---
description: Instruções sobre como executar a Ad Hoc Analysis no Java 11.
title: Executar Ad Hoc Analysis no Java 11
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Executar Ad Hoc Analysis no Java 11

É necessário seguir etapas adicionais ao executar a Ad Hoc Analysis com o Java 11, em comparação com a execução com o Java 8.

## Pré-requisitos

Trabalhe com sua equipe de TI para garantir que o seguinte esteja em vigor:

* O Java 11 deve ser instalado, com o conjunto de variáveis do ambiente *JAVA_HOME*
* JavaFX deve ser instalado, com a variável de ambiente *PATH_TO_FX_SDK* apontada para o diretório do JavaFX SDK. Por exemplo, *PATH_TO_FX_SDK=/homedir/javafx-sdk-11.0.2* em um Mac ou *PATH_TO_FX_SDK=C:\Users\username\javafx-sdk-11.0.2* em um PC.

## Instalar a Ad Hoc Analysis para o Java 11

1. Acesse **[!UICONTROL Analytics > Ferramentas > Ad Hoc Analysis]**.
1. Clique em **[!UICONTROL Ad Hoc Analysis (Java 11)]**. Um arquivo zip será baixado.
1. Descompacte o arquivo baixado.
1. **Selecione o arquivo .bat (PC) ou .sh (Mac)**. Selecione o arquivo do data center apropriado, observando o número após &quot;sc&quot; no URL do Adobe Analytics. (3 = LON, 4 = SIN, 5 = PNW) Se você usa um PC, verifique se está executando um sistema operacional Windows de 32 bits ou 64 bits acessando &quot;Sobre o seu PC&quot;. Em seguida, selecione o arquivo .bat apropriado.
1. **Execute o arquivo selecionado**. Para PC: clique duas vezes no arquivo .bat. Para Mac: clique com o botão direito do mouse no arquivo .sh e selecione **[!UICONTROL Abrir com > Outros... > Utilidades > (Habilitar todos os aplicativos) > selecione Terminal > Abrir]**.
1. Faça logon na Ad Hoc Analysis.

> [!NOTE] Os métodos de autenticação Federated ID e Enterprise ID não são compatíveis com a versão Java 11 da Ad Hoc Analysis.

## Recursos não suportados na Ad Hoc Analysis (Java 11)

Há algumas limitações conhecidas na versão Java 11 compatível com a Ad Hoc Analysis:

* Os métodos de autenticação Federated ID e Enterprise ID não são suportados.
* Sistemas operacionais Linux não são suportados.
* Ao usar um Mac, não use o menu de aplicativos do Mac (incluindo *cmd + Q*). Isso pode fazer com que a Ad Hoc Analysis seja fechada sem aviso. Em vez disso, use o menu dentro da Ad Hoc Analysis.
* A visualização de Análise do site não é suportada ao executar a Ad Hoc Analysis no MacOS.

## Perguntas frequentes

**P: Eu recebo um erro “Não é possível encontrar \bin\javaw” (exemplo abaixo), o que devo fazer?**

![](/help/analyze/ad-hoc-analysis/assets/error-java.png)

R: Se você receber esse erro, trabalhe com sua equipe de TI para definir a variável de ambiente *JAVA_HOME*, que é necessária para executar a Ad Hoc Analysis no Java 11.
