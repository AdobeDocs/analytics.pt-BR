---
title: Motivo da desativação do rastreamento
description: Visualiza quais dados seriam excluídos se as Configurações de privacidade fossem ativadas.
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 7%

---

# Motivo da desativação do rastreamento

*Esta página se refere à [dimensão](overview.md) que permite ver o impacto potencial dos dados ao habilitar determinadas configurações do Conjunto de Relatórios. Não está relacionado ao [Serviço de Opt-in da Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=pt-BR).*

A dimensão &quot;Motivo da desativação do rastreamento&quot; atua como uma visualização dos dados que seriam excluídos se as Configurações de privacidade fossem ativadas. Essa dimensão é usada principalmente para determinar se sua implementação será afetada negativamente se você tiver ativado as [Configurações de privacidade](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html?lang=pt-BR) nas Configurações do conjunto de relatórios.

As implementações típicas veem 1% ou menos do tráfego geral do conjunto de relatórios nessa dimensão se as Configurações de privacidade ainda não tiverem sido ativadas. Porcentagens maiores que 1% de todo o tráfego sugerem um possível problema de implementação que impede o AppMeasurement de definir cookies próprios.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações que ainda não ativaram as [Configurações de privacidade](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html?lang=pt-BR). Se sua organização já tiver habilitado a configuração **[!UICONTROL Remover usuários que bloquearam todos os cookies]** para navegadores de desktop e móveis, esta dimensão não conterá dados.

## Itens de dimensão

Os itens de dimensão incluem `"Cookies disabled by Desktop Browser"` e `"Cookies disabled by Mobile Browser"`.

* **Cookies desabilitados pelo Navegador de Desktop**: o visitante bloqueou cookies usando um navegador de desktop e **[!UICONTROL Remover usuários que bloquearam todos os cookies em navegadores de desktop]** está desabilitado.
* **Cookies desabilitados pelo Navegador móvel**: o visitante bloqueou cookies com um navegador móvel e **[!UICONTROL Remover usuários que bloquearam todos os cookies em navegadores móveis]** está desabilitado.
