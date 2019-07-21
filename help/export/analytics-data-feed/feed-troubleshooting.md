---
description: Essa seção apresenta informações sobre problemas comuns.
keywords: Feed de dados; solução de problemas
seo-description: Essa seção apresenta informações sobre problemas comuns.
seo-title: Solução de problemas de feeds de dados
solution: Analytics
title: Solução de problemas de feeds de dados
uuid: 4 be 981 ab -3 a 61-4099-9 b 0 d -785 d 2 ac 2492 a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Solução de problemas de feeds de dados

Essa seção apresenta informações sobre problemas comuns.

## Erro ao salvar o feed {#section_EF38BB51A7E240D69DAD4C07A34D9AD5}

Os nomes de arquivos do feed de dados são criados a partir da ID do conjunto de relatórios e data. Qualquer par de feeds configurados para a mesma RSID (ID do conjunto de relatórios) e data(s) terá o mesmo nome de arquivo. Se esses arquivos forem entregues na mesma localização, um arquivo irá sobrepor o outro. Para evitar uma sobreposição de arquivos, não é possível criar um feed com potencial para sobrepor um feed já existente na mesma localização.

Tentar criar um feed quando já existe outro com o mesmo nome de arquivo resulta na seguinte mensagem:

Se receber essa mensagem de erro, considere as seguintes soluções alternativas:

* Alterar o caminho de entrega
* Alterar as datas, se possível
* Alterar o conjunto de relatórios, se possível

## Configuração BucketOwnerFullControl para feeds de dados da Amazon S3 {#section_6797EBBB7E6D44D4B00C7AEDF4C2EE1D}

O caso de uso comum da Amazon S3 é que o proprietário da conta da Amazon Web Services (AWS) cria um bucket e, em seguida, cria um usuário com permissões para criar objetos nele, além de fornecer credenciais para esse usuário. Nesse caso, os objetos de um usuário pertencem à mesma conta, e o proprietário dela tem o controle total do objeto (ler, excluir etc.). Isso é semelhante ao modo como a entrega por FTP funciona.

O AWS também possibilita que um usuário crie objetos em um bucket que pertencem a uma conta de usuário diferente. Por exemplo, se dois usuários do AWS, o usuárioA e o usuárioB, não pertencem à mesma conta do AWS, mas desejam criar objetos em outros buckets. Se o usuárioA cria um bucket, por exemplo, bucketA, ele ou ela pode criar uma política de bucket que permite explicitamente que o usuárioB crie objetos no bucketA, mesmo se o usuário não for o proprietário do bucket. Isso pode ser vantajoso, pois não exige que o usuárioA e o usuárioB troquem as credenciais. Em vez disso, o usuárioB fornece ao usuárioA o número da conta, e o usuárioA cria uma política de bucket que essencialmente diz “permitir que o usuárioB crie objetos do bucketA”.

**BucketOwnerFullControl** fornece direitos entre contas para criar objetos em outros buckets. Se o usuárioB envia um objeto para o bucket do usuárioA, o usuárioB ainda é o “proprietário” do objeto e, por padrão, o usuárioA não recebe permissões para esse objeto, embora seja o proprietário do bucket. Os objetos não herdam as permissões do bucket pai. O usuárioB deve conceder permissões para o usuárioA, pois o primeiro ainda é o proprietário do objeto. Para esse envio entre contas, o AWS fornece um ACL BucketOwnerFullControl ao especificar o uso desse ACL pelo proprietário do bucket (usuárioA) e recebe as permissões para o objeto (ler, gravar, excluir etc.), embora o objeto seja “de propriedade” do usuárioB.

## Falhas de transferência {#section_4BD44E9167F0494FB2B379D2BA132AD8}

Se houver uma falha de transferência no FTP (logon negado, conexão perdida, extraquota, etc.), a Adobe tenta automaticamente se conectar e faz até três tentativas de envio de dados. Se a falha continuar, o feed é marcado como falho e um email de notificação é enviado.

No caso de falha na transferência, você pode [executar uma tarefa novamente](../../export/analytics-data-feed/c-df-jobs/t-job-rerun.md#task_FF9CD08685944E1EBB0CCA02F581C501) até que seja concluída com sucesso.

## Opções de reenvio {#section_BFD4447B0B5946CAAEE4F0F03D42EDFD}

Once you have verified/corrected the delivery issue, just use [rerun the job](../../export/analytics-data-feed/c-df-jobs/t-job-rerun.md#task_FF9CD08685944E1EBB0CCA02F581C501) to get the files.

## Impacto do horário de verão nos feeds de dados por hora {#section_70E867D942054DD09048E027A9474FFD}

Em alguns fusos horários, o tempo será alterado duas vezes por ano devido às definições do horário de verão. Os feeds de dados seguem o fuso horário em que o conjunto de relatórios é configurado. Se o fuso horário do conjunto de relatórios não seguir o horário de verão, a entrega do arquivo continuará normalmente como qualquer outro dia. Se o fuso horário do conjunto de relatórios seguir o horário de verão, a entrega do arquivo será alterada para a hora em que ocorreu a alteração de horário (normalmente às 02h00).

Ao fazer as transições de horário padrão -&gt; horário de verão (“Spring Forward”, primavera em diante), o cliente obterá somente 23 arquivos. O horário saltado na transição do horário de verão é simplesmente omitido. Por exemplo, se a transição ocorrer às 02h00, os clientes obterão um arquivo às 01h00 e outro às 03h00. Não haverá arquivo às 02h00, visto que o horário padrão de 02h00 torna-se o horário de verão de 03h00.

Ao fazer as transições de horário de verão -&gt; horário padrão, (“Fall Back”, outono para trás), o cliente obterá os 24 arquivos. Contudo, o horário de transição incluirá o equivalente a 2 horas de dados. Por exemplo, se a transição ocorrer às 02h00, o arquivo para 01h00 será atrasado em uma hora, mas conterá os dados para duas horas. Ele conterá os dados do horário de verão de 01h00 as 02h00 do horário padrão (que teria sido 03h00 do horário de verão). O arquivo a seguir começará às 02h00 do horário padrão.

## Sem dados por um período de tempo {#section_72510794694D42A9A75C966B812AEB0F}

É possível optar por configurar o feed de dados para entregar um arquivo manifest se não houver dados coletados por um período específico. Se ativar essa opção, você receberá um arquivo manifest semelhante ao seguinte:

```
Datafeed-Manifest-Version: 1.0
 Lookup-Files: 0
 Data-Files: 0
 Total-Records: 0
```

## Não há informações de domínio para relatório de domínio {#section_B7508D65370442C7A314EAED711A2C75}

Algumas operadoras de dispositivos móveis (tais como T-Mobile e O1) não fornecem mais informações de domínio de pesquisas de DNS Reverso. Sendo assim, os dados não estão disponíveis para relatório de domínio.

## Visão geral do processamento de dados {#section_6346328F8D8848A7B81474229481D404}

Antes de processar dados por dia ou por hora, os feeds de dados aguardam até que todas os hits inseridos na coleta de dados no período (dia ou hora) tenham sido gravados no data warehouse. Depois que isso ocorrer, os feeds de dados coletam os dados com carimbos de data e hora que correspondem ao período, compactando-os e reenviando-os via FTP. Nos feeds por hora, os arquivos são normalmente gravados no data warehouse dentro de 15 a 30 minutos depois da hora, mas não há um período de tempo definido. Se não houver dados com carimbos de data e hora correspondentes ao período, o processo tenta novamente o próximo período. O processo do feed de dados atual usa o campo `date_time` para determinar quais hits pertencem à hora. Esse campo se baseia no fuso horário do conjunto de relatórios.
