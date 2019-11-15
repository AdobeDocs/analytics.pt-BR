---
description: Antes de ser possível exibir canais e dados de canal no relatório, é preciso criar os canais e as regras subjacentes que processam os dados. Você também pode criar valores de custo e orçamento para os canais associados no relatório, e especificar a duração desejada para o período de envolvimento do visitante. As tarefas de configuração do relatório são realizadas nas Ferramentas de administração.
solution: Analytics
subtopic: Marketing channels
title: Sobre canais e regras
topic: Reports and analytics
uuid: 7d574790-4d0d-419d-8fb5-c16ec5a4a387
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Sobre canais e regras

Antes de ser possível exibir canais e dados de canal no relatório, é preciso criar os canais e as regras subjacentes que processam os dados. Você também pode criar valores de custo e orçamento para os canais associados no relatório, e especificar a duração desejada para o período de envolvimento do visitante. As tarefas de configuração do relatório são realizadas nas Ferramentas de administração.

Imagine um canal como um recipiente para as visitas. As regras atribuem as visitas ao recipiente apropriado.

![](assets/buckets_2.png)

A Adobe fornece diversos canais predefinidos durante uma [configuração automática](/help/components/c-marketing-channels/c-channel-autosetup.md) que pode ser editada conforme seus requisitos.

>[!NOTE]
>
>A Adobe recomenda configurar seu relatório em um conjunto de relatórios que você pode usar como modelo para fins de teste. É possível usar o modelo para aplicar globalmente as definições de canal e regras a um ou mais conjuntos de relatório de produção.
>
>Consulte [Aplicar configurações de conjuntos de relatório de modelo a múltiplos conjuntos de relatório](/help/components/c-marketing-channels/t-template.md).

Leia os seguintes tópicos:

* [Pré-requisitos](/help/components/c-marketing-channels/c-channels-rules.md#prereqs)
* [Notas importantes de processamento](/help/components/c-marketing-channels/c-channels-rules.md#important-proc-rules)

## Pré-requisitos {#prereqs}

Se necessário, entre em contato com o Atendimento ao cliente para obter ajuda com esses pré-requisitos:

* In the Administration Console (General Account Settings), enable the **[!UICONTROL Conversion Level]** (e-commerce) option for the report suite.

   See [General Account Settings](https://marketing.adobe.com/resources/help/en_US/reference/general_acct_settings_admin.html) in Analytics help for more information.

* Configure o acesso do grupo de usuários ao **[!UICONTROL Relatório de Canal de marketing]**.

   See [Configure User Group Access](/help/components/c-marketing-channels/t-user-groups.md).

* Ensure that your account manager has enabled **[!UICONTROL Channel Reports]** for your report suite.

## Important processing notes {#important-proc-rules}

* O sistema processa as regras na ordem especificada e, quando uma regra é atendida, o sistema para de processar as regras restantes.
* As regras podem acessar variáveis definidas pelo VISTA, mas não podem acessar dados excluídos pelo VISTA.
* Os canais só armazenam métricas de conversão. As métricas de tráfego não estão disponíveis.
* Dois canais de marketing nunca recebem crédito pelo mesmo evento (como compras ou cliques). Dessa forma, os canais de marketing diferem das eVars (já que duas eVars podem receber crédito pelo mesmo evento).
* O relatório pode processar até 25 canais simultaneamente.

