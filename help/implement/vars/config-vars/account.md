---
title: account
description: (Desativado) Determine o conjunto de relatórios para o qual os dados são enviados.
feature: Variables
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 38%

---

# account

>[!IMPORTANT]
>
>Essa variável foi removida. Use a função [`s.sa()`](../functions/sa-method.md) se a implementação exigir que modifique o destino do conjunto de relatórios.

Em versões anteriores do Adobe Analytics, a variável `account` determinava o conjunto de relatórios para o qual você deseja enviar dados. É necessária uma ID de conjunto de relatórios para enviar dados ao Adobe Analytics.

* Se você usar o SDK da Web, os conjuntos de relatórios estarão nas configurações de serviço do Adobe Analytics na sequência de dados para a qual o SDK da Web envia dados.
* Se você usar a extensão do Adobe Analytics, os conjuntos de relatórios ficarão na opção [!UICONTROL Gerenciamento de biblioteca] ao configurar a extensão do Adobe Analytics.
* Se você usar a função [`s_gi()`](../functions/s-gi.md) para instanciar um objeto de rastreamento do Analytics, as IDs do conjunto de relatórios já existem como um argumento obrigatório na função.
