---
title: Visão geral dos conjuntos de classificações
description: Saiba como usar conjuntos de classificações para gerenciar dados de classificação. Entenda como os conjuntos de classificações diferem das classificações herdadas.
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
feature: Classifications
source-git-commit: 5256319752fb6521ef86c1dde9d3624689879ecb
workflow-type: tm+mt
source-wordcount: '950'
ht-degree: 9%

---

# Visão geral dos conjuntos de classificação

Conjuntos de classificações fornecem uma única interface para gerenciar classificações e regras. Este fluxo de trabalho combina a criação de classificações nas configurações do conjunto de relatórios com o [Importador de classificação](/help/components/classifications/sets/manage/set-manager.md). O resultado é uma única interface intuitiva para criar e gerenciar dados de classificação.


## Conjuntos de classificações em relação a classificações herdadas

A principal diferença entre os conjuntos de classificação e as classificações herdadas é que eles combinam todas as funcionalidades em uma interface, na qual as classificações herdadas dependem de três interfaces.

### Classificações herdadas

![Classificação herdada](/help/components/classifications/sets/assets/classifications-legacy.svg)

Nas classificações herdadas, as classificações ![Esquema](/help/assets/icons2/Schema.svg) (como para tráfego, conversões, canais de marketing e muito mais) têm suas próprias dimensões (chave ![Chave](/help/assets/icons2/Key.svg)). Você define essas classificações como parte das [configurações do conjunto de relatórios](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-classifications.md).

Você define as regras ![BidRule](/help/assets/icons/BidRule.svg) separadamente em conjuntos de regras como parte da interface do [Construtor de regras de classificação](/help/components/classifications/crb/classification-rule-builder.md). Nessa interface, você associa um conjunto de regras a um ou mais conjuntos de relatórios.

Use o [Importador de classificação](/help/components/classifications/importer/c-working-with-saint.md) para baixar um modelo ![DocumentFragment](/help/assets/icons/DocumentFragment.svg), para importar classificações ![UploadToCloud](/help/assets/icons/UploadToCloud.svg) ou exportar classificações ![Download](/help/assets/icons/Download.svg) de uma combinação de conjunto de relatórios - chave (conjunto de dados).



### Conjuntos de classificação

![Conjuntos de classificações](./assets/classifications-sets.svg)

Os conjuntos de classificações combinam todas as interfaces de classificação herdadas em uma só. Cada conjunto de classificações define:

* Uma ou mais assinaturas, que são a combinação de um conjunto de relatórios ![Dados](/help/assets/icons2/Data.svg) e a dimensão ![Chave](/help/assets/icons2/Key.svg) (chave), que você deseja classificar. Se quiser classificar produtos com base em um SKU de produto, você poderá definir todos os conjuntos de relatórios com uma dimensão SKU de produto aplicável. E não é necessário replicar classificações em conjuntos de relatórios como na interface de classificações herdada.
* Uma lista de classificações ![Esquema](/help/assets/icons2/Schema.svg) (esquema) para a chave. Por exemplo, para classificações de produtos, é possível especificar a categoria, a cor, o tamanho, o gênero e muito mais. Depois de definir suas classificações, é possível baixar um modelo ![DocumentFragment](/help/assets/icons/DocumentFragment.svg), carregar dados de classificação ![UploadToCloud](/help/assets/icons/UploadToCloud.svg), baixar dados de classificação ![Download](/help/assets/icons/Download.svg) e muito mais.
* Uma ou mais regras ![BidRule](/help/assets/icons/BidRule.svg) para dar suporte às classificações.


Para acessar **[!UICONTROL Conjuntos de classificações]** pelo menu **[!UICONTROL Componentes]** na interface do Adobe Analytics, você deve ser um administrador de produto ou pertencer a um perfil de produto que contenha o item de permissão [!UICONTROL Ferramentas de Conjunto de Relatórios] > [!UICONTROL Classificações]. Observe que as interfaces herdadas do gerenciamento de classificação estão disponíveis no menu **[!UICONTROL Admin]**.

Os conjuntos de classificações consistem em três áreas funcionais:

* [**[!UICONTROL Conjuntos de classificações]**](manage/set-manager.md): criar, editar e excluir conjuntos de classificações.
* [**[!UICONTROL Trabalhos]**](job-manager.md): exibir o status dos trabalhos dos conjuntos de classificações.
* [**[!UICONTROL Consolidações]**](consolidations/manage.md): combinar vários conjuntos de classificações em um único conjunto de classificações.


## Fluxo de trabalho

O fluxo de trabalho para conjuntos de classificação geralmente envolve as seguintes etapas:

1. Considere para quais conjuntos de relatórios e combinações de dimensões você deseja criar um conjunto de classificações. Um exemplo é definir um conjunto de classificações de produtos que você cria para qualquer conjunto de relatórios para o qual deseja classificar produtos com mais detalhes. Por exemplo, detalhes como categoria e cor.
1. [Crie um conjunto de classificações](/help/components/classifications/sets/manage/create.md) com assinaturas para um ou mais conjuntos de relatórios e combinações de dimensões principais que identificam produtos. Por exemplo:

   | Conjunto de relatórios | Dimensão principal |
   |---|---|
   | Report Suite 1 | Identificação do produto |
   | Report Suite 2 | SKU do produto |

1. [Adicione as classificações](/help/components/classifications/sets/manage/schema.md#add) identificadas ao esquema do conjunto de classificações. Por exemplo:

   | Nome da classificação | Nome da identidade |
   |---|---|
   | Categoria | categoria |
   | Cor do canal | cor |

1. Criar manualmente um arquivo contendo dados de classificação. [Use um modelo](/help/components/classifications/sets/manage/schema.md#template) para garantir o uso do [formato de arquivo com suporte](data-files.md#classification-set-file-formats) e das colunas para o arquivo. Em seguida, adicione os dados ao arquivo de modelo.

   Como alternativa, você pode exportar dados diretamente do catálogo de produtos nos [formatos de arquivo com suporte](data-files.md#classification-set-file-formats) com colunas que seguem o modelo. Por exemplo, um arquivo CSV, como:

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

   No arquivo de dados de classificação, você faz referência à dimensão principal de cada conjunto de relatórios (por exemplo: **[!UICONTROL ID do Produto]** e **[!UICONTROL SKU do Produto]**) usando o `Key`. E você faz referência a cada classificação usando o **[!UICONTROL Nome da Classificação]** (por exemplo, `Category` ou `Color`).

1. [Carregue](/help/components/classifications/sets/manage/schema.md#upload) o arquivo que contém os dados de classificação no esquema do conjunto de classificações.

1. Configure [regras](manage/rules.md) para classificar automaticamente os dados recebidos e os dados do passado.

1. [Automatize](/help/components/classifications/sets/manage/schema.md#automate) o processo de atualizações do catálogo de produtos que você deseja ver refletidas nos dados de classificação por meio do uso de um local na nuvem.

1. [Baixe](/help/components/classifications/sets/manage/schema.md#download) seus dados de classificação para validar o conteúdo.

1. [Inspecione o histórico do trabalho](/help/components/classifications/sets/job-manager.md) para ver os resultados das suas ações (carregamento, download, modelo e muito mais) sobre classificações.
1. Se você tiver vários conjuntos de classificações semelhantes como resultado de uma migração da funcionalidade de classificação herdada, [consolide](consolidations/manage.md) esses conjuntos de classificações.



## Aprimoramentos

A arquitetura de back-end lançada com conjuntos de classificação contém várias melhorias:

* Tempo de processamento reduzido (de 72 horas para 24 horas).
* Uma interface de usuário reprojetada para gerenciar classificações.
* A opção para usar dados de classificação no Adobe Experience Platform por meio do [conector de origem do Adobe Analytics para dados de classificação](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sources/connectors/adobe-applications/classifications).

A arquitetura de back-end lançada com conjuntos de classificação também contém várias alterações:

* Ao usar o navegador ou a importação automatizada, **[!UICONTROL Substituir em caso de conflito]** sempre estará habilitado.
* Ao usar o navegador ou a importação automatizada, não há mais a opção de exportar imediatamente após a importação. As exportações devem ser iniciadas separadamente.
* O ponto de extremidade da API `GetDimensions` do Analytics 2.0 agora retorna identificadores de sequência para classificações em vez de identificadores numéricos. Identificadores numéricos ainda podem ser usados, mas a recomendação é usar os novos identificadores de cadeia de caracteres, quando possível. Os identificadores numéricos podem ser recuperados usando o parâmetro da sequência de consulta `?expansion=hidden`.

>[!IMPORTANT]
>
>O desempenho dos conjuntos de classificação depende principalmente do número de valores de chave exclusiva que contêm dados. Tenha cuidado quando tiver variáveis que contêm grandes números de valores únicos. Especialmente ao combinar essas variáveis de vários conjuntos de relatórios e dimensões em um único conjunto de classificações.

## Limitações

* Os conjuntos de classificações ainda não aceitam regras. A funcionalidade Regras é adicionada à interface dos conjuntos de classificação antes que a funcionalidade [construtor de regras herdada](/help/components/classifications/crb/classification-rule-builder.md) fique indisponível.
* Não há migração de regras e configurações de classificação herdadas para conjuntos de classificação. Um utilitário de migração é adicionado à interface dos conjuntos de classificação antes que a funcionalidade de classificação herdada fique indisponível.
