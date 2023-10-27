---
description: Configurar a conta de importação na nuvem e o local onde os dados de classificação podem ser carregados
keywords: Analysis Workspace
title: Configurar locais de importação na nuvem
feature: Classifications
exl-id: 55179868-6228-44ff-835c-f4a7b38e929b
source-git-commit: f71b80dce9d447c431130901d86947d23e28d378
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 7%

---

# Configurar locais de importação na nuvem

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

Antes de importar os dados de classificação do Adobe Analytics de um destino na nuvem, é necessário adicionar e configurar a conta e o local dentro dessa conta onde deseja que os dados de classificação sejam coletados.

Esse processo consiste em adicionar e configurar a conta (como a Função ARN do Amazon S3, a Plataforma da Google Cloud e assim por diante) e o local dentro da conta (como uma pasta dentro da conta).

Para configurar um local de importação na nuvem:

1. É necessário adicionar uma conta antes de adicionar um local. Caso ainda não o tenha feito, adicione uma conta conforme descrito em [Configurar contas de importação na nuvem](/help/components/locations/configure-import-accounts.md).
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
   | [!UICONTROL **Nome do bucket**] | O bucket da conta do Amazon S3 para o qual você deseja que os dados do Adobe Analytics sejam enviados. |
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

   Agora é possível importar dados da conta e do local configurados.

   Os dados não são excluídos do destino da nuvem após serem importados.

   >[!NOTE]
   >
   >   Se você usou anteriormente [FTP para importar classificações](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) no Adobe Analytics, era necessário carregar um arquivo FIN. Esse arquivo FIN não é necessário ao importar de contas na nuvem.

