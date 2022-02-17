---
description: Saiba como especificar a expiração do engajamento do visitante nos Canais de marketing.
subtopic: Marketing channels
title: Expiração de canal de marketing
feature: Marketing Channels
exl-id: a9df659b-3b6a-4bdb-bd77-f4490d2b7c79
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 100%

---

# Expiração de canal de marketing

>[!NOTE]
>
>Para maximizar a eficiência dos Canais de marketing para o Attribution IQ e o Customer Journey Analytics, publicamos algumas [práticas recomendadas revisadas](/help/components/c-marketing-channels/mchannel-best-practices.md).

Saiba como especificar a expiração ou o período de engajamento do visitante para Canais de marketing.

O engajamento do visitante indica quanto tempo você deseja permitir que a atividade anterior do visitante em seu site seja atribuída ao canal de primeiro contato. A configuração padrão de expiração é de 30 dias.

Se o visitante usar o site com frequência, a janela de engajamento será aberta com ele. Eles devem estar inativos por 30 dias para que o período expire e os canais sejam redefinidos. Os canais de primeiro e último contato de um visitante são redefinidos após 30 dias de inatividade no navegador.

Exemplo:

* Dia 1: o usuário acessa o site em Exibir. Os canais de primeiro e último toque serão definidos como Exibir.
* Dia 2: o usuário acessa o site em Pesquisa natural. O primeiro toque permanece como Exibir e o Último toque é definido como Pesquisa natural.
* Dia 35: o usuário não visitou o site há 33 dias e retorna usando a guia que havia aberto em seu navegador. Presumindo uma janela de envolvimento de 30 dias, a janela teria fechado e os cookies do Canal de marketing estariam expirados. O canal de primeiro e último toque será redefinido e definido como Atualização da sessão desde que o usuário tenha vindo de um URL interno.

## Configurações de expiração do canal de marketing

As configurações de expiração consistem no seguinte:

| Campo | Definição |
|--- |--- |
| Dias de inatividade | O número de dias que devem decorrer antes que o envolvimento de primeiro toque de um visitante expire. O valor padrão é 30. |
| Nunca | O período de envolvimento do visitante não expira. |
| Redefinição de canal | Expira todos os períodos de envolvimento do visitante.  Se você precisar redefinir todos os dados de canal de marketing, poderá expirar todos os períodos de envolvimento de visitantes. Talvez seja preciso redefinir os dados se suas regras de processamento tiverem sido previamente configuradas de maneira incorreta. Todos os valores de canais de primeiro e último toque expirarão imediatamente e serão redefinidos quando os visitantes retornarem. |

## Definir a expiração do canal de marketing {#define-expiration}

Especifique o período de engajamento do visitante.

1. Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]**.
2. No [!UICONTROL Gerenciador do conjunto de relatórios], clique em **[!UICONTROL Editar configurações]** > **[!UICONTROL Canais de marketing]** > **[!UICONTROL Expiração do canal de marketing]**.

   ![](assets/mchannel_expiration.png)

3. Configure os campos do período de engajamento do visitante.
4. Clique em **[!UICONTROL Salvar]**.
