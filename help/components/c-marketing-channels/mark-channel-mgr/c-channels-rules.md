---
title: Definir canais
description: Antes de ser possível exibir canais e dados de canal no relatório, é preciso criar os canais e as regras subjacentes que processam os dados. Você também pode criar valores de custo e orçamento para os canais associados no relatório, e especificar a duração desejada para o período de envolvimento do visitante. As tarefas de configuração do relatório são realizadas nas Ferramentas de administração.
translation-type: tm+mt
source-git-commit: e080c38e536f710490291aaca252cba36456b0f9

---


# Definir canais

Antes de ser possível exibir canais e dados de canal no relatório, é preciso criar os canais e as regras subjacentes que processam os dados. Você também pode criar valores de custo e orçamento para os canais associados no relatório, e especificar a duração desejada para o período de envolvimento do visitante. As tarefas de configuração do relatório são realizadas nas Ferramentas de administração.

Imagine um canal como um recipiente para as visitas. As regras atribuem as visitas ao recipiente apropriado.

![](assets/buckets_2.png)

A Adobe fornece diversos canais predefinidos durante uma  [configuração automática](/help/components/c-marketing-channels/getting-started/c-channel-autosetup.md) que pode ser editada conforme seus requisitos.

>[!NOTE]
>
>A Adobe recomenda configurar seu relatório em um conjunto de relatório que pode ser usado como modelo para fins de teste. É possível usar o modelo para aplicar globalmente as definições de canal e regras a um ou mais conjuntos de relatório de produção.
>
>Consulte [Aplicar configurações de conjuntos de relatório de modelo a múltiplos conjuntos de relatório](/help/components/c-marketing-channels/getting-started/t-template.md).

## Pré-requisitos {#prereqs}

Se necessário, entre em contato com o Atendimento ao cliente para obter ajuda com esses pré-requisitos:

* In the Administration Console (General Account Settings), enable the **[!UICONTROL Conversion Level]** (e-commerce) option for the report suite.

   Consulte [Configurações gerais da conta](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/general-acct-settings-admin.html) na ajuda do Analytics para obter mais informações.

* Configure o acesso às dimensões do Canal de marketing.

   See [Marketing Channels permissions](/help/components/c-marketing-channels/mc-access/c-channel-report-access.md).

* Ensure that your account manager has enabled **[!UICONTROL Channel Reports]** for your report suite.

## Observações importantes de processamento {#important-proc-rules}

* O sistema processa as regras na ordem especificada e, quando uma regra é atendida, o sistema para de processar as regras restantes.
* As regras podem acessar variáveis definidas pelo VISTA, mas não podem acessar dados excluídos pelo VISTA.
* Os canais só armazenam métricas de conversão. As métricas de tráfego não estão disponíveis.
* Dois canais de marketing nunca recebem crédito pelo mesmo evento (como compras ou cliques). Dessa forma, os canais de marketing diferem das eVars (já que duas eVars podem receber crédito pelo mesmo evento).
* O relatório pode processar até 25 canais simultaneamente.

