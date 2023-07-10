---
description: Configurar a conta de importação na nuvem e o local onde os dados de classificação podem ser carregados
keywords: Analysis Workspace
title: Configurar locais de importação na nuvem
feature: Classifications
source-git-commit: 8d6ee33e867da274334c8adc557105af4942c894
workflow-type: tm+mt
source-wordcount: '1356'
ht-degree: 6%

---

# Configurar locais de importação na nuvem

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

Antes de importar os dados de classificação do Adobe Analytics de um destino na nuvem, é necessário adicionar e configurar o local onde deseja que os dados de classificação sejam coletados.

Esse processo consiste em adicionar e configurar a conta (como a Função ARN do Amazon S3, a Plataforma da Google Cloud e assim por diante) e o local dentro da conta (como uma pasta dentro da conta).

## Adicionar uma conta

É necessário configurar o Adobe Analytics com as informações necessárias para acessar a conta de destino da nuvem.

1. No Adobe Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Localizações**].
1. No [!UICONTROL Localizações] selecione a [!UICONTROL **Credenciais de localização**] guia.
1. Selecionar [!UICONTROL **Adicionar conta**]. <!-- add screenshot? -->

   A caixa de diálogo Add account (Adicionar conta) é exibida.
1. Especifique as seguintes informações: |Campo | Função | |—|—| | [!UICONTROL **Nome da conta de localização**] | O nome da conta de localização. Este nome aparece ao criar um local | | [!UICONTROL **Descrição da conta de localização**] | Forneça uma breve descrição da conta para ajudar a diferenciá-la de outras contas do mesmo tipo. | | [!UICONTROL **Tipo de conta**] | Selecione o tipo de conta na nuvem. Recomendamos ter uma única conta para cada tipo, com vários locais conforme necessário dentro dessa conta. |
1. No [!UICONTROL **Propriedades da conta**] especifique as informações específicas ao tipo de conta selecionado.

   Para obter instruções de configuração, expanda a seção abaixo que corresponde à variável [!UICONTROL **Tipo de conta**] selecionado.

   +++Amazon S3 Role ARN

   Especifique as seguintes informações para configurar uma conta ARN da Função S3 do Amazon:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Função ARN**] | Você deve fornecer uma Função ARN (Amazon Resource Name) que o Adobe pode usar para obter acesso à conta do Amazon S3. Para fazer isso, crie uma política de permissão IAM para a conta de origem, anexe a política a um usuário e crie uma função para a conta de destino. Para obter informações específicas, consulte [esta documentação do AWS](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
   | [!UICONTROL **ARN do usuário**] | O usuário ARN (Amazon Resource Name) é fornecido pelo Adobe. Você deve anexar este usuário à política criada. |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   Especifique as seguintes informações para configurar uma conta da Google Cloud Platform:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **ID do projeto**] | Sua ID de projeto da Google Cloud. Consulte a [Documentação da Google Cloud sobre como obter uma ID de projeto](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

   {style="table-layout:auto"}

+++

   +++Azure SAS

   Especifique as seguintes informações para configurar uma conta SAS do Azure:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **ID do aplicativo**] | Copie essa ID do aplicativo do Azure que você criou. No Microsoft Azure, essas informações estão localizadas no **Visão geral** no aplicativo. Para obter mais informações, consulte [Documentação do Microsoft Azure sobre como registrar um aplicativo na Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **ID do locatário**] | Copie essa ID do aplicativo do Azure que você criou. No Microsoft Azure, essas informações estão localizadas no **Visão geral** no aplicativo. Para obter mais informações, consulte [Documentação do Microsoft Azure sobre como registrar um aplicativo na Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **URI do cofre de chaves**] | <p>O caminho para o token SAS no Cofre de Chaves do Azure.  Para configurar o Azure SAS, você precisa armazenar um token SAS como um segredo usando o Cofre de Chaves do Azure. Para obter informações, consulte a [Documentação do Microsoft Azure sobre como definir e recuperar um segredo do Cofre de Chaves do Azure](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Depois que o URI do cofre de chaves for criado, adicione uma política de acesso ao Cofre de Chaves para conceder permissão ao aplicativo do Azure que você criou. Para obter informações, consulte a [Documentação do Microsoft Azure sobre como atribuir uma política de acesso do Cofre da Chave](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
   | [!UICONTROL **Nome secreto do cofre de chaves**] | O nome secreto que você criou ao adicionar o segredo ao Cofre de Chaves do Azure. No Microsoft Azure, essas informações estão localizadas no Cofre de Chaves que você criou, na **Cofre da Chave** páginas de configurações. Para obter informações, consulte a [Documentação do Microsoft Azure sobre como definir e recuperar um segredo do Cofre de Chaves do Azure](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **Segredo da conta de localização**] | Copie o segredo do aplicativo do Azure que você criou. No Microsoft Azure, essas informações estão localizadas no **Certificados e segredos** no aplicativo. Para obter mais informações, consulte [Documentação do Microsoft Azure sobre como registrar um aplicativo na Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   Especifique as seguintes informações para configurar uma conta RBAC do Azure:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **ID do aplicativo**] | Copie essa ID do aplicativo do Azure que você criou. No Microsoft Azure, essas informações estão localizadas no **Visão geral** no aplicativo. Para obter mais informações, consulte [Documentação do Microsoft Azure sobre como registrar um aplicativo na Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **ID do locatário**] | Copie essa ID do aplicativo do Azure que você criou. No Microsoft Azure, essas informações estão localizadas no **Visão geral** no aplicativo. Para obter mais informações, consulte [Documentação do Microsoft Azure sobre como registrar um aplicativo na Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Segredo da conta de localização**] | Copie o segredo do aplicativo do Azure que você criou. No Microsoft Azure, essas informações estão localizadas no **Certificados e segredos** no aplicativo. Para obter mais informações, consulte [Documentação do Microsoft Azure sobre como registrar um aplicativo na Microsoft identity platform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

+++

1. Selecione [!UICONTROL **Salvar**].

1. Continuar com [Adicionar uma localização](#add-a-location).

## Adicionar uma localização

1. É necessário adicionar uma conta antes de adicionar um local. [Adicionar uma conta](#add-an-account) se você ainda não tiver feito.
1. No Adobe Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Localizações**].
1. No [!UICONTROL Localizações] selecione a [!UICONTROL **Localizações**] guia.
1. Selecionar [!UICONTROL **Adicionar localização**]. <!-- add screenshot? -->

   A caixa de diálogo Local é exibida.
1. Especifique as seguintes informações: |Campo | Função | |—|—| | [!UICONTROL **Nome**] | O nome do local.  | | [!UICONTROL **Descrição**] | Forneça uma breve descrição da conta para ajudar a diferenciá-la de outras contas do mesmo tipo. | | [!UICONTROL **Conta de localização**] | Selecione a conta de localização na qual você criou [Adicionar uma conta](#add-an-account). |

1. No [!UICONTROL **Propriedades do local**] especifique as informações específicas ao tipo de conta da sua conta de localização.

   Para obter instruções de configuração, expanda a seção abaixo que corresponde ao tipo de conta selecionado em [!UICONTROL **Contas de localização**] campo.

   +++Amazon S3 Role ARN

   Especifique as seguintes informações para configurar um local ARN de Função do Amazon S3:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Nome do bucket**] | O bucket da conta do Amazon S3 para o qual você deseja que os dados do Adobe Analytics sejam enviados. Certifique-se de que o usuário ARN fornecido pelo Adobe tenha acesso para carregar arquivos nesse bucket. |
   | [!UICONTROL **Prefixo da chave**] | A pasta dentro do bucket onde você deseja colocar os dados. Especifique um nome de pasta e adicione uma barra invertida depois do nome para criar a pasta. Por exemplo, folder_name/ |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   Especifique as seguintes informações para configurar um local da Google Cloud Platform:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Nome do bucket**] | O bucket da conta GCP para o qual você deseja que os dados do Adobe Analytics sejam enviados. Verifique se você concedeu permissão ao Principal fornecido pelo Adobe para fazer upload de arquivos para esse bucket. |
   | [!UICONTROL **Prefixo da chave**] | A pasta dentro do bucket onde você deseja colocar os dados. Especifique um nome de pasta e adicione uma barra invertida depois do nome para criar a pasta. Por exemplo, folder_name/ |

   {style="table-layout:auto"}

+++

   +++Azure SAS

   Especifique as seguintes informações para configurar um local SAS do Azure:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Nome do container**] | O container na conta especificada para onde você deseja que os dados do Adobe Analytics sejam enviados. |
   | [!UICONTROL **Prefixo da chave**] | A pasta no container onde você deseja colocar os dados. Especifique um nome de pasta e adicione uma barra invertida depois do nome para criar a pasta. Por exemplo, `folder_name/` |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   Especifique as seguintes informações para configurar um local do Azure RBAC:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Nome do container**] | O container na conta especificada para onde você deseja que os dados do Adobe Analytics sejam enviados. Conceda permissões para carregar arquivos para o aplicativo do Azure criado anteriormente. |
   | [!UICONTROL **Prefixo da chave**] | A pasta no container onde você deseja colocar os dados. Especifique um nome de pasta e adicione uma barra invertida depois do nome para criar a pasta. Por exemplo, `folder_name/` |
   | [!UICONTROL **Nome da conta**] | A conta de armazenamento do Azure. |

   {style="table-layout:auto"}

+++

1. Selecione [!UICONTROL **Salvar**].

   Agora é possível importar dados para a conta e o local configurados.