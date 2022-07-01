---
title: Motivo da desativação do rastreamento
description: Visualiza quais dados serão excluídos se você tiver ativado as Configurações de privacidade.
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
source-git-commit: b7209b914695423099266f5c507eaa34c2b98bc5
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 9%

---

# Motivo da desativação do rastreamento

*Esta página se refere à dimensão que permite observar o impacto potencial dos dados ao ativar determinadas configurações do Conjunto de relatórios. Não está relacionada ao [Serviço de Opt-in da Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=pt-BR).*

A dimensão &quot;Rastreamento do motivo de recusa&quot; atua como uma visualização dos dados que seriam excluídos se você ativasse as Configurações de privacidade. Essa dimensão é usada principalmente para determinar se a implementação será afetada negativamente se a ativação [Configurações de privacidade](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html) em Configurações do conjunto de relatórios.

As implementações típicas veem 1% ou menos do tráfego geral do conjunto de relatórios sob essa dimensão se as Configurações de privacidade ainda não tiverem sido habilitadas. Porcentagens acima de 1% de todo o tráfego sugerem um possível problema de implementação que impede o AppMeasurement de definir cookies próprios.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações que ainda não foram ativadas [Configurações de privacidade](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html). Se sua organização já tiver ativado a variável **[!UICONTROL Remover usuários que bloquearam todos os cookies]** para navegadores móveis e de desktop, essa dimensão não contém dados.

## Itens de dimensão

Os itens de dimensão incluem `"Cookies disabled by Desktop Browser"` e `"Cookies disabled by Mobile Browser"`.

* **Cookies desativados pelo navegador de desktop**: O visitante bloqueou cookies usando um navegador de desktop e **[!UICONTROL Remover usuários que bloquearam todos os cookies em navegadores para desktop]** está desativado.
* **Cookies desativados pelo navegador móvel**: O visitante bloqueou cookies usando um navegador móvel, e **[!UICONTROL Remover usuários que bloquearam todos os cookies em navegadores móveis]** está desativado.
