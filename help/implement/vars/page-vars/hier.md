---
title: hier
description: Implementar variáveis de hierarquia no Adobe Analytics.
feature: Variables
exl-id: 72bdab8f-a001-4ada-b5e2-453a8e3f24a6
source-git-commit: f435453f655caef89460de42ebecf489b021dc47
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 62%

---

# hier

>[!IMPORTANT]
>
>Essa variável foi removida e não é uma dimensão disponível no Analysis Workspace. A Adobe recomenda usar [eVars](evar.md) e classificações.

As variáveis de hierarquia são variáveis personalizadas que permitem visualizar a estrutura de um site. A Adobe oferece suporte a até 5 variáveis de hierarquia na sua implementação.

Essa variável é útil para sites com mais de três níveis na estrutura do site. Por exemplo, um site de mídia pode ter quatro níveis para a seção de Esportes: `Sports`, `Local Sports`, `Baseball` e `Team name`. Se alguém visitar a página Beisebol, as páginas Esportes, Esportes locais e Beisebol refletirão essa visita.

Antes de usar hierarquias na implementação, configure cada hierarquia nas configurações do conjunto de relatórios.

## Hierarquias usando o SDK da Web

As hierarquias são [mapeado para Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=pt-BR) nos campos XDM `_experience.analytics.customDimensions.hierarchies.hier1` para `_experience.analytics.customDimensions.hierarchies.hier5`.

## Hierarquias usando a extensão Adobe Analytics

Você pode definir hierarquias ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon em [Coleta de dados do Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Selecione Adobe Analytics na lista suspensa [!UICONTROL Extensão] e defina [!UICONTROL Tipo de ação] como [!UICONTROL Definir variáveis].
6. Localize a variável [!UICONTROL Hierarquia] seção.

Você pode definir um valor de hierarquia como uma string estática ou fazer referência a um elemento de dados. Também é possível definir o delimitador desejado. Verifique se o delimitador definido aqui corresponde ao conjunto de delimitadores nas configurações do Conjunto de relatórios.

## s.hier1 - s.hier5 no AppMeasurement e no editor de código personalizado da extensão do Analytics

Cada hierarquia é uma string que contém valores personalizados específicos para sua organização. O comprimento máximo delas é de 255 bytes; valores com mais de 255 bytes são truncados automaticamente quando enviados para a Adobe.

Verifique se nenhum dos nomes da sua seção inclui o delimitador. Por exemplo, se uma de suas seções for chamada `Coach Griffin, Jim`, escolha um delimitador diferente de vírgula. O limite total da variável é de 255 bytes. Os delimitadores podem consistir em vários caracteres, como `||` ou `/|\`, que têm menos probabilidade de aparecer em valores variáveis.

```js
s.hier1 = "Toys|Boys 6+|Legos|Super Block Tub";

s.hier3 = "Sports/Local Sports/Baseball";
```
