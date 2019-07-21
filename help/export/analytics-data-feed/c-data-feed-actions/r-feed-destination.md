---
description: A seção de Destino do feed define como o feed é distribuído.
keywords: Feed de dados; feed; destino; sftp; s 3; ftp; configurações
seo-description: A seção de Destino do feed define como o feed é distribuído.
seo-title: Destino do feed
solution: Analytics
title: Destino do feed
uuid: 4 a 59 e 8 de-e 7 a 6-4 f 7 a-bf 42-db 7 d 59 e 61 b 4 c
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Destino do feed

A seção de Destino do feed define como o feed é distribuído.

Há quatro canais de distribuição:

* FTP
* SFTP
* Amazon S3
* Azure Blob

## FTP {#section_D2B521C49BDE4F91A1999FE222CF306F}

Os dados do feed de dados podem ser entregues para um local FTP hospedado na Adobe ou no cliente.

Se optar por carregar os dados no servidor FTP, forneça à Adobe o nome de usuário, a senha e o caminho de carregamento apropriados. Você deve implementar seu próprio processo para gerenciar o espaço em disco no servidor, visto que a Adobe não exclui dados do servidor.

![](assets/dest-ftp.jpg)

## SFTP {#section_8D9215E441474D2BBC56228C2BC926E5}

Os dados do feed de dados podem ser entregues para um local sFTP hospedado pela Adobe ou pelo cliente.

Se optar por carregar os dados no servidor FTP, forneça à Adobe o nome de usuário e o caminho de carregamento apropriados.

<!-- 

Adobe Customer Care will provide you with a Public key. Verify in recording.

 -->

Você deve implementar seu próprio processo para gerenciar o espaço em disco no servidor, visto que a Adobe não exclui dados do servidor.

![](assets/dest-sftp.jpg)

## Amazon S3 {#section_4191CD7B8D3F419EB850B286B542C14A}

Você pode fazer o upload de seus arquivos para um bucket Amazon S3. A Amazon automaticamente criptografa os dados na parada (nos servidores da Amazon). Os dados são descriptografados automaticamente ao baixá-los.

Se você optar pelo envio por meio da Amazon S3, é necessário fornecer um nome de bucket, uma ID de chave de acesso, uma chave secreta e um nome de pasta.

![](assets/dest-s3.jpg)

Agora, os feeds de dados comunicam-se com as 11 regiões AWS a seguir (usando o algoritmo de assinatura apropriado, quando necessário):

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

No momento, a região AWS de Pequim, China (cn-north-1) não é compatível.

## Azure Blob {#section_1E9F1D0E7EAB4189A5D748FCA57D63D1}

É possível fazer o upload de seus arquivos para um Azure Blob.

![](assets/azure.png)

## Campos {#section_AD54B41BC7C945DC85F5FB8FCD4A4792}

A tabela a seguir mostra opções para todos os canais de distribuição. A opções disponíveis dependem do canal de distribuição selecionado.

<table id="table_F743C620C82349D9943A13B99EA312BA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Chave de acesso </p> </td> 
   <td colname="col2"> <p>Insira a chave de acesso do Amazon S3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bucket </p> </td> 
   <td colname="col2"> <p>Insira a localização do bucket do Amazon S3. </p> <p>Esse valor deve corresponder ao formato bucket S3 apropriado. (See <a href="https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html" format="html" scope="external"> https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html</a>.) </p> <p> <p>Observação: consulte <a href="../../../export/analytics-data-feed/feed-troubleshooting.md#section_6797EBBB7E6D44D4B00C7AEDF4C2EE1D" format="dita" scope="local">configurações BucketOwnerFullControl para feed de dados Amazon S3</a> abaixo, para detalhes sobre as configurações do Amazon S3. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contêiner </p> </td> 
   <td colname="col2"> <p>Insira o nome do contêiner do Azure Blob. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Host </p> </td> 
   <td colname="col2"> <p>Especifique a localização de host FTP ou SFTP. </p> <p>Esse valor deve cumprir com o devido formato ftp/sftp, <code>ftp.domain.com/subdomain</code> ou <code>sftp.domain.com/subdomain</code>. </p> <p> As portas padrão 21 e 22 para FTP e sFTP são necessárias. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Senha </p> <p>Confirmar senha </p> </td> 
   <td colname="col2"> <p>Insira a senha FTP. Insira novamente para confirmação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caminho </p> </td> 
   <td colname="col2"> <p>Selecione o caminho para o host ou bucket. Esse caminho deve existir antes da criação do feed. </p> <p> <p>Observação: consulte <a href="../../../export/analytics-data-feed/feed-troubleshooting.md#section_6797EBBB7E6D44D4B00C7AEDF4C2EE1D" format="dita" scope="local">configurações BucketOwnerFullControl para feed de dados Amazon S3</a> abaixo, para detalhes sobre as configurações do Amazon S3. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Conta </p> </td> 
   <td colname="col2"> <p> Insira a conta de armazenamento do Azure. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chave pública </p> </td> 
   <td colname="col2"> <p>Forneça a chave pública do SFTP. </p> <p>Você deve baixar a chave pública para configurar o repositório SFTP. </p> <p> <p>Observação: não é necessário baixar a chave pública para criar o feed. </p> </p> <p>Você pode usar uma chave pública já baixada ao criar um feed anterior. </p> <p>Para obter mais informações, consulte <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/ftp_sftp_dw.html" format="html" scope="external">https://marketing.adobe.com/resources/help/pt_BR/whitepapers/ftp/ftp_sftp_dw.html</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chave </p> <p>Confirmar chave </p> </td> 
   <td colname="col2"> <p> Insira a sua chave de acesso de armazenamento. Insira novamente para confirmar. </p> <p> <p>Observação: consulte <a href="https://docs.microsoft.com/en-us/azure/storage/common/storage-create-storage-account#view-and-copy-storage-access-keys" format="https" scope="external">https://docs.microsoft.com/pt-br/azure/storage/common/storage-create-storage-account#view-and-copy-storage-access-keys</a> para acessar as chaves de acesso. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chave secreta </p> <p>Confirme a chave secreta </p> </td> 
   <td colname="col2"> <p>Insira a chave secreta do Amazon S3. Insira novamente para confirmação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tipo </p> </td> 
   <td colname="col2"> <p>Selecione o tipo de destino. </p> <p> 
     <ul id="ul_B893EEDA73A34DE0AEB8570BE9027F21"> 
      <li id="li_325546FCEB404C50AA6829573CCA340B">FTP (padrão) </li> 
      <li id="li_6A2C03115903484797485D073A610607">AmazonS3 </li> 
      <li id="li_C24540F6FCD24702B7693A515CEBE977">SFTP </li> 
      <li id="li_8E03CA78E7FE427C9F6F8B112BC76266">Azure Blob </li> 
     </ul> </p> <p>Após selecionar o tipo de destino, a lista de campos é alterada para exibir as opções disponíveis para o destino selecionado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome de usuário </p> </td> 
   <td colname="col2"> <p>Insira o nome de usuário FTP. </p> </td> 
  </tr> 
 </tbody> 
</table>

