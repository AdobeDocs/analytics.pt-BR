---
description: Em vez de manter e fazer upload das classificações sempre que seus códigos de acompanhamento forem alterados, é possível criar classificações automáticas baseadas em regras e aplicá-las em vários conjuntos de relatórios. As regras são processadas durante intervalos frequentes, dependendo do seu volume de tráfico relacionado de classificação.
seo-description: Em vez de manter e fazer upload das classificações sempre que seus códigos de acompanhamento forem alterados, é possível criar classificações automáticas baseadas em regras e aplicá-las em vários conjuntos de relatórios. As regras são processadas durante intervalos frequentes, dependendo do seu volume de tráfico relacionado de classificação.
seo-title: Fluxo de trabalho do criador de regras de classificação
solution: Analytics
subtopic: Classificações
title: Fluxo de trabalho do criador de regras de classificação
topic: Ferramentas administrativas
uuid: edb1f07e-fa86-4055-8f4b-cce2d370edbb
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Fluxo de trabalho do criador de regras de classificação

Em vez de manter e fazer upload das classificações sempre que seus códigos de acompanhamento forem alterados, é possível criar classificações automáticas baseadas em regras e aplicá-las em vários conjuntos de relatórios. As regras são processadas durante intervalos frequentes, dependendo do seu volume de tráfico relacionado de classificação.

## Important Notice before you get started

Keep this in mind before you start using classification rules:

* Our current classification system can only export up to 10 million rows at a time.
* When classification rule builder (CRB) requests an export, it pulls both classified AND unclassified values, with unclassified values coming through at the end of the export. This means that, over time, you could fill up 10 million classified values - without ever getting to the unclassified values.
* Because the architecture is set up in a way that CRB could be pulling from "n" number of servers, this can lead to inconsistencies as to which servers get picked up and in what order. For that reason, it is very difficult to get to unclassified values.

Esta é a **solução** alternativa para aqueles que têm mais de 10 milhões de valores classificados para uma dimensão: Você precisará exportar valores não classificados via FTP, em 10 milhões de lotes e classificá-los manualmente.

## Introdução às Regras de classificação {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL Administrador]** &gt; Construtor de regras **[!UICONTROL de classificação]**

Estas são as etapas de alto nível que você segue para implementar regras de classificação:

| Etapa | Local de execução | Descrição |
|--- |--- |--- |
| Step 1 (Prerequisite): [Set up your classification schema](https://marketing.adobe.com/resources/help/en_US/reference/c_classifications.html). | [!UICONTROL Admin] &gt; Conjuntos [!UICONTROL de] relatórios &gt; [!UICONTROL Editar configurações] &gt; &lt;Classificações de tráfego ou Classificações de conversão&gt; | Escolha uma variável e defina as classificações a serem usadas para ela. <br>As variáveis devem ter pelo menos uma coluna de classificação criada antes de serem disponibilizadas para uso nas regras.<br>Quando as classificações estiverem habilitadas, pode-se usar o importador e o construtor de regras para classificar valores específicos. |
| Step 2: [Create a rule set](../../../components/c-classifications2/crb/classification-rule-set.md). | [!UICONTROL Administração] &gt; [!UICONTROL Construtor de regras de classificação] &gt; [!UICONTROL Adicionar conjunto de regras] | Um conjunto de regras é um grupo de regras de classificação para uma variável específica. |
| Step 3: Configure report suites and variables. | [!UICONTROL Construtor] de regras de classificação &gt; &lt;seu conjunto de regras&gt; | Aplique o conjunto de regras a conjuntos de relatórios e variáveis. |
| Step 4: [Add classification rules to the set](../../../components/c-classifications2/crb/classification-quickstart-rules.md). | [!UICONTROL Construtor] de regras de classificação &gt; &lt;seu conjunto de regras&gt; | Corresponda uma condição a uma classificação e especificar a ação que aplicará à regra.  Familiarize-se com as informações em [Como as regras são processadas](../../../components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 5: [Test a Classification Rule Set](../../../components/c-classifications2/crb/classification-quickstart-rules.md) | [!DNL Testing Page] | Você desejará testar a validação das regras editando-as no modo de Rascunho. No modo de Rascunho, não é possível executar regras.<br>Essa etapa é importante ao usar expressões [](../../../components/c-classifications2/crb/classification-quickstart-rules.md)regulares. |
| Etapa 6: [Ativar regras](../../../components/c-classifications2/crb/classification-rule-definitions.md)válidas. | [!DNL Rules Page] | Depois que as regras estiverem válidas, ative o conjunto de regras.  É possível substituir teclas existentes, se necessário. Consulte [Como as regras são processadas](../../../components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 7 (Optional): [Delete unwanted rules](../../../components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | Excluir regras indesejadas de um conjunto.<br>Observação: a exclusão de regras não exclui dados classificados e carregados.  See  [Delete classification data](../../../components/c-classifications2/c-classifications-importer/t-delete-classification-data.md) if you need to delete classified data. |

>[!NOTE]
>
>Groups with permissions to use the classification import tool can use classification rules. See [How Rules Are Processed](../../../components/c-classifications2/crb/classification-quickstart-rules.md) for important processing information.

**Recursos adicionais**

**Blog**: Para obter informações adicionais sobre esse recurso, consulte o Blog de marketing digital: Classificações [baseadas em](https://blogs.adobe.com/digitalmarketing/analytics/rule-based-classifications-part-1-making-classifications-easier/?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+AdobeDigitalMarketing+%28Adobe+Digital+Marketing+Blog%29)regras.

**Vídeo**: Visite o [YouTube](https://www.youtube.com/watch?v=6laI5SBXY-I) para exibir o vídeo Visão geral [!UICONTROL de] classificações.
