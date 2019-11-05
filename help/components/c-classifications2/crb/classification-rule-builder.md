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
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Fluxo de trabalho do criador de regras de classificação

Em vez de manter e fazer upload das classificações sempre que seus códigos de acompanhamento forem alterados, é possível criar classificações automáticas baseadas em regras e aplicá-las em vários conjuntos de relatórios. As regras são processadas durante intervalos frequentes, dependendo do seu volume de tráfico relacionado de classificação.

## Aviso importante antes de começar

Lembre-se disso antes de começar a usar as regras de classificação:

* Nosso sistema de classificação atual só pode exportar até 10 milhões de linhas por vez.
* Quando o CRB (Construtor de regras de classificação) solicita uma exportação, ele extrai valores classificados E não classificados, com valores não classificados sendo atingidos no final da exportação. Isso significa que, com o tempo, você poderia preencher 10 milhões de valores classificados - sem nunca chegar aos valores não classificados.
* Como a arquitetura está configurada de uma forma que o CRB pode estar tirando do número "n" de servidores, isso pode levar a inconsistências sobre quais servidores são coletados e em que ordem. Por essa razão, é muito difícil chegar a valores não classificados.

Esta é a **solução** alternativa para aqueles que têm mais de 10 milhões de valores classificados para uma dimensão: Você precisará exportar valores não classificados via FTP, em 10 milhões de lotes e classificá-los manualmente.

## Introdução às Regras de classificação {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL Administrador]** &gt; Construtor de regras **[!UICONTROL de classificação]**

Estas são as etapas de alto nível que você segue para implementar regras de classificação:

| Etapa | Local de execução | Descrição |
|--- |--- |--- |
| Step 1 (Prerequisite): [Set up your classification schema](https://marketing.adobe.com/resources/help/en_US/reference/c_classifications.html). | [!UICONTROL Admin] &gt; Conjuntos [!UICONTROL de] relatórios &gt; [!UICONTROL Editar configurações] &gt; &lt;Classificações de tráfego ou Classificações de conversão&gt; | Escolha uma variável e defina as classificações a serem usadas para ela. <br>As variáveis devem ter pelo menos uma coluna de classificação criada antes de serem disponibilizadas para uso nas regras.<br>Quando as classificações estiverem habilitadas, pode-se usar o importador e o construtor de regras para classificar valores específicos. |
| Step 2: [Create a rule set](/help/components/c-classifications2/crb/classification-rule-set.md). | [!UICONTROL Administração] &gt; [!UICONTROL Construtor de regras de classificação] &gt; [!UICONTROL Adicionar conjunto de regras] | Um conjunto de regras é um grupo de regras de classificação para uma variável específica. |
| Etapa 3: Configure conjuntos de relatórios e variáveis. | [!UICONTROL Construtor] de regras de classificação &gt; &lt;seu conjunto de regras&gt; | Aplique o conjunto de regras a conjuntos de relatórios e variáveis. |
| Step 4: [Add classification rules to the set](/help/components/c-classifications2/crb/classification-quickstart-rules.md). | [!UICONTROL Construtor] de regras de classificação &gt; &lt;seu conjunto de regras&gt; | Corresponda uma condição a uma classificação e especificar a ação que aplicará à regra.  Familiarize-se com as informações em [Como as regras são processadas](/help/components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 5: [Test a Classification Rule Set](/help/components/c-classifications2/crb/classification-quickstart-rules.md) | [!DNL Testing Page] | Você desejará testar a validação das regras editando-as no modo de Rascunho. No modo de Rascunho, não é possível executar regras.<br>Essa etapa é importante ao usar expressões [](/help/components/c-classifications2/crb/classification-quickstart-rules.md)regulares. |
| Etapa 6: [Ativar regras](/help/components/c-classifications2/crb/classification-rule-definitions.md)válidas. | [!DNL Rules Page] | Depois que as regras estiverem válidas, ative o conjunto de regras.  É possível substituir teclas existentes, se necessário. Consulte [Como as regras são processadas](/help/components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 7 (Optional): [Delete unwanted rules](/help/components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | Excluir regras indesejadas de um conjunto.<br>Observação: a exclusão de regras não exclui dados classificados e carregados.  See  [Delete classification data](/help/components/c-classifications2/c-classifications-importer/t-delete-classification-data.md) if you need to delete classified data. |

>[!NOTE]
>
> Grupos com permissões para usar a ferramenta de importação de classificação podem usar regras de classificação. See [How Rules Are Processed](/help/components/c-classifications2/crb/classification-quickstart-rules.md) for important processing information.

**Recursos adicionais**

**Blog**: Para obter informações adicionais sobre esse recurso, consulte o Blog de marketing digital: Classificações [baseadas em](https://blogs.adobe.com/digitalmarketing/analytics/rule-based-classifications-part-1-making-classifications-easier/?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+AdobeDigitalMarketing+%28Adobe+Digital+Marketing+Blog%29)regras.

**Vídeo**: Visite o [YouTube](https://www.youtube.com/watch?v=6laI5SBXY-I) para exibir o vídeo Visão geral [!UICONTROL de] classificações.
