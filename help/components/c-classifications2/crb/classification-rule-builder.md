---
description: Em vez de manter e fazer upload das classificações sempre que seus códigos de acompanhamento forem alterados, é possível criar classificações automáticas baseadas em regras e aplicá-las em vários conjuntos de relatórios. As regras são processadas durante intervalos frequentes, dependendo do seu volume de tráfico relacionado de classificação.
seo-description: Em vez de manter e fazer upload das classificações sempre que seus códigos de acompanhamento forem alterados, é possível criar classificações automáticas baseadas em regras e aplicá-las em vários conjuntos de relatórios. As regras são processadas durante intervalos frequentes, dependendo do seu volume de tráfico relacionado de classificação.
seo-title: Fluxo de trabalho do Construtor de regras de classificação
solution: Analytics
subtopic: Classificações
title: Fluxo de trabalho do Construtor de regras de classificação
topic: Ferramentas administrativas
uuid: edb 1 f 07 e-fa 86-4055-8 f 4 b-cce 2 d 370 edbb
translation-type: tm+mt
source-git-commit: e71c24fa4762d7f0bc80fc7133ca1cd79dfaf7c5

---


# Fluxo de trabalho do Construtor de regras de classificação

Em vez de manter e fazer upload das classificações sempre que seus códigos de acompanhamento forem alterados, é possível criar classificações automáticas baseadas em regras e aplicá-las em vários conjuntos de relatórios. As regras são processadas durante intervalos frequentes, dependendo do seu volume de tráfico relacionado de classificação.

## Aviso importante antes de começar

Lembre-se disso antes de começar a usar as regras de classificação:

* Nosso sistema de classificação atual só pode exportar até 10 milhões de linhas por vez.
* Quando o construtor de regras de classificação (CRB) solicita uma exportação, ela obtém valores classificados e não classificados, com valores não classificados chegando ao fim da exportação. Isso significa que, ao longo do tempo, você pode preencher 10 milhões de valores classificados, sem nunca chegar aos valores não classificados.
* Como a arquitetura está configurada de uma forma que a CRB possa obter a partir do número "n" de servidores, isso pode gerar inconsistências sobre quais servidores são selecionados e em que ordem. Por esse motivo, é muito difícil obter valores não classificados.

This is the **workaround** for those who have more than 10 million classified values for a dimension: You will need to export unclassified values via FTP, in 10-million batches, and manually classify them.

## Introdução às Regras de classificação {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL Administração]** &gt; **[!UICONTROL Construtor de regras de classificação]**

Estas são as etapas de alto nível que você utiliza para implementar regras de classificação:

| Etapa | Local de execução | Descrição |
|--- |--- |--- |
| Step 1 (Prerequisite): [Set up your classification schema](https://marketing.adobe.com/resources/help/en_US/reference/?f=c_classifications). | [!UICONTROL Administração] &gt; [!UICONTROL Conjuntos] de relatórios &gt; [!UICONTROL Editar configurações] &gt; &lt; Classificações de tráfego ou Classificações de conversão &gt; | Escolha uma variável e defina as classificações a serem usadas para ela. <br>As variáveis devem ter pelo menos uma coluna de classificação criada antes de serem disponibilizadas para uso nas regras.<br>Quando as classificações estiverem habilitadas, pode-se usar o importador e o construtor de regras para classificar valores específicos. |
| Step 2: [Create a rule set](../../../components/c-classifications2/crb/classification-rule-set.md). | [!UICONTROL Administração] &gt; [!UICONTROL Construtor de regras de classificação] &gt; [!UICONTROL Adicionar conjunto de regras] | Um conjunto de regras é um grupo de regras de classificação para uma variável específica. |
| Etapa 3: Configurar conjuntos de relatórios e variáveis. | [!UICONTROL Construtor de regras de classificação] &gt; &lt; seu conjunto de regras &gt; | Aplique o conjunto de regras a conjuntos de relatórios e variáveis. |
| Step 4: [Add classification rules to the set](../../../components/c-classifications2/crb/classification-quickstart-rules.md). | [!UICONTROL Construtor de regras de classificação] &gt; &lt; seu conjunto de regras &gt; | Corresponda uma condição a uma classificação e especificar a ação que aplicará à regra.  Be familiar with the information in  [How Rules Are Processed](../../../components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 5: [Test a Classification Rule Set](../../../components/c-classifications2/crb/classification-quickstart-rules.md) | [!DNL Testing Page] | Você desejará testar a validação das regras editando-as no modo de Rascunho. No modo de Rascunho, não é possível executar regras.<br>Essa etapa é importante ao usar [expressões regulares](../../../components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 6: [Activate valid rules](../../../components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | Depois que as regras estiverem válidas, ative o conjunto de regras.  É possível substituir teclas existentes, se necessário. Consulte [Como as regras são processadas](../../../components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 7 (Optional): [Delete unwanted rules](../../../components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | Excluir regras indesejadas de um conjunto.<br>Observação: a exclusão de regras não exclui dados classificados e carregados.  See  [Delete classification data](../../../components/c-classifications2/c-classifications-importer/t-delete-classification-data.md) if you need to delete classified data. |

>[!NOTE]
>
>Grupos com permissões para usar a ferramenta de importação de classificação podem usar regras de classificação. See [How Rules Are Processed](../../../components/c-classifications2/crb/classification-quickstart-rules.md) for important processing information.

**Recursos adicionais**

**Blog**: Para obter mais informações sobre esse recurso, consulte o Blog de marketing digital: [Classificações com base em regras](https://blogs.adobe.com/digitalmarketing/analytics/rule-based-classifications-part-1-making-classifications-easier/?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+AdobeDigitalMarketing+%28Adobe+Digital+Marketing+Blog%29).

**Vídeo**: Visite [o youtube](https://www.youtube.com/watch?v=6laI5SBXY-I) para exibir [!UICONTROL o vídeo Visão geral] das classificações.
