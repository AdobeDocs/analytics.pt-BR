---
description: Etapas que descrevem como criar uma solicitação do data warehouse.
title: Configurar um destino de relatório para uma solicitação do data warehouse
feature: Data Warehouse
exl-id: 3c7faea3-4d90-4274-88f3-e9337c94155f
source-git-commit: b960aaa60569d65cb8501cf041341a3a132929b1
workflow-type: tm+mt
source-wordcount: '2584'
ht-degree: 85%

---

# Configurar um destino de relatório para uma solicitação do data warehouse

Há várias opções de configuração disponíveis ao criar uma solicitação do data warehouse. As informações a seguir descrevem como configurar um destino de relatório para a solicitação.

Para obter informações sobre como começar a criar uma solicitação, bem como links para outras opções de configuração importantes, consulte [Criar uma solicitação do data warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

>[!NOTE]
>
>Considere o seguinte ao configurar um destino de relatório:
>
>* Recomendamos o uso de uma conta na nuvem ou de um email como destino do seu relatório. [Contas FTP e SFTP herdadas](#legacy-destinations) estão disponíveis, mas não são recomendadas.
>
>* Todas as contas em nuvem configuradas anteriormente estão disponíveis para uso no Data Warehouse. Você pode configurar contas em nuvem de qualquer uma das seguintes maneiras:
>
>   * Ao configurar [Feeds de dados](/help/export/analytics-data-feed/create-feed.md)
>   
>   * Quando [importação de dados de classificação do Adobe Analytics](/help/components/locations/locations-manager.md) (Contas podem ser usadas, mas os locais configurados nessas contas não podem ser usados.)
>   
>   * No Gerenciador de locais, em [Componentes > Locais](/help/components/locations/configure-import-accounts.md).
>
>* As contas em nuvem estão associadas à sua conta de usuário do Adobe Analytics. Outros usuários não podem usar ou exibir contas na nuvem configuradas por você.
>
>* É possível editar quaisquer locais criados no Gerenciador de locais em [Componentes > Locais](/help/components/locations/configure-import-accounts.md)

Configure o destino para o qual enviar os relatórios do data warehouse.

1. Caso ainda não o tenha feito, crie uma solicitação no Adobe Analytics selecionando **[!UICONTROL Ferramentas]** > **[!UICONTROL Data warehouse]** > [!UICONTROL **Adicionar**].

   Para obter detalhes adicionais, consulte [Criar uma solicitação do data warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Na página Nova solicitação do data warehouse, selecione a guia [!UICONTROL **Destino do relatório**].

   ![Guia Destino do relatório](assets/dw-report-destination.png)

1. (Condicional) Se uma conta da nuvem (e um destino nessa conta) já tiver sido configurada no Adobe Analytics, você poderá usá-la como destino do relatório:

   >[!NOTE]
   >
   >As contas estão disponíveis somente se você as tiver configurado ou se tiverem sido compartilhadas com uma organização da qual você faz parte.
   >
   >Se você for um administrador do sistema, a variável [!UICONTROL **Mostrar todos os destinos**] está disponível. Habilite essa opção se desejar ter acesso a todas as contas e locais que foram criados por qualquer usuário na organização.

   1. Selecione a conta no menu suspenso [!UICONTROL **Selecionar conta**].

      Todas as contas em nuvem configuradas em qualquer uma das seguintes áreas do Adobe Analytics estão disponíveis para uso:

      * Ao importar dados de classificação do Adobe Analytics, conforme descrito em [Esquema](/help/components/classifications/sets/manage/schema.md).

        No entanto, os locais configurados para a importação de dados de classificação não podem ser usados. Em vez disso, adicione um novo destino, conforme descrito abaixo.

      * Ao configurar contas e locais na área Locais, conforme descrito em [Configurar contas de importação e exportação na nuvem](/help/components/locations/configure-import-accounts.md) e [Configurar locais de importação e exportação na nuvem](/help/components/locations/configure-import-locations.md).

   1. Selecione o destino associado à conta no menu suspenso [!UICONTROL **Selecionar destino**]. <!-- Is this correct? -->

1. (Condicional) Se você não tiver acesso a uma conta da nuvem já configurada no Adobe Analytics, será possível configurar uma:

   1. Selecione [!UICONTROL **Adicionar conta**] e especifique as seguintes informações:

      | Campo | Função |
      |---------|----------|
      | [!UICONTROL **Tipo de conta**] | Selecione o tipo de conta na nuvem. Recomendamos ter uma única conta de cada tipo, com os vários locais necessários contidos nessa conta. <p>Depois de escolher um tipo de conta, aparecerão campos específicos para esse tipo de conta. </p> |
      | [!UICONTROL **Nome da conta**] | Especifique um nome para a conta. Esse nome aparece ao criar um local. <!-- true? --> |
      | [!UICONTROL **Descrição da conta**] | Forneça uma breve descrição da conta para ajudar a diferenciá-la de outras contas do mesmo tipo. |

      Para obter instruções de configuração, expanda a seção abaixo que corresponde ao [!UICONTROL **Tipo de conta**] que você selecionou.

      Use qualquer um dos tipos de conta a seguir ao configurar um destino de relatório. Para obter instruções de configuração, expanda o tipo de conta. ([Destinos herdados](#legacy-destinations) adicionais também estão disponíveis, mas não são recomendados.)

      +++Amazon S3

      Para configurar uma conta ARN com a função S3 do Amazon, especifique as seguintes informações:

      | Campo | Função |
      |---------|----------|
      | [!UICONTROL **ARN de função**] | Você deve fornecer um ARN (Amazon Resource Name) de função que a Adobe possa usar para obter acesso à conta do Amazon S3. Para fazer isso, crie uma política de permissão IAM para a conta de origem, anexe a política a um usuário e crie uma função para a conta de destino. Para obter informações específicas, consulte [esta documentação do AWS](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/).<p>Para obter informações sobre como configurar a permissão do bucket, consulte o artigo [Como fornecer acesso entre contas a objetos que estão nos buckets do Amazon S3?](https://repost.aws/knowledge-center/cross-account-access-s3) no centro de conhecimento da Amazon. |
      | [!UICONTROL **ARN de usuário**] | O ARN (Amazon Resource Name) de usuário é fornecido pela Adobe. É preciso anexar este usuário à política que você criou. |

      {style="table-layout:auto"}

+++

      +++Google Cloud Platform

      Para configurar uma conta da Google Cloud Platform, especifique as seguintes informações:

      | Campo | Função |
      |---------|----------|
      | [!UICONTROL **ID do projeto**] | Sua ID de projeto da Google Cloud. Consulte a [documentação da Google Cloud sobre como obter uma ID de projeto](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

      {style="table-layout:auto"}

+++

      +++Azure SAS

      Para configurar uma conta SAS do Azure, especifique as seguintes informações:

      | Campo | Função |
      |---------|----------|
      | [!UICONTROL **ID do aplicativo**] | Copie essa ID do aplicativo do Azure que você criou. No Microsoft Azure, essas informações se localizam na guia **Visão geral** do aplicativo. Para obter mais informações, consulte a [documentação do Microsoft Azure sobre como registrar um aplicativo na plataforma de identidade da Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **ID do locatário**] | Copie essa ID do aplicativo do Azure que você criou. No Microsoft Azure, essas informações se localizam na guia **Visão geral** do aplicativo. Para obter mais informações, consulte a [documentação do Microsoft Azure sobre como registrar um aplicativo na plataforma de identidade da Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **URI do cofre de chaves**] | <p>O caminho para o token SAS no cofre de chaves do Azure.  Para configurar o Azure SAS, você precisa armazenar um token SAS como um segredo usando o cofre de chaves do Azure. Para obter informações, consulte a [documentação do Microsoft Azure sobre como definir e recuperar um segredo do cofre de chaves do Azure](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Depois que o URI do cofre de chaves for criado:<ul><li>Adicione uma política de acesso no cofre de chaves para conceder permissão ao aplicativo do Azure que você criou.</li><li>Verifique se a ID do aplicativo recebeu a função integrada `Key Vault Certificate User` para acessar o URI do cofre de chaves.</br><p>Para obter mais informações, consulte [Funções integradas do Azure](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles).</p></li></ul><p>Para obter informações, consulte a [documentação do Microsoft Azure sobre como atribuir uma política de acesso do cofre de chaves](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
      | [!UICONTROL **Nome secreto do cofre de chaves**] | O nome secreto que você criou ao adicionar o segredo ao cofre de chaves do Azure. No Microsoft Azure, essas informações se localizam no cofre de chaves que você criou, nas páginas de configurações do **cofre de chaves**. Para obter mais informações, consulte a [documentação do Microsoft Azure sobre como definir e recuperar um segredo do cofre de chaves do Azure](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
      | [!UICONTROL **Segredo**] | Copie o segredo do aplicativo do Azure que você criou. No Microsoft Azure, essas informações se localizam na guia **Certificados e segredos** do aplicativo. Para obter mais informações, consulte a [documentação do Microsoft Azure sobre como registrar um aplicativo na plataforma de identidade da Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

+++

      +++Azure RBAC

      Para configurar uma conta RBAC do Azure, especifique as seguintes informações:

      | Campo | Função |
      |---------|----------|
      | [!UICONTROL **ID do aplicativo**] | Copie essa ID do aplicativo do Azure que você criou. No Microsoft Azure, essas informações se localizam na guia **Visão geral** do aplicativo. Para obter mais informações, consulte a [documentação do Microsoft Azure sobre como registrar um aplicativo na plataforma de identidade da Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **ID do locatário**] | Copie essa ID do aplicativo do Azure que você criou. No Microsoft Azure, essas informações se localizam na guia **Visão geral** do aplicativo. Para obter mais informações, consulte a [documentação do Microsoft Azure sobre como registrar um aplicativo na plataforma de identidade da Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **Segredo**] | Copie o segredo do aplicativo do Azure que você criou. No Microsoft Azure, essas informações se localizam na guia **Certificados e segredos** do aplicativo. Para obter mais informações, consulte [documentação do Microsoft Azure sobre como registrar um aplicativo na plataforma de identidade da Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

+++

      +++Email

      Para configurar uma conta de email, especifique as seguintes informações:

      | Campo | Função |
      |---------|----------|
      | [!UICONTROL **Destinatários**] | É possível enviar notificações por email a usuários específicos quando o relatório é enviado. Especifique um único endereço de email ou uma lista separada por vírgulas de endereços de email. <!-- How does this differ from the Notification email tab? --> |

   1. Selecione [!UICONTROL **Adicionar localização**] e especifique as seguintes informações: 
|Campo | Função |
|---------|----------|
| [!UICONTROL **Nome**] | O nome do local.    | 
| [!UICONTROL **Descrição**] | Forneça uma breve descrição da conta para ajudar a diferenciá-la de outras contas do mesmo tipo. | 
| [!UICONTROL **Conta de localização**] | Selecione a conta de localização que você criou em [Adicionar uma conta](#add-an-account). |

   1. Na seção [!UICONTROL **Propriedades da localização**], insira as informações específicas ao tipo da sua conta de localização.

      Para obter instruções de configuração, expanda a seção abaixo que corresponde ao [!UICONTROL **Tipo de conta**] que você selecionou anteriormente.

      +++Amazon S3

      Para configurar um local do Amazon S3, especifique as seguintes informações:

      | Campo | Função |
      |---------|----------|
      | [!UICONTROL **Nome do bucket**] | O bucket da conta do Amazon S3 para o qual você deseja enviar os dados do Adobe Analytics. <p>Certifique-se de que o ARN de usuário fornecido pela Adobe contenha a permissão `S3:PutObject` para fazer upload de arquivos nesse bucket. Esta permissão possibilita que o ARN de usuário faça upload dos arquivos iniciais e sobrescreva arquivos em uploads subsequentes.</p><p>Os nomes dos buckets devem atender às regras de nomenclatura específicas. Por exemplo, eles devem ter entre 3 e 63 caracteres de comprimento, podem consistir apenas de letras minúsculas, números, pontos (.) e hifens (-) e devem começar e terminar com uma letra ou número. [Uma lista completa de regras de nomenclatura está disponível na documentação do AWS](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html). </p> |
      | [!UICONTROL **Prefixo da chave**] | A pasta dentro do bucket onde você deseja inserir os dados. Especifique um nome de pasta e adicione uma barra invertida depois do nome para criar a pasta. Por exemplo, folder_name/ |

      {style="table-layout:auto"}

+++

      +++Google Cloud Platform

      Para configurar um local da Google Cloud Platform, especifique as seguintes informações:

      | Campo | Função |
      |---------|----------|
      | [!UICONTROL **Nome do bucket**] | O bucket da conta da GCP para o qual você deseja enviar os dados do Adobe Analytics. <p>Certifique-se de conceder uma das seguintes permissões ao principal fornecido pela Adobe:<ul><li>`roles/storage.objectCreator`: use essa permissão se desejar limitar o principal a criar arquivos somente em sua conta da GCP. </br>**Importante:** se você usar essa permissão com relatórios agendados, deverá usar um nome de arquivo único para cada nova exportação agendada. Caso contrário, ocorrerá uma falha na geração do relatório, pois o principal não terá permissão para sobrescrever os arquivos existentes.</li><li>`roles/storage.objectUser`: use essa permissão se desejar que o principal tenha acesso para exibir, listar, atualizar e excluir arquivos na sua conta da GCP.</br>Essa permissão possibilita que o principal sobrescreva arquivos existentes em uploads subsequentes, sem a necessidade de gerar automaticamente nomes de arquivo únicos para cada nova exportação agendada.</li></ul><p>Para obter informações sobre a concessão de permissões, consulte [Adicionar um principal a uma política de nível de bucket](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) na documentação da Google Cloud.</p> |
      | [!UICONTROL **Prefixo da chave**] | A pasta dentro do bucket onde você deseja inserir os dados. Especifique um nome de pasta e adicione uma barra invertida depois do nome para criar a pasta. Por exemplo, folder_name/ |

      {style="table-layout:auto"}

+++

      +++Azure SAS

      Para configurar um local SAS do Azure, especifique as seguintes informações:

      | Campo | Função |
      |---------|----------|
      | [!UICONTROL **Nome do container**] | O container na conta especificada para onde você deseja enviar os dados do Adobe Analytics. |
      | [!UICONTROL **Prefixo da chave**] | A pasta no container onde você deseja inserir os dados. Especifique um nome de pasta e adicione uma barra invertida depois do nome para criar a pasta. Por exemplo, `folder_name/`<p>Verifique se o armazenamento de tokens SAS que você especificou no campo Nome secreto do cofre de chaves ao configurar a conta do Azure SAS possui a permissão `Write`. Isso permite que o token SAS crie arquivos no container do Azure. <p>Se desejar que o token SAS também sobrescreva arquivos, verifique se o armazenamento de token SAS possui a permissão `Delete`.</p><p>Para obter mais informações, consulte [Recursos de armazenamento de blobs](https://learn.microsoft.com/en-us/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources) na documentação do Armazenamento Azure Blob.</p> |

      {style="table-layout:auto"}

+++

      +++Azure RBAC

      Para configurar um local do RBAC do Azure, especifique as seguintes informações:

      | Campo | Função |
      |---------|----------|
      | [!UICONTROL **Nome do container**] | O container na conta especificada para onde você deseja enviar os dados do Adobe Analytics. Conceda permissões para fazer upload de arquivos para o aplicativo do Azure que você criou anteriormente. |
      | [!UICONTROL **Prefixo de chave**] | A pasta no container onde você deseja inserir os dados. Especifique um nome de pasta e adicione uma barra invertida depois do nome para criar a pasta. Por exemplo, `folder_name/`<p>Verifique se a ID do aplicativo que você especificou ao configurar a conta do Azure RBAC recebeu a função `Storage Blob Data Contributor` para acessar o container (pasta).</p> <p>Para obter mais informações, consulte [Funções integradas do Azure](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles).</p> |
      | [!UICONTROL **Nome da conta**] | A conta de armazenamento do Azure. |

      {style="table-layout:auto"}

+++

1. Continue configurando sua solicitação do data warehouse na guia [!UICONTROL **Opções de relatório**]. Para obter mais informações, consulte [Configurar opções de relatório para uma solicitação do data warehouse](/help/export/data-warehouse/create-request/dw-request-report-options.md).

## Destinos herdados

>[!IMPORTANT]
>
>Os destinos descritos nesta seção são herdados e não são recomendados. Em vez disso, use um dos seguintes destinos ao criar um destino do data warehouse: Amazon S3, Google Cloud Platform, Azure RBAC, Azure SAS ou Email. Consulte as informações acima para obter detalhes sobre cada um desses destinos recomendados.

As informações a seguir fornecem informações de configuração para cada um dos destinos herdados:

### FTP

Os dados do data warehouse podem ser entregues em um local FTP da Adobe ou hospedado pelo cliente. Requer um host FTP, nome de usuário e senha. Use o campo de caminho para colocar arquivos de feed em uma pasta. As pastas já devem existir; os feeds exibem um erro se o caminho especificado não existir.

Use as seguintes informações ao preencher os campos disponíveis:

#### Campos da conta

* [!UICONTROL **Nome da conta**]: o nome da conta FTP.

* [!UICONTROL **Descrição da conta**]: uma descrição da conta FTP.

* [!UICONTROL **Nome do host**]: insira o URL de destino do FTP desejado. Por exemplo, `ftp.company.com`.

  >[!NOTE]
  >
  >  Não inclua `ftp://` no início do URL.

* [!UICONTROL **Nome de usuário**]: digite o nome de usuário para fazer logon no site FTP.

* [!UICONTROL **Senha e confirmação de senha**]: digite a senha para fazer logon no site FTP.

#### Campos de local

* [!UICONTROL **Nome do local**]: o nome do local na conta FTP para o qual você deseja enviar os arquivos.

* [!UICONTROL **Descrição do local**]: uma descrição do local na conta FTP.

* [!UICONTROL **Caminho do diretório**]: o caminho para o local na conta FTP.

### SFTP

O SFTP é compatível com o data warehouse. Isso exige que um host SFTP, nome de usuário e site de destino contenham uma chave pública RSA ou DSA válida. Você pode baixar a chave pública apropriada ao criar o destino do data warehouse.

Use as seguintes informações ao preencher os campos disponíveis:

#### Campos da conta

* [!UICONTROL **Nome da conta**]: o nome da conta FTP.

* [!UICONTROL **Descrição da conta**]: uma descrição da conta FTP.

* [!UICONTROL **Nome do host**]: insira o URL de destino do SFTP desejado. Por exemplo, `sftp.company.com`.

  >[!NOTE]
  >
  >  Não inclua `sftp://` no início do URL.

* [!UICONTROL **Nome de usuário**]: digite o nome de usuário para fazer logon no site SFTP.

* [!UICONTROL **Usar extensões de arquivo temporárias durante o upload**]: quando habilitada, a extensão de arquivo `.part` é usada durante o processo de upload. Mantenha essa opção habilitada, a menos que o servidor SFTP proíba a alteração de nomes dos arquivos após a conclusão do upload.

* [!UICONTROL **Chaves públicas**]: baixe a chave pública apropriada ao criar o destino do data warehouse.

#### Campos de local

* [!UICONTROL **Nome do local**]: o nome do local na conta SFTP para o qual você deseja enviar os arquivos.

* [!UICONTROL **Descrição do local**]: uma descrição do local na conta SFTP.

* [!UICONTROL **Caminho do diretório**]: o caminho para o local na conta SFTP.

Para obter informações adicionais sobre a configuração de SFTP, consulte [Enviar solicitações do data warehouse para servidores SFTP](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md).

### S3

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

### Azure Blob

O data warehouse é compatível com destinos do Azure Blob. Requer um contêiner, uma conta e uma chave. A Amazon criptografa automaticamente os dados em repouso. Os dados são descriptografados automaticamente ao baixá-los. Consulte [Criar uma conta de armazenamento](https://docs.microsoft.com/pt-br/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) nos documentos do Microsoft Azure para obter mais informações.

>[!NOTE]
>
>Você deve implementar seu próprio processo para gerenciar o espaço em disco no destino do data warehouse. A Adobe não exclui dados do servidor.
