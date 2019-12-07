---
description: As variáveis de página populam diretamente um relatório, como pageName, Propriedades de lista, Variáveis de lista, entre outros.
keywords: Analytics Implementation
subtopic: Variables
title: Variáveis de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---



# javascriptVersion

A variável indica a versão do JavaScript suportada pelo navegador.


<!-- 

javascriptVersion.xml

 -->

Esta variável é preenchida depois do código de página e antes da execução de *`doPlugins`*.

> [!NOTE] Observação: esta variável só deve ser lida, e nunca definida.

Você pode ler esses valores e copiá-los em props/eVars, mas nunca deve alterá-los. Essa variável é introduzida com a versão H.11 do arquivo JavaScript.

| Parâmetro de consulta | Valor | Exemplo | Relatórios afetados |
|---|---|---|---|
| j | 1.0, 1.1, 1.2, … 1.7 | 1.7 | Tráfego &gt; Tecnologia &gt; Versão do JavaScript |

A Versão H.10 e superior do arquivo JavaScript detecta precisamente o arquivo até a versão 1.7 (a versão mais recente quando a H.10 foi lançada). Versões anteriores do arquivo JavaScript só detectavam até a versão 1.3
