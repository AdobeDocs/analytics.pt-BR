---
title: Visão geral dos conjuntos de classificações
description: Saiba como usar conjuntos de classificações para gerenciar dados de classificação. Entenda como os conjuntos de classificações diferem das classificações legadas.
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
feature: Classifications
source-git-commit: e1ccd006336f10b8f843d59cfdcd220064524349
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 100%

---

# Visão geral dos conjuntos de classificação

Conjuntos de classificações fornecem uma única interface para gerenciar classificações e regras. Este fluxo de trabalho combina a criação de classificações nas [Configurações do conjunto de relatórios](/help/admin/tools/manage-rs/report-suites-admin.md) com o [Importador de classificação](/help/components/classifications/sets/manage-sets.md). O resultado é uma única interface intuitiva para criar e gerenciar dados de classificação.


## Conjuntos de classificações vs. classificações herdadas

A principal diferença entre os conjuntos de classificações e as classificações legadas é que os conjuntos de classificações combinam todas as funcionalidades em uma única interface e as classificações legadas dependem de três interfaces.

### Classificações herdadas

![Classificação herdada](/help/components/classifications/sets/assets/classifications-legacy.svg)

Nas classificações herdadas, classificações ![Esquema](/help/assets/icons2/Schema.svg) (como para tráfego, conversões, canais de marketing e mais) têm cada uma sua própria dimensão (chave ![Chave](/help/assets/icons2/Key.svg)). Você define essas classificações como parte das [Configurações do conjunto de relatórios](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-classifications.md).

As regras ![BidRule](/help/assets/icons/BidRule.svg) são definidas separadamente em conjuntos de regras como parte da interface do [Construtor de regras de classificação](/help/components/classifications/crb/classification-rule-builder.md). Nessa interface, você associa um conjunto de regras a um ou mais conjuntos de relatórios.

Use o [Importador de classificação](/help/components/classifications/importer/c-working-with-saint.md) para baixar um modelo ![DocumentFragment](/help/assets/icons/DocumentFragment.svg), para importar classificações ![UploadToCloud](/help/assets/icons/UploadToCloud.svg) ou exportar classificações ![Download](/help/assets/icons/Download.svg) de uma combinação de conjunto de relatórios - chave (conjunto de dados).



### Conjuntos de classificações

![Conjuntos de classificações](./assets/classifications-sets.svg)

Os conjuntos de classificações combinam todas as interfaces de classificação legadas em apenas uma. Cada conjunto de classificações define:

* Uma ou mais assinaturas, que são a combinação de um conjunto de relatórios ![Dados](/help/assets/icons2/Data.svg) e a dimensão ![Chave](/help/assets/icons2/Key.svg) (chave) que você deseja classificar. Se quiser classificar produtos com base em um SKU de produto, você poderá definir todos os conjuntos de relatórios com uma dimensão do SKU de produto aplicável. E não é necessário replicar classificações em conjuntos de relatórios, como na interface de classificações herdada.
* Uma lista de classificações ![Esquema](/help/assets/icons2/Schema.svg) (esquema) para a chave. Por exemplo, para classificações de produtos, é possível especificar a categoria, a cor, o tamanho, o gênero e mais. Depois de definir as classificações, é possível baixar um modelo ![DocumentFragment](/help/assets/icons/DocumentFragment.svg), carregar dados de classificação ![UploadToCloud](/help/assets/icons/UploadToCloud.svg), baixar dados de classificação ![Download](/help/assets/icons/Download.svg) e mais.
* Uma ou mais regras ![BidRule](/help/assets/icons/BidRule.svg) para dar suporte às classificações.


Para acessar os **[!UICONTROL Conjuntos de classificações]** pelo menu **[!UICONTROL Componentes]** na interface do Adobe Analytics, é necessário ser admin de produto ou pertencer a um perfil de produto que contenha o item de permissão [!UICONTROL Ferramentas de conjunto de relatórios] > [!UICONTROL Classificações]. Observe que as interfaces herdadas do gerenciamento de classificações estão disponíveis no menu **[!UICONTROL Admin]**.

Os conjuntos de classificações consistem em três áreas funcionais:

* [**[!UICONTROL Conjuntos de classificações]**](manage-sets.md): crie, edite e exclua conjuntos de classificações.
* [**[!UICONTROL Trabalhos]**](job-manager.md): exiba o status das tarefas dos conjuntos de classificações.
* [**[!UICONTROL Consolidações]**](consolidations/manage.md): combine vários conjuntos de classificações em um único.


## Fluxo de trabalho

O fluxo de trabalho para conjuntos de classificações geralmente envolve as seguintes etapas:

1. Considere para quais conjuntos de relatórios e combinações de dimensões você deseja criar um conjunto de classificações. Um exemplo é definir um conjunto de classificações de produtos que é criado para qualquer conjunto de relatórios, no qual você deseja classificar produtos com mais detalhes. Por exemplo, detalhes como categoria e cor.
1. [Crie um conjunto de classificações](/help/components/classifications/sets/create-set.md) com assinaturas para um ou mais conjuntos de relatórios e combinações de dimensões principais que identifica produtos. Por exemplo:

   | Conjunto de relatórios | Dimensão principal |
   |---|---|
   | Conjunto de relatórios 1 | Identificação do produto |
   | Conjunto de relatórios 2 | SKU do produto |

1. [Adicione as classificações](/help/components/classifications/sets/manage/schema.md#add) identificadas ao esquema do conjunto de classificações. Por exemplo:

   | Nome da classificação | Nome da identidade |
   |---|---|
   | Categoria | categoria |
   | Cor | Cor |

1. Criar manualmente um arquivo contendo dados de classificação. [Utilize um modelo](/help/components/classifications/sets/manage/schema.md#template) para garantir o uso do [formato de arquivo compatível](data-files.md#classification-set-file-formats) e das colunas no arquivo. Em seguida, adicione os dados ao arquivo modelo.

   Como alternativa, é possível exportar dados diretamente do catálogo de produtos nos [formatos de arquivo compatíveis](data-files.md#classification-set-file-formats) com colunas que seguem o modelo. Por exemplo, um arquivo CSV, como:

   ```
   Key,Category,Color
   Adobe Nike Tech Fleece Full-Zip Hoodie - Men's,Men,Black
   Adobe Nike Tech Fleece Full-Zip Hoodie - Women's,Women,Black
   Men's North Face Adobe Jacket,Men,Black
   Nike Air Hybrid 2 Golf Bag,Equipment,Blue
   STITCH&reg; Ultimate Garment Bag,Equipment,Brown
   Adobe Analytics Training Tee - Navy,Men,Navy
   AirPods Pro 2,Electronics,White
   Adobe Analytics Training Tee - Green,Men,Green
   Women's North Face Adobe Jacket,Women,Blue
   Adobe Analytics Training Tee - Grey,Men,Gray
   Adobe Analytics One Million Views - Grey,Equipment,Grey
   Adobe and MGM Tee - White,Women,White
   Adobe and MGM Tee - Charcoal,Women,Charcoal
   ```

   No arquivo de dados de classificação, você faz referência à dimensão principal de cada conjunto de relatórios (por exemplo: **[!UICONTROL ID do produto]** e **[!UICONTROL SKU do Produto]**) usando o `Key`. E você faz referência a cada classificação usando o **[!UICONTROL Nome da classificação]** (por exemplo, `Category` ou `Color`).

1. [Faça upload](/help/components/classifications/sets/manage/schema.md#upload) do arquivo que contém os dados de classificação no esquema do conjunto de classificações.

1. Configure [regras](manage/rules.md) para classificar automaticamente os dados recebidos e os dados do passado.

1. [Automatize](/help/components/classifications/sets/manage/schema.md#automate) o processo de atualizações do catálogo de produtos que você deseja ver refletidas nos dados de classificação por meio do uso de um local na nuvem.

1. [Baixe](/help/components/classifications/sets/manage/schema.md#download) os dados de classificação para validar o conteúdo.

1. [Inspecione o histórico do trabalho](/help/components/classifications/sets/job-manager.md) para ver os resultados das suas ações (upload, download, modelo e muito mais) sobre as classificações.
1. Se você tiver vários conjuntos de classificações semelhantes como resultado de uma migração da funcionalidade de classificação legada, [consolide](consolidations/manage.md) esses conjuntos de classificações.



## Melhorias

A arquitetura de back-end lançada com os conjuntos de classificação contém várias melhorias:

* Redução do tempo de processamento (de 72 horas para 24 horas).
* Uma interface de usuário reprojetada para gerenciar classificações.
* A opção de usar dados de classificação na Adobe Experience Platform por meio do [Conector de origem do Adobe Analytics para classificação de dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sources/connectors/adobe-applications/classifications).

A arquitetura de back-end lançada com os conjuntos de classificação também contém várias alterações:

* Ao usar o navegador ou a importação automatizada, a opção **[!UICONTROL Substituir em caso de conflito]** está sempre habilitada.
* Ao usar o navegador ou a importação automatizada, não há mais a opção de exportar imediatamente após a importação. As exportações devem ser iniciadas separadamente.
* O ponto de acesso da API `GetDimensions` do Analytics 2.0 agora retorna identificadores de string para classificações em vez de identificadores numéricos. Identificadores numéricos ainda podem ser usados, mas a recomendação é usar os novos identificadores de texto sempre que possível. Os identificadores numéricos podem ser recuperados usando o parâmetro da sequência de consulta `?expansion=hidden`.

>[!IMPORTANT]
>
>O desempenho dos conjuntos de classificação depende principalmente do número de valores de chave exclusiva que contêm dados. Tenha cuidado quando tiver variáveis que contêm grandes números de valores únicos. Esse cuidado se aplica especialmente ao combinar variáveis de vários conjuntos de relatórios e dimensões em um único conjunto de classificação.
