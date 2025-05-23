---
description: Em vez de manter e fazer upload das classificações sempre que seus códigos de acompanhamento forem alterados, é possível criar classificações automáticas baseadas em regras e aplicá-las em vários conjuntos de relatórios. As regras são processadas durante intervalos frequentes, dependendo do seu volume de tráfico relacionado de classificação.
title: Fluxo de trabalho do criador de regras de classificação
feature: Classifications
exl-id: cdb20dcc-0635-4d5e-9c54-f102d17a0a3d
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 86%

---

# Visão geral do construtor de regras de classificação (herdado)

Em vez de manter e fazer upload das classificações sempre que seus códigos de acompanhamento forem alterados, é possível criar classificações automáticas baseadas em regras e aplicá-las em vários conjuntos de relatórios. As regras são processadas durante intervalos frequentes, dependendo do seu volume de tráfico relacionado de classificação.

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Construtor de regras de classificação](https://video.tv.adobe.com/v/3434379?quality=12&learn=on&captions=por_br){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]

## Aviso importante antes de começar

Lembre-se destes pontos ao usar as regras de classificação:

* Você pode exportar até 10 milhões de linhas por vez.
* Quando o CRB solicita uma exportação, ele extrai valores classificados E não classificados, e os valores não classificados chegam ao final da exportação. Isso significa que, com o tempo, você poderia preencher 10 milhões de valores classificados - sem nunca chegar aos valores não classificados.
* Como a arquitetura é configurada de forma que o CRB pode extrair do &quot;n&quot; número de servidores, isso pode levar a inconsistências sobre quais servidores são selecionados e em que ordem. Por essa razão, é muito difícil chegar aos valores não classificados.

Essa é a **solução alternativa** para quem têm mais de 10 milhões de valores classificados para uma dimensão: você precisará exportar valores não classificados via FTP, em 10 milhões de lotes e classificá-los manualmente.

## Introdução às Regras de classificação {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL Administração]** > **[!UICONTROL Construtor de regras de classificação]**

Veja as etapas de alto nível que você deve seguir para implementar as regras de classificação:

| Etapa | Local de execução | Descrição |
|--- |--- |--- |
| Etapa 1 (pré-requisito): configurar seu esquema de classificação. | [!UICONTROL Administrador] > [!UICONTROL Conjuntos de Relatórios] > [!UICONTROL Editar Configurações] > [!UICONTROL Classificações de Tráfego] ou [!UICONTROL Classificações de Conversão] | Escolha uma variável e defina as classificações a serem usadas para ela. <br>As variáveis devem ter pelo menos uma coluna de classificação criada antes de serem disponibilizadas para uso nas regras.<br>Quando as classificações estiverem habilitadas, pode-se usar o importador e o construtor de regras para classificar valores específicos. |
| Etapa 2: [criar um conjunto de regras](classification-rule-set.md). | [!UICONTROL Administração] > [!UICONTROL Construtor de regras de classificação] > [!UICONTROL Adicionar conjunto de regras] | Um conjunto de regras é um grupo de regras de classificação para uma variável específica. |
| Etapa 3: configurar conjuntos de relatórios e variáveis. | [!UICONTROL Construtor de regras de classificação] > &lt;seu conjunto de regras> | Aplique o conjunto de regras a conjuntos de relatórios e variáveis. |
| Etapa 4: [adicionar as regras de classificação ao conjunto](classification-quickstart-rules.md). | [!UICONTROL Construtor de regras de classificação] > &lt;seu conjunto de regras> | Corresponda uma condição a uma classificação e especificar a ação que aplicará à regra.  Familiarize-se com as informações em [Como as regras são processadas](classification-quickstart-rules.md). |
| Etapa 5: [testar um conjunto de regras de classificação](classification-quickstart-rules.md) | [!DNL Testing Page] | Você desejará testar a validação das regras editando-as no modo de Rascunho. No modo de Rascunho, não é possível executar regras.<br>Essa etapa é importante ao usar [expressões regulares](classification-quickstart-rules.md). |
| Etapa 6: [ativar regras válidas](classification-rule-definitions.md). | [!DNL Rules Page] | Depois que as regras estiverem válidas, ative o conjunto de regras.  É possível substituir teclas existentes, se necessário. Consulte [Como as regras são processadas](classification-quickstart-rules.md). |
| Etapa 7 (opcional): [excluir regras indesejadas](classification-rule-definitions.md). | [!DNL Rules Page] | Excluir regras indesejadas de um conjunto.<br>Observação: a exclusão de regras não exclui dados classificados e carregados. Consulte [Excluir dados de classificação](/help/components/classifications/importer/t-delete-classification-data.md) se precisar excluir dados classificados. |

>[!NOTE]
>
>Grupos com permissões para usar a ferramenta de importação de classificação podem usar regras de classificação. Consulte [Como as regras são processadas](classification-quickstart-rules.md) para obter informações importantes sobre o processamento.

**Recursos adicionais**

**Blog**: para obter mais informações sobre esse recurso, consulte o Blog de marketing digital: [Classificações com base em regras](https://theblog.adobe.com/rule-based-classifications-part-1-making-classifications-easier/).

**Vídeo**: assista ao vídeo [Visão geral de classificações](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/classifications/overview-of-classifications.html?lang=pt-BR).
