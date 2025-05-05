---
title: Visão geral dos conjuntos de classificação
description: Use conjuntos de classificações para gerenciar os dados de classificação.
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
feature: Classifications
source-git-commit: 66be48d0f41061d259cc53fb835ebd155294a710
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 84%

---

# Visão geral dos conjuntos de classificação

Conjuntos de classificações fornecem uma única interface para gerenciar classificações e regras. Este fluxo de trabalho combina o conceito de criação de classificações nas configurações do conjunto de relatórios com o conceito do importador de classificação para fornecer uma interface mais intuitiva para criar e gerenciar dados de classificação.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de classificações]**

Você deve ser um administrador de produto ou pertencer a um perfil de produto que contenha o item de permissão [!UICONTROL Ferramentas do Conjunto de relatórios] > [!UICONTROL Classificações] para ver este item de menu. Observe que enquanto as interfaces anteriores de gerenciamento de classificação estão no menu [!UICONTROL Admin], os conjuntos de classificação estão no menu [!UICONTROL Componentes].

## Melhorias

A arquitetura de back-end lançada com os conjuntos de classificação contém várias melhorias notáveis:

* Redução do tempo de processamento (72 horas → 24 horas)
* Uma interface do usuário reprojetada para gerenciar classificações
* A opção de usar os dados de classificação na Adobe Experience Platform no futuro por meio do [Conector de origem do Adobe Analytics para dados de classificação](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sources/connectors/adobe-applications/classifications)

A arquitetura de back-end lançada com os conjuntos de classificação também contém várias alterações importantes:

* Ao usar o navegador ou a importação automatizada, a opção “[!UICONTROL Sobrescrever em caso de conflito]” está sempre habilitada.
* Ao usar o navegador ou a importação automatizada, não há mais a opção de exportar imediatamente após a importação. As exportações devem ser iniciadas separadamente.
* O endpoint `GetDimensions` da API do Analytics 2.0 agora retorna identificadores de string para classificações em vez de identificadores numéricos. Identificadores numéricos ainda podem ser usados, mas a Adobe recomenda o uso dos novos identificadores de sequência, quando possível. Os identificadores numéricos podem ser recuperados usando o parâmetro da sequência de consulta `?expansion=hidden`.

>[!IMPORTANT]
>
>O desempenho dos conjuntos de classificação depende principalmente do número de valores de chave exclusiva que contêm dados. A Adobe recomenda ter cuidado ao lidar com variáveis que contêm grandes números de valores únicos. Esse cuidado se aplica especialmente ao combinar variáveis de vários conjuntos de relatórios e dimensões em um único conjunto de classificação.

Os conjuntos de classificação consistem em três áreas principais:

* [**[!UICONTROL Gerenciador de conjuntos de classificações]**](manage/set-manager.md): crie, edite e exclua conjuntos de classificação.
* [**[!UICONTROL Gerenciador de tarefas do conjunto de classificação]**](job-manager.md): veja o status das tarefas do conjunto de classificação e baixe arquivos de exportação.
* [**[!UICONTROL Consolidações de conjuntos de classificação]**](consolidations/manage.md): combine vários conjuntos de classificação em um único conjunto.
