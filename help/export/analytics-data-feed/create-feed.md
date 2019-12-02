---
title: Criar ou editar um feed de dados
description: Saiba como criar ou editar um feed de dados.
translation-type: tm+mt
source-git-commit: 7db88bce7b3d0f90fa5b50664d7c0c23904348c0

---


# Criar ou editar um feed de dados

A criação de um feed de dados permite que a Adobe saiba onde enviar arquivos de dados brutos e o que você deseja incluir em cada arquivo. Esta página lista configurações individuais que você pode personalizar ao criar um feed de dados.

O conhecimento básico dos feeds de dados é recomendado antes da leitura desta página. Consulte Visão geral [dos feeds de](data-feed-overview.md) dados para verificar se você atende aos requisitos para criar um feed de dados.

## Campos de informações do feed

* **Nome**: O nome do feed de dados. Deve ser único no conjunto de relatórios selecionado e pode ter até 255 caracteres.
* **** Conjunto de relatórios: O conjunto de relatórios no qual o feed de dados se baseia. Se vários feeds de dados forem criados para o mesmo conjunto de relatórios, eles deverão ter definições de colunas diferentes. Somente conjuntos de relatórios de origem oferecem suporte para feeds de dados; conjuntos de relatórios virtuais não são suportados.
* **Enviar email ao concluir**: O endereço de email a ser notificado quando um feed terminar o processamento. O endereço de email deve estar formatado corretamente.
* **Intervalo** do feed: Os feeds por hora contêm dados de uma hora. Os feeds diários contêm dados de um dia inteiro.
* **Atraso no processamento**: Aguarde um determinado tempo antes de processar um arquivo de feed de dados. Um atraso pode ser útil para dar às implementações móveis uma oportunidade para que os dispositivos offline entrem online e enviem dados. Ele também pode ser usado para acomodar os processos do lado do servidor de sua organização no gerenciamento de arquivos processados anteriormente. Na maioria dos casos, não é necessário retardar. Um feed pode ser atrasado em até 120 minutos.
* **Datas** de início e término: A data de início indica a primeira data em que você deseja um feed de dados. Defina essa data no passado para iniciar imediatamente o processamento de feeds de dados para dados históricos. Os feeds continuam a ser processados até atingirem a data de término.
* **Alimentação** contínua: Essa caixa de seleção remove a data de término, permitindo que um feed seja executado indefinidamente. Quando um feed terminar de processar dados históricos, um feed aguarda que os dados terminem de coletar por uma determinada hora ou dia. Quando a hora ou o dia atual terminar, o processamento começará após o atraso especificado.

## Campos de destino

Os campos disponíveis nos campos de destino dependem do tipo de destino.

### FTP

Os dados do feed de dados podem ser entregues para um local FTP hospedado na Adobe ou no cliente. Requer um host FTP, nome de usuário e senha. Use o campo path para colocar arquivos de feed em uma pasta. As pastas já devem existir; os feeds exibem um erro se o caminho especificado não existir.

![Informações FTP](assets/dest-ftp.jpg)

### SFTP

O suporte SFTP para feeds de dados está disponível. Exige que um host SFTP, nome de usuário e site de destino contenham uma chave pública RSA ou DSA válida. Você pode baixar a chave pública apropriada ao criar o feed.

![Informações do SFTP](assets/dest-sftp.jpg)

### S3

Você pode enviar feeds diretamente para o Amazon S3 buckets. Requer um nome de bucket, uma ID de chave de acesso e uma chave secreta. Consulte Requisitos [de nomenclatura de bucket do](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html) Amazon S3 nos documentos do Amazon S3 para obter mais informações.

![Informações de S3](assets/dest-s3.jpg)

As 11 regiões AWS padrão a seguir são suportadas (usando o algoritmo de assinatura apropriado, quando necessário):

* us-east-1
* us-west-1
* us-west-2
* ap-south-1
* ap-northeast-2
* ap-southeast-1
* ap-southeast-2
* ap-northeast-1
* eu-central-1
* eu-west-1
* sa-east-1

> [!NOTE] A região cn-norte-1 não é suportada.

### Azure Blob

Os feeds de dados suportam destinos Blob do Azure. Requer um contêiner, uma conta e uma chave. A Amazon automaticamente criptografa os dados em repouso. Os dados são descriptografados automaticamente ao baixá-los. Consulte [Criar uma conta](https://docs.microsoft.com/en-us/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) de armazenamento nos documentos do Microsoft Azure para obter mais informações.

![Informações do Azure](assets/azure.png)

> [!NOTE] Você deve implementar seu próprio processo para gerenciar o espaço em disco no destino do feed. A Adobe não exclui dados do servidor.

## Definições da coluna de dados

Todas as colunas, independentemente de terem dados, estão disponíveis. Um feed de dados deve incluir pelo menos uma coluna.

* **Remover caracteres** de escape: Ao coletar dados, alguns caracteres (como novas linhas) podem causar problemas. Marque essa caixa se desejar que esses caracteres sejam removidos dos arquivos de feed.
* **Formato** de compactação: O tipo de compactação usado. O Gzip gera arquivos no `.tar.gz` formato. O Zip gera arquivos no `.zip` formato.
* **Tipo** de empacotamento: Um único arquivo gera o arquivo `hit_data.tsv` em um único arquivo, potencialmente massivo. Vários arquivos paginam seus dados em blocos de 2 GB (descompactados). Se vários arquivos forem selecionados e os dados descompactados para a janela de relatório forem menores que 2 GB, um arquivo será enviado. A Adobe recomenda usar vários arquivos para a maioria dos feeds de dados.
* **Modelos** de colunas: Ao criar muitos feeds de dados, a Adobe recomenda criar um modelo de coluna. A seleção de um modelo de coluna inclui automaticamente as colunas especificadas no modelo. A Adobe também fornece vários modelos por padrão.
* **Colunas** disponíveis: Todas as colunas de dados disponíveis no Adobe Analytics. Clique em [!UICONTROL Adicionar tudo] para incluir todas as colunas em um feed de dados.
* **Colunas** incluídas: As colunas a serem incluídas em um feed de dados. Clique em [!UICONTROL Remover tudo] para remover todas as colunas de um feed de dados.
* **Baixar CSV**: Faz o download de um arquivo CSV contendo todas as colunas incluídas.
