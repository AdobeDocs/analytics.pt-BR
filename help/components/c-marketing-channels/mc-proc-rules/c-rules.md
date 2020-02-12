---
title: Regras de processamento para Canais de marketing
description: As regras de processamento de Canal de marketing determinam se uma ocorrência de visitante atende aos critérios atribuídos a um canal. As regras processam cada acesso que um visitante faz ao seu site. Quando uma regra não atende aos critérios de um canal, ou se as regras não foram configuradas corretamente, o sistema atribui o acesso a Nenhum canal identificado.
translation-type: tm+mt
source-git-commit: ea4d9e6c9396032fe323de594cb43eecbf97aa15

---


# Regras de processamento para Canais de marketing

As regras de processamento de Canal de marketing determinam se uma ocorrência de visitante atende aos critérios atribuídos a um canal. As regras processam cada acesso que um visitante faz ao seu site. Quando uma regra não atende aos critérios de um canal, ou se as regras não foram configuradas corretamente, o sistema atribui o acesso a Nenhum canal identificado.

A seguir, algumas orientações importantes para a criação de regras:

* Classifique as regras na ordem em que deseja que elas sejam processadas.
* Ao fim da lista, inclua uma regra para capturar tudo como, por exemplo, Outros. Essa regra identifica o tráfego externo, mas não o tráfego interno.

   Consulte [Nenhum Canal Identificado.](/help/components/c-marketing-channels/mc-faq/c-faq.md#no-channel-identified)

> [!NOTE] Embora essas regras não afetem o relatório fora dos canais de marketing, afetam a coleção de dados do canal de marketing. Os dados coletados com essas regras são totalmente permanentes, e as regras alteradas após a coleta dos dados não são retroativas. It is strongly recommended to review and consider all circumstances before saving [!UICONTROL Marketing Channel Processing Rules] to mitigate data being collected in incorrect channels.

## Pré-requisitos

* Revise as informações conceituais em [Introdução aos Canais](/help/components/c-marketing-channels/getting-started/c-getting-started-mchannel.md)de marketing.
* Crie um ou mais canais para poder atribuir regras a eles. Consulte [Adicionar canais de marketing.](/help/components/c-marketing-channels/mark-channel-mgr/c-channels.md)
