---
description: Configurar a conta de importação na nuvem e o local onde os dados de classificação podem ser carregados
keywords: Analysis Workspace
title: Configurar locais de importação e exportação na nuvem
feature: Classifications
exl-id: 55179868-6228-44ff-835c-f4a7b38e929b
source-git-commit: df9470f1870879ac91f00a021ed890bc6fb10cda
workflow-type: tm+mt
source-wordcount: '1687'
ht-degree: 30%

---

# Configurar locais de importação e exportação na nuvem

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

>[!NOTE]
>
>Considere o seguinte ao criar e editar locais:<ul><li>Os administradores de sistema podem impedir que os usuários criem locais, conforme descrito em [Configurar se os usuários podem criar locais](/help/components/locations/locations-manager.md#configure-whether-users-can-create-locations). Se você não puder criar locais conforme descrito nesta seção, entre em contato com o administrador do sistema.</li><li>Um local pode ser editado somente pelo usuário que o criou ou por um administrador do sistema.</li></ul>

Depois que você [configurar uma conta na nuvem](/help/components/locations/configure-import-accounts.md), você poderá configurar uma localização nessa conta. Um único local pode ser usado para qualquer uma das seguintes finalidades (um único local não pode ser associado a várias finalidades):

* Exportação de arquivos usando [Feeds de dados](/help/export/analytics-data-feed/create-feed.md)
* Exportar relatórios usando [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* Importação de esquemas usando o [Conjuntos de classificações](/help/components/classifications/sets/overview.md)

Você deve configurar o Adobe Analytics com as informações necessárias para acessar sua conta da nuvem. Esse processo consiste em adicionar e configurar a conta (como a função ARN do Amazon S3, a Google Cloud Platform e assim por diante), conforme descrito em [Configurar contas de importação e exportação na nuvem](/help/components/locations/configure-import-accounts.md)e, em seguida, adicionar e configurar o local nessa conta (conforme descrito neste artigo).

Para obter informações sobre como exibir e excluir locais existentes, consulte [Gerenciador de locais](/help/components/locations/locations-manager.md).

## Começar a criar ou editar um local

1. No Adobe Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Localizações**].

1. No [!UICONTROL Localizações] selecione a [!UICONTROL **Localizações**] guia.

1. (Condicional) Se você for um administrador do sistema, poderá ativar a [!UICONTROL **Exibir locais para todos os usuários**] opção para exibir locais criados por todos os usuários em sua organização.
   ![exibir locais para todos os usuários](assets/locations-all-users.png)

1. Para adicionar um novo local, selecione [!UICONTROL **Adicionar localização**]. (Se ainda não tiver adicionado uma conta, adicione-a conforme descrito em [Configurar contas de importação e exportação na nuvem](/help/components/locations/configure-import-accounts.md).)

   A variável [!UICONTROL **Adicionar localização**] é exibida

   Ou

   Para editar um local existente, selecione o menu de 3 pontos ao lado do nome do local e selecione [!UICONTROL **Editar**].

   A variável [!UICONTROL **Detalhes do local**] é exibida.

1. Especifique as seguintes informações: |Campo | Função | |—|—| | [!UICONTROL **Nome**] | O nome do local.  | 
| [!UICONTROL **Descrição**] | Forneça uma breve descrição da conta para ajudar a diferenciá-la de outras contas do mesmo tipo. | | [!UICONTROL **Usar com**] | Selecione se você deseja usar esta localização com [!UICONTROL **Feeds de dados**], [!UICONTROL **Data Warehouse**] ou [!UICONTROL **Conjuntos de classificações**]. <p>Considere o seguinte ao fazer uma seleção:</p><ul><li>Um único local não pode ser usado para vários propósitos. Por exemplo, um local usado para feeds de dados também não pode ser usado para conjuntos de Datas Warehouse ou Classificações.</li><li>Para evitar conflitos de arquivos em um local, não altere o valor do [!UICONTROL **Usar com**] após a localização ter sido usada.</li><li>Se você estiver criando um local para uma conta de email, selecione [!UICONTROL **Data Warehouse**] neste campo. Os locais de email não são compatíveis com feeds de dados e conjuntos de classificação.</li></ul> | | [!UICONTROL **Disponibilizar a localização a todos os usuários na organização**] | Habilite essa opção para permitir que outros usuários em sua organização usem o local.<p>Considere o seguinte ao compartilhar locais:</p><ul><li>Os locais compartilhados não podem ter o compartilhamento cancelado.</li><li>Os locais compartilhados podem ser editados somente pelo proprietário do local.</li><li>Os locais podem ser compartilhados somente se a conta à qual o local está associado também for compartilhada.</li></ul> | | [!UICONTROL **Conta de localização**] | Selecione a conta de localização na qual deseja criar esta localização. Para obter informações sobre como criar uma conta, consulte [Configurar contas de importação e exportação na nuvem](/help/components/locations/configure-import-accounts.md). |

1. Para preencher o formulário para configurar a localização, continue com a seção abaixo que corresponde ao tipo de conta selecionado no [!UICONTROL **Contas de localização**] campo. (Tipos de conta herdada adicionais também estão disponíveis, mas não são recomendados.)

### Amazon S3 Role ARN

Para configurar um local ARN de função do Amazon S3, especifique as seguintes informações:

1. [Começar a criar ou editar um local](#begin-creating-or-editing-a-location), conforme descrito acima.

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Balde**] | O bucket da conta do Amazon S3 para o qual você deseja enviar os dados do Adobe Analytics. <p>Certifique-se de que o ARN do usuário fornecido pelo Adobe tenha o `S3:PutObject` para carregar arquivos nesse bucket. </p><p>Os nomes dos blocos precisam cumprir regras de nomenclatura específicas. Por exemplo, eles precisam conter entre 3 e 63 caracteres, só podem conter letras minúsculas, números, pontos (.) e hifens (-), e precisam começar e terminar com uma letra ou número. [Uma lista completa de regras de nomenclatura está disponível na documentação do AWS](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html). </p> |
   | [!UICONTROL **Prefixo**] | A pasta dentro do bucket onde você deseja inserir os dados. Especifique um nome de pasta e adicione uma barra invertida depois do nome para criar a pasta. Por exemplo, folder_name/ |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

   Agora você pode importar ou exportar dados para ou da conta e do local configurados. Para exportar dados, use [Feeds de dados](/help/export/analytics-data-feed/create-feed.md) ou [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). Para importar dados, use [Conjuntos de classificações](/help/components/classifications/sets/overview.md).

   Os dados importados não são excluídos do destino da nuvem após serem importados.

   >[!NOTE]
   >
   >   Se você usou anteriormente [FTP para importar classificações](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) no Adobe Analytics, era necessário carregar um arquivo FIN. Esse arquivo FIN não é necessário ao importar de contas na nuvem.


### Google Cloud Platform

Para configurar um local da Google Cloud Platform, especifique as seguintes informações:

1. [Começar a criar ou editar um local](#begin-creating-or-editing-a-location), conforme descrito acima.

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Balde**] | O bucket da conta GCP para o qual você deseja que os dados do Adobe Analytics sejam enviados. Verifique se você concedeu permissão ao Principal fornecido pelo Adobe para fazer upload de arquivos para esse bucket. |
   | [!UICONTROL **Prefixo**] | A pasta dentro do bucket onde você deseja inserir os dados. Especifique um nome de pasta e adicione uma barra invertida depois do nome para criar a pasta. Por exemplo, folder_name/ |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

   Agora você pode importar ou exportar dados para ou da conta e do local configurados. Para exportar dados, use [Feeds de dados](/help/export/analytics-data-feed/create-feed.md) ou [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). Para importar dados, use [Conjuntos de classificações](/help/components/classifications/sets/overview.md).

   Os dados importados não são excluídos do destino da nuvem após serem importados.

   >[!NOTE]
   >
   >   Se você usou anteriormente [FTP para importar classificações](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) no Adobe Analytics, era necessário carregar um arquivo FIN. Esse arquivo FIN não é necessário ao importar de contas na nuvem.


### Azure SAS

Para configurar um local do Azure SAS, especifique as seguintes informações:

1. [Começar a criar ou editar um local](#begin-creating-or-editing-a-location), conforme descrito acima.

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Contêiner**] | O container na conta especificada para onde você deseja enviar os dados do Adobe Analytics. |
   | [!UICONTROL **Prefixo**] | A pasta no container onde você deseja inserir os dados. Especifique um nome de pasta e adicione uma barra invertida depois do nome para criar a pasta. Por exemplo, `folder_name/` |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

   Agora você pode importar ou exportar dados para ou da conta e do local configurados. Para exportar dados, use [Feeds de dados](/help/export/analytics-data-feed/create-feed.md) ou [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). Para importar dados, use [Conjuntos de classificações](/help/components/classifications/sets/overview.md).

   Os dados importados não são excluídos do destino da nuvem após serem importados.

   >[!NOTE]
   >
   >   Se você usou anteriormente [FTP para importar classificações](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) no Adobe Analytics, era necessário carregar um arquivo FIN. Esse arquivo FIN não é necessário ao importar de contas na nuvem.


### Azure RBAC

Para configurar um local do Azure RBAC, especifique as seguintes informações:

1. [Começar a criar ou editar um local](#begin-creating-or-editing-a-location), conforme descrito acima.

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Conta**] | A conta de armazenamento do Azure. |
   | [!UICONTROL **Contêiner**] | O container na conta especificada para onde você deseja enviar os dados do Adobe Analytics. Conceda permissões para fazer upload de arquivos para o aplicativo do Azure que você criou anteriormente. |
   | [!UICONTROL **Prefixo**] | A pasta no container onde você deseja inserir os dados. Especifique um nome de pasta e adicione uma barra invertida depois do nome para criar a pasta. Por exemplo, `folder_name/` |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

   Agora você pode importar ou exportar dados para ou da conta e do local configurados. Para exportar dados, use [Feeds de dados](/help/export/analytics-data-feed/create-feed.md) ou [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). Para importar dados, use [Conjuntos de classificações](/help/components/classifications/sets/overview.md).

   Os dados importados não são excluídos do destino da nuvem após serem importados.

   >[!NOTE]
   >
   >   Se você usou anteriormente [FTP para importar classificações](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) no Adobe Analytics, era necessário carregar um arquivo FIN. Esse arquivo FIN não é necessário ao importar de contas na nuvem.

### Email

Para configurar um local de email, especifique as seguintes informações:

1. [Começar a criar ou editar um local](#begin-creating-or-editing-a-location), conforme descrito acima.

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Assunto**] | O assunto da mensagem de email. |
   | [!UICONTROL **Notas**] | O conteúdo da mensagem de email. |

   {style="table-layout:auto"}

1. Selecione [!UICONTROL **Salvar**].

   Agora é possível exportar dados para a conta e o local configurados ao usar o [Feeds de dados](/help/export/analytics-data-feed/create-feed.md). (As localizações de email não são compatíveis com o [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) ou [Conjuntos de classificações](/help/components/classifications/sets/overview.md)).

### Tipos de conta herdada

Esses tipos de conta herdados estão disponíveis somente ao exportar dados com [Feeds de dados](/help/export/analytics-data-feed/create-feed.md) e [Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md). Essas opções não estão disponíveis ao importar dados com o [Conjuntos de classificações](/help/components/classifications/sets/manage/schema.md).

+++FTP

Os dados do feed de dados podem ser entregues a um Adobe ou local FTP hospedado pelo cliente. Especifique o diretório Use o campo de caminho para colocar arquivos de feed em uma pasta.

| Campo | Função |
|---------|----------|
| [!UICONTROL **Caminho do diretório**] | Insira o caminho para o diretório no servidor FTP. As pastas já devem existir; os feeds exibem um erro se o caminho especificado não existir. </br>Por exemplo, `/folder_name/folder_name`. |

{style="table-layout:auto"}

+++

+++SFTP

Os dados do feed de dados podem ser entregues para um Adobe ou local SFTP hospedado pelo cliente. O site de destino deve conter uma chave pública RSA ou DSA válida. Você pode baixar a chave pública apropriada ao criar o feed.

| Campo | Função |
|---------|----------|
| [!UICONTROL **Caminho do diretório**] | Insira o caminho para o diretório no servidor FTP. As pastas já devem existir; os feeds exibem um erro se o caminho especificado não existir. </br>Por exemplo, `/folder_name/folder_name`. |

{style="table-layout:auto"}

+++

+++S3

Você pode enviar dados do warehouse diretamente para buckets do Amazon S3. Este tipo de destino requer um nome de bucket, uma ID de chave de acesso e uma chave secreta. Consulte [Requisitos de nomenclatura de bucket do Amazon S3](https://docs.aws.amazon.com/pt_br/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html) nos documentos do Amazon S3 para obter mais informações.

O usuário fornecido para fazer upload dos dados do data warehouse precisa ter as seguintes [permissões](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html):

* s3:GetObject
* s3:PutObject
* s3:PutObjectAcl

As 16 regiões AWS padrão a seguir são compatíveis (usando o algoritmo de assinatura apropriado, quando necessário):

* us-east-2
* us-east-1
* us-west-1
* us-west-2
* ap-south-1
* ap-northeast-2
* ap-southeast-1
* ap-southeast-2
* ap-northeast-1
* ca-central-1
* eu-central-1
* eu-west-1
* eu-west-2
* eu-west-3
* eu-north-1
* sa-east-1

>[!NOTE]
>
>A região cn-north-1 não é compatível.

+++

+++Blob do Azure

O data warehouse é compatível com destinos do Azure Blob. Requer um contêiner, uma conta e uma chave. A Amazon criptografa automaticamente os dados em repouso. Os dados são descriptografados automaticamente ao baixá-los. Consulte [Criar uma conta de armazenamento](https://docs.microsoft.com/pt-br/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) nos documentos do Microsoft Azure para obter mais informações.

>[!NOTE]
>
>Você deve implementar seu próprio processo para gerenciar o espaço em disco no destino do data warehouse. A Adobe não exclui dados do servidor.

+++


