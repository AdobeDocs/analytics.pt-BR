---
description: Explica a nova estratégia de lançamento de recursos contínuos do Adobe Analytics
title: Versões de recursos do Adobe Analytics
exl-id: 1e403bef-4aab-4a9a-a358-62449ce801ff
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 92%

---

# Versões de recursos do Adobe Analytics

Historicamente, as versões de recursos do Adobe Analytics seguiam uma programação mensal fixa. Em abril de 2020, o Adobe Analytics migrou para um modelo de delivery contínuo que permite uma abordagem mais escalável e em fases para a implantação de recursos.

## Estratégia de lançamento

O [!UICONTROL Analysis Workspace] usa sinalizadores de recursos (também conhecidos como &quot;alternadores&quot;) para controlar a visibilidade de novos recursos, permitindo testes de escala controlados antes do lançamento completo. A estratégia de lançamento inclui as seguintes fases:

* **Liberação para produção (RTP)**: o código é lançado para produção, com a visibilidade do recurso desativada no Analysis Workspace. **Observação**: na RTP, o recurso pode estar disponível na API do Analytics 2.0.

* **Teste limitado**: uma versão em fases começa com testes feitos por usuários internos da Adobe. A versão é redimensionada de 0% a 100% de disponibilidade ao longo de dois meses. A implementação em fases acontece no nível da Organização da Experience Cloud, de modo que todos os usuários autorizados em uma organização recebem a mesma experiência.

* **Disponibilidade Geral (GA)**: o recurso está disponível para 100% das organizações da Experience Cloud autorizadas e a versão do recurso está concluída.

Com cada versão de recurso, a linha do tempo de RTP para GA pode variar. O objetivo é manter as versões curtas, para que, dentro de 2 meses do início do lançamento (RTP), um recurso tenha GA.

## Sinalizadores de recurso

Sinalizadores de recursos são usados para controlar a visibilidade de novos recursos durante o lançamento. A Adobe recomenda adicionar app.launch.darkly.com à [lista de permissões](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=pt-BR) do firewall para obter uma experiência ideal durante o lançamento. Logo após a GA ser atingida, o sinalizador é removido.

Você pode visualizar os sinalizadores de recursos ativos a qualquer momento em **Ajuda > Sobre o Workspace > Sinalizadores de recursos ativos**.

## Benefícios

As versões por fases permitem que a Adobe dimensione melhor o processo de implantação de software e garanta que os recursos sejam totalmente testados antes da Disponibilidade geral. Também permite que os recursos sejam lançados assim que estiverem disponíveis, em vez de seguirem uma janela de lançamento mensal fixa.

## Perguntas frequentes

| Pergunta | Resposta |
|---|---|
| Posso solicitar acesso antecipado a um recurso? | Não. O acesso antecipado não será concedido.<br>Se você quiser testar os conceitos iniciais do Analytics, recomendamos que você experimente o [Adobe Analytics Labs](https://experienceleague.adobe.com/docs/analytics/analyze/tech-previews/overview.html) para fornecer feedback sobre as inovações líderes do setor. |
| Essa estratégia de lançamento afeta meu acesso aos recursos? | Não. Depois que um recurso chegar à GA, você terá acesso ao recurso se ele fizer parte do seu pacote do Analytics.<br>Você pode visualizar detalhes do seu pacote do Analytics em  [!UICONTROL Admin]  >  [!UICONTROL Todos os administradores]  > Configurações  [!UICONTROL da empresa]  > Níveis de acesso a  [recursos](https://experienceleague.adobe.com/docs/analytics/admin/company-settings/feature-access-levels.html). |
