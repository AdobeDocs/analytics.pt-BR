---
title: Visão geral dos conjuntos de classificações
description: Use conjuntos de classificações para gerenciar dados de classificação.
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
feature: Classifications
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 26%

---

# Visão geral dos conjuntos de classificações

Os conjuntos de classificações fornecem uma única interface para gerenciar classificações e regras. Esse fluxo de trabalho combina o conceito de criação de classificações das configurações do conjunto de relatórios com o conceito do importador de classificação para fornecer uma interface mais intuitiva para criação e gerenciamento de dados de classificação.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de classificações]**

A arquitetura de back-end lançada com conjuntos de classificação contém várias melhorias notáveis:

* Tempo de processamento reduzido (72 horas → 24 horas)
* A capacidade de usar a interface dos conjuntos de classificação
* A opção de usar os dados de classificação na Adobe Experience Platform no futuro por meio do [Conector de origem do Adobe Analytics para dados de classificação](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html?lang=pt-BR)

A arquitetura de back-end lançada com conjuntos de classificação também contém várias alterações importantes:

* Ao usar o navegador ou a importação automatizada, &#39;[!UICONTROL Substituir em caso de conflito]&#39; é sempre ativado.
* Ao usar o navegador ou a importação automatizada, a opção de exportar imediatamente após a importação não é mais compatível. As exportações devem ser iniciadas separadamente.
* O endpoint `GetDimensions` da API do Analytics 2.0 agora retorna identificadores de string para classificações em vez de identificadores numéricos. Identificadores numéricos ainda podem ser usados, mas a Adobe recomenda o uso dos novos identificadores de sequência, quando possível. Os identificadores numéricos podem ser recuperados usando o parâmetro da sequência de consulta `?expansion=hidden`.

>[!IMPORTANT]
>
>O desempenho dos conjuntos de classificação depende principalmente do número de valores de chave únicos que contêm dados. Adobe recomenda ter cuidado ao lidar com variáveis que contêm grandes números de valores únicos. Esse cuidado se aplica especialmente ao combinar variáveis de vários conjuntos de relatórios e dimensões em um único conjunto de classificação.

Os conjuntos de classificações consistem em três áreas principais:

* [**[!UICONTROL Gerenciador de conjuntos de classificações]**](manage/set-manager.md): criar, editar e excluir conjuntos de classificações.
* [**[!UICONTROL Gerenciador de processos do conjunto de classificações]**](job-manager.md): visualize o status dos trabalhos do conjunto de classificações e baixe os arquivos de exportação.
* [**[!UICONTROL Consolidações do conjunto de classificações]**](consolidations/manage.md): combine vários conjuntos de classificações em um único conjunto de classificações.
