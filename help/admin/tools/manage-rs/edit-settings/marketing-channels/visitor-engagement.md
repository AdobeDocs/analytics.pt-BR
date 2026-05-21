---
description: Saiba como especificar a expiração do engajamento do visitante nos Canais de marketing.
subtopic: Marketing channels
title: Expiração de canal de marketing
feature: Marketing Channels
exl-id: a9df659b-3b6a-4bdb-bd77-f4490d2b7c79
role: Admin
TQID: https://experienceleague.adobe.com/Og6HFSObiTqFg-HRqVzQWWnaGP0J--cJ9N8wvfuKsJc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 393
ht-degree: 82%

---

# Expiração de canal de marketing

>[!NOTE]
>
> Para obter informações gerais sobre canais de marketing, consulte [Introdução aos canais de marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md).
>
> Para maximizar a eficácia dos canais de marketing para a atribuição e o Customer Journey Analytics, publicamos algumas [práticas recomendadas revisadas](/help/components/c-marketing-channels/mchannel-best-practices.md).

**[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]** > **[!UICONTROL Editar configurações]** > **[!UICONTROL Canais de marketing]** > **[!UICONTROL Expiração de canal de marketing]**.

Saiba como especificar a expiração ou o período de engajamento do visitante para Canais de marketing.

O engajamento do visitante indica quanto tempo você deseja permitir que a atividade anterior do visitante em seu site seja atribuída ao canal de primeiro contato. A configuração padrão de expiração é de 30 dias.

Se o visitante usar o site com frequência, a janela de engajamento será aberta com ele. Eles devem estar inativos por 30 dias para que o período expire e os canais sejam redefinidos. Os canais de primeiro e último contato de um visitante são redefinidos após 30 dias de inatividade no navegador.

Exemplo:

* Dia 1: o usuário acessa o site em Exibir. Os canais de primeiro e último toque serão definidos como Exibir.
* Dia 2: o usuário acessa o site em Pesquisa natural. O primeiro toque permanece como Exibir e o Último toque é definido como Pesquisa natural.
* Dia 35: o usuário não visitou o site há 33 dias e retorna usando a guia que havia aberto em seu navegador. Presumindo uma janela de engajamento de 30 dias, a janela teria fechado e os cookies do Canal de marketing estariam expirados. O canal de primeiro e último toque será redefinido e definido como Atualização da sessão desde que o usuário tenha vindo de um URL interno.

## Configurações de expiração do canal de marketing

As configurações de expiração consistem no seguinte:

| Campo | Definição |
|--- |--- |
| Dias de Inatividade | O número de dias que devem decorrer antes que o envolvimento de primeiro contato de um visitante expire. O valor padrão é 30. |
| Nunca | O período de envolvimento do visitante não expira. |
| Redefinição de canal | Expira todos os períodos de engajamento do visitante.  Se precisar redefinir todos os dados de canal de marketing, você pode expirar todos os períodos de engajamento do visitante. Talvez seja necessário redefinir os dados se as regras de processamento tiverem sido configuradas incorretamente anteriormente. Todos os valores do canal de primeiro e último toque expirarão imediatamente e serão redefinidos quando os visitantes retornarem. |

## Definir a expiração do canal de marketing {#define-expiration}

Especifique o período de engajamento do visitante.

1. Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]**.
2. No [!UICONTROL Gerenciador do conjunto de relatórios], clique em **[!UICONTROL Editar configurações]** > **[!UICONTROL Canais de marketing]** > **[!UICONTROL Expiração do canal de marketing]**.

   ![](assets/mchannel_expiration.png)

3. Configure os campos do período de engajamento do visitante.
4. Clique em **[!UICONTROL Salvar]**.
