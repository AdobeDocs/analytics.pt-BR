---
description: Explica a nova estratégia de lançamento de recursos contínuos do Adobe Analytics
title: Versões de recursos do Adobe Analytics
translation-type: tm+mt
source-git-commit: dcca8559c9e730c9e04981d69068786878062561
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 4%

---


# Versões de recursos do Adobe Analytics

Historicamente, as versões de recursos do Adobe Analytics seguiam uma programação mensal fixa. A partir de abril de 2020, o Adobe Analytics foi para um modelo de delivery contínuo que permite uma abordagem mais escalonável e em fases para a implantação de recursos.

## Estratégia de lançamento

[!UICONTROL A área de trabalho] da Análise usa sinalizadores de recursos (também conhecidos como &quot;alternâncias&quot;) para controlar a visibilidade de novos recursos, permitindo testes de escala controlados antes do lançamento completo. Esta estratégia de lançamento inclui as seguintes fases:

* **Liberação para a Produção (RTP)**: O código é lançado para a produção, com a visibilidade do recurso desativada na área de trabalho da Análise. **Observação**: No RTP, o recurso pode estar disponível na API do Analytics 2.0.

* **Teste** limitado: Uma versão em fases começa com testes por usuários internos da Adobe. A versão é então redimensionada de 0% a 100% de disponibilidade ao longo de dois meses. A implantação em fases ocorre no nível da organização da Experience Cloud, de modo que todos os usuários autorizados em uma organização recebem a mesma experiência.

* **Disponibilidade Geral (GA)**: O recurso está disponível para 100% das organizações autorizadas da Experience Cloud e a versão do recurso está concluída.

Com cada versão de recurso, a linha do tempo de RTP para GA pode variar. O objetivo é manter as versões curtas, para que, dentro de 2 meses do start de lançamento (RTP), um recurso seja GA.

## Benefícios

As versões por fases permitem que a Adobe dimensione melhor o processo de implantação de software e garanta que os recursos sejam totalmente endurecidos antes da Disponibilidade Geral. Também permite que os recursos sejam lançados assim que estiverem disponíveis, em vez de aderirem a uma janela de lançamento mensal fixa.

## Perguntas frequentes

| Pergunta | Resposta |
|---|---|
| Posso solicitar acesso antecipado a um recurso? | Não. O acesso antecipado não será concedido.<br>Se você quiser testar os conceitos iniciais do Analytics, recomendamos que experimente o [Adobe Analytics Labs](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/tech-previews/overview.html) para fornecer feedback sobre as inovações líderes do setor. |
| Esta estratégia de lançamento afeta meu acesso aos recursos? | Não. Quando um recurso chegar ao GA, você terá acesso ao recurso se ele estiver incluído no pacote do Analytics.<br>Você pode visualização detalhes do pacote do Analytics em [!UICONTROL Admin] > Configurações [!UICONTROL de] Empresa > Níveis [de acesso a](https://docs.adobe.com/content/help/en/analytics/admin/company-settings/feature-access-levels.html)recursos. |