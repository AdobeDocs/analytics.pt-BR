---
description: Explica a nova estratégia de lançamento de recursos contínuos do Adobe Analytics
title: Versões de recursos do Adobe Analytics
translation-type: ht
source-git-commit: dcca8559c9e730c9e04981d69068786878062561
workflow-type: ht
source-wordcount: '358'
ht-degree: 100%

---


# Versões de recursos do Adobe Analytics

Historicamente, as versões de recursos do Adobe Analytics seguiam uma programação mensal fixa. A partir de abril de 2020, a Adobe Analytics migrou para um modelo de delivery contínuo que permite uma abordagem mais escalável e em fases para a implantação de recursos.

## Estratégia de lançamento

O [!UICONTROL Analysis Workspace] usa sinalizadores de recursos (também conhecidos como &quot;alternadores&quot;) para controlar a visibilidade de novos recursos, permitindo testes de escala controlados antes do lançamento completo. A estratégia de lançamento inclui as seguintes fases:

* **Liberação para produção (RTP)**: o código é lançado para produção, com a visibilidade do recurso desativada no Analysis Workspace. **Observação**: na RTP, o recurso pode estar disponível na API do Analytics 2.0.

* **Teste limitado**: uma versão em fases começa com testes feitos por usuários internos da Adobe. A versão é redimensionada de 0% a 100% de disponibilidade ao longo de dois meses. A implementação em fases acontece no nível da Organização da Experience Cloud, de modo que todos os usuários autorizados em uma organização recebem a mesma experiência.

* **Disponibilidade Geral (GA)**: o recurso está disponível para 100% das organizações da Experience Cloud autorizadas e a versão do recurso está concluída.

Com cada versão de recurso, a linha do tempo de RTP para GA pode variar. O objetivo é manter as versões curtas, para que, dentro de 2 meses do início do lançamento (RTP), um recurso tenha GA.

## Benefícios

As versões por fases permitem que a Adobe dimensione melhor o processo de implantação de software e garanta que os recursos sejam totalmente testados antes da Disponibilidade geral. Também permite que os recursos sejam lançados assim que estiverem disponíveis, em vez de seguirem uma janela de lançamento mensal fixa.

## Perguntas frequentes

| Pergunta | Resposta |
|---|---|
| Posso solicitar acesso antecipado a um recurso? | Não. O acesso antecipado não será concedido.<br>Se você quiser testar os conceitos iniciais do Analytics, recomendamos que você experimente o [Adobe Analytics Labs](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/tech-previews/overview.html) para fornecer feedback sobre as inovações líderes do setor. |
| Essa estratégia de lançamento afeta meu acesso aos recursos? | Não. Depois que um recurso chegar à GA, você terá acesso ao recurso se ele fizer parte do seu pacote do Analytics.<br>Você pode ver os detalhes do seu pacote do Analytics em [!UICONTROL Admin] > [!UICONTROL Configurações da empresa] > [Níveis de acesso ao recurso](https://docs.adobe.com/content/help/pt-BR/analytics/admin/company-settings/feature-access-levels.html). |