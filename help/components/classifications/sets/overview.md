---
title: Visão geral dos conjuntos de classificações
description: Use conjuntos de classificações para gerenciar os dados de classificação.
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 90%

---

# Visão geral dos conjuntos de classificações

Os conjuntos de classificações fornecem uma única interface para gerenciar classificações e regras. Esse fluxo de trabalho combina o conceito de criação de classificações das configurações do conjunto de relatórios com o conceito do Importador de classificações para fornecer uma interface mais intuitiva para criação e gerenciamento de dados de classificação.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de classificações]**

>[!NOTE]
>
>Esse recurso está disponível para todos os clientes na arquitetura do Conjunto de classificações. Entre em contato com o Atendimento ao cliente da Adobe ou com a equipe de conta da Adobe para obter mais informações.

A arquitetura de back-end lançada com os Conjuntos de Classificação contém várias melhorias notáveis:

* Redução significativa do tempo de processamento (72 horas → 24 horas)
* A capacidade de usar a Interface dos Conjuntos de Classificação
* A opção de usar os dados de classificação na Adobe Experience Platform no futuro por meio do [Conector de origem do Adobe Analytics para dados de classificação](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)

A arquitetura de back-end lançada com os Conjuntos de Classificação também contém várias alterações importantes:

* Ao usar o navegador ou a importação de FTP, &#39;[!UICONTROL Substituir em conflito]&#39; está sempre ativado.
* Ao usar o navegador ou importação de FTP, a opção de exportar imediatamente após a importação não é mais suportada. As exportações devem ser iniciadas separadamente.
* O endpoint `GetDimensions` da API do Analytics 2.0 agora retorna identificadores de string para classificações em vez de identificadores numéricos. Identificadores numéricos ainda podem ser usados, mas a Adobe recomenda o uso dos novos identificadores de sequência, quando possível. Os identificadores numéricos podem ser recuperados usando o parâmetro da string de consulta `?expansion=hidden`.


Os conjuntos de classificações consistem em duas áreas principais:

* [**[!UICONTROL Gerenciador de conjuntos de classificações]**](set-manager.md): criar, editar e excluir conjuntos de classificações.
* [**[!UICONTROL Gerenciador de processos do conjunto de classificações]**](job-manager.md): visualizar o status dos processos do conjunto de classificações e baixar os arquivos de exportação.
