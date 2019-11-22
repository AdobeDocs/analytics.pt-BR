---
description: As variáveis de página populam diretamente um relatório, como pageName, Propriedades de lista, Variáveis de lista, entre outros.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variáveis de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---



# javaEnabled

A variável indica se Java estava ativado no navegador.


<!-- 

javaEnabled.xml

 -->

Esta variável é preenchida depois do código de página e antes da execução de doPlugins.

> [!NOTE] Observação: esta variável só deve ser lida, e nunca definida.

Você pode ler esses valores e copiá-los em props/eVars, mas nunca deve alterá-los. Essa variável é introduzida com a versão H.11 do arquivo JavaScript.

| Parâmetro de consulta | Valor | Exemplo | Relatórios afetados |
|---|---|---|---|
| v | Y ou N | S | Tráfego &gt; Tecnologia &gt; Java |
