---
title: Motivo da desativação do rastreamento
description: Visualiza quais dados seriam excluídos se as Configurações de privacidade fossem ativadas.
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
TQID: https://experienceleague.adobe.com/mFYYrj4iBWBi87sErHnWTYXce3lUhV0pwUt63x3vfnY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: eddd9b14-83bd-4ff4-9072-54a4a484abb7id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 281
ht-degree: 11%

---

# Motivo da desativação do rastreamento

*Esta página se refere à [dimensão](overview.md) que permite ver o impacto potencial dos dados ao habilitar determinadas configurações do Conjunto de Relatórios. Não está relacionado ao [Serviço de Opt-in da Adobe Experience Cloud ID](https://experienceleague.adobe.com/pt-br/docs/id-service/using/implementation/opt-in-service/optin-overview).*

A dimensão &quot;Motivo da desativação do rastreamento&quot; atua como uma visualização dos dados que seriam excluídos se as Configurações de privacidade fossem ativadas. Essa dimensão é usada principalmente para determinar se sua implementação será afetada negativamente se você tiver ativado as [Configurações de privacidade](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html) nas Configurações do conjunto de relatórios.

As implementações típicas veem 1% ou menos do tráfego geral do conjunto de relatórios nessa dimensão se as Configurações de privacidade ainda não tiverem sido ativadas. Porcentagens maiores que 1% de todo o tráfego sugerem um possível problema de implementação que impede o AppMeasurement de definir cookies próprios.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações que ainda não ativaram as [Configurações de privacidade](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html). Se sua organização já tiver habilitado a configuração **[!UICONTROL Remover usuários que bloquearam todos os cookies]** para navegadores de desktop e móveis, esta dimensão não conterá dados.

## Itens de dimensão

Os itens de dimensão incluem `"Cookies disabled by Desktop Browser"` e `"Cookies disabled by Mobile Browser"`.

* **Cookies desabilitados pelo Navegador de Desktop**: o visitante bloqueou cookies usando um navegador de desktop e **[!UICONTROL Remover usuários que bloquearam todos os cookies em navegadores de desktop]** está desabilitado.
* **Cookies desabilitados pelo Navegador móvel**: o visitante bloqueou cookies com um navegador móvel e **[!UICONTROL Remover usuários que bloquearam todos os cookies em navegadores móveis]** está desabilitado.
