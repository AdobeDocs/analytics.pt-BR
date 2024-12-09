---
description: Saiba como usar feeds de dados para obter dados brutos do Adobe Analytics. Descubra os pré-requisitos para usar os feeds de dados a seguir.
keywords: sequência de cliques;feed de dados;datafeed;Feed de dados
title: Visão geral do feed de dados do Analytics
feature: Data Feeds
exl-id: 2cfff9ad-cdb5-4ae9-a266-4f3d3d046f0c
source-git-commit: 0eef1b1269dcfbc7648127602bdfe24d4789f4b7
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 86%

---

# Visão geral do feed de dados do Analytics

Os feeds de dados são uma maneira avançada de obter dados brutos do Adobe Analytics. Esses dados brutos podem ser usados em outras plataformas fora da Adobe para uso a critério da sua organização. Os dados são fornecidos em lotes por hora, no final de cada hora, ou em lotes diários, no final de cada dia.

## Pré-requisitos

Verifique se você atende a todos os requisitos a seguir antes de utilizar os feeds de dados.

* Uma implementação em funcionamento que envia dados para os servidores de coleta de dados da Adobe. Consulte [Validar e publicar uma implementação](/help/implement/launch/validate-publish-prod.md) no guia de implementação.
* Sua conta é um administrador de produto do Analytics ou pertence a um perfil de produto com acesso a feeds de dados.
* Um bucket configurado no Amazon S3, Google Cloud Platform, Azure RBAC ou Azure SAS.
* (Herdado: obrigatório somente para tipos de destino FTP e SFTP herdados) Tenha um site FTP e credenciais acessíveis (credenciais FTP fornecidas pela sua organização).

## Próximas etapas

Os recursos a seguir ajudam você a entender o fluxo de trabalho básico de obtenção dos feeds de dados. Depois de entender o fluxo de trabalho básico, você pode trabalhar com as equipes na organização para armazenar ou assimilar dados brutos em um banco de dados.

* [Práticas recomendadas de feed de dados](/help/export/analytics-data-feed/data-feeds-best-practices.md): práticas recomendadas para criar e gerenciar feeds de dados.
* [Criar um feed de dados](create-feed.md): Detalhes técnicos para criar um feed de dados, explicando campos individuais com mais detalhes
* [Gerenciar feeds de dados](df-manage-feeds.md): Saiba mais sobre como navegar na interface do feed de dados
* [Conteúdo do feed de dados](c-df-contents/datafeeds-contents.md): Entenda o que está dentro do arquivo compactado <!-- Is this still the output users can download from the destination? I aske Jun. -->
* [Definições de coluna de dados](c-df-contents/datafeeds-reference.md): uma lista abrangente de todas as colunas disponíveis.
* Vídeo de apresentação da interface do feed de dados:

  >[!VIDEO](https://video.tv.adobe.com/v/25452/?quality=12)

* Vídeo sobre como encontrar a ID do feed de dados:

  >[!VIDEO](https://video.tv.adobe.com/v/335747/?quality=12)