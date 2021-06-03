---
description: Perguntas frequentes sobre feeds de dados
keywords: Feed de dados;coluna pré;coluna pós;diferencia maiúsculas de minúsculas
title: Perguntas frequentes sobre feeds de dados
exl-id: 1bbf62d5-1c6e-4087-9ed9-8f760cad5420
source-git-commit: 46ba345247c6a2553cd30b446d87eeb7b15ee94b
workflow-type: tm+mt
source-wordcount: '1375'
ht-degree: 41%

---

# Perguntas frequentes sobre feeds de dados

Perguntas frequentes sobre feeds de dados.

## Os nomes dos feeds devem ser exclusivos?{#section_EF38BB51A7E240D69DAD4C07A34D9AD5}

Os nomes de arquivos do feed de dados são criados a partir da ID do conjunto de relatórios e data. Todos os dois feeds configurados para o mesmo RSID e data(s) têm o mesmo nome de arquivo. Se esses feeds forem entregues no mesmo local, um arquivo substituirá o outro. Para evitar uma sobreposição de arquivos, não é possível criar um feed com potencial para sobrepor um feed já existente na mesma localização.

Tentar criar um feed quando já existe outro com o mesmo nome de arquivo resulta na seguinte mensagem:

Se receber essa mensagem de erro, considere as seguintes soluções alternativas:

* Alterar o caminho de entrega
* Alterar as datas, se possível
* Alterar o conjunto de relatórios, se possível

## Quando os dados são processados? {#section_6346328F8D8848A7B81474229481D404}

Antes de processar dados por dia ou por hora, os feeds de dados aguardam até que todas os hits inseridos na coleta de dados no período (dia ou hora) tenham sido gravados no data warehouse. Depois que isso ocorrer, os feeds de dados coletam os dados com carimbos de data e hora que correspondem ao período, compactando-os e enviando-os via FTP. Nos feeds por hora, os arquivos são normalmente gravados no data warehouse dentro de 15 a 30 minutos depois da hora, mas não há um período de tempo definido. Se não houver dados com carimbos de data e hora correspondentes ao período, o processo tenta novamente o próximo período. O processo do feed de dados atual usa o campo `date_time` para determinar quais hits pertencem à hora. Esse campo se baseia no fuso horário do conjunto de relatórios.

## Qual é a diferença entre colunas com um prefixo `post_` e colunas sem um prefixo `post_`?

As colunas sem o prefixo `post_` contêm dados exatamente como foram enviados para a coleta de dados. As colunas com um prefixo `post_` contêm o valor após o processamento. Exemplos que podem alterar um valor são persistência de variáveis, regras de processamento, regras VISTA, conversão de moeda ou outra lógica do lado do servidor aplicada pela Adobe. A Adobe recomenda usar a versão `post_` de uma coluna, quando possível.

Se uma coluna não tiver uma versão `post_` (por exemplo, `visit_num`), ela pode ser considerada uma coluna posterior.

## Como os feeds de dados lidam com distinção entre maiúsculas e minúsculas?

No Adobe Analytics, a maioria das variáveis não diferencia maiúsculas de minúsculas para fins de relatório. Por exemplo, &#39;neve&#39;, &#39;Neve&#39;, &#39;NEVE&#39; e &#39;nEve&#39; são considerados o mesmo valor. A diferenciação entre maiúsculas e minúsculas é mantida nos feeds de dados.

Se você vir variações de maiúsculas e minúsculas diferentes do mesmo valor entre colunas que não sejam de publicação e posterior (por exemplo, &quot;neve&quot; na coluna anterior e &quot;Neve&quot; na coluna posterior), sua implementação usa valores em maiúsculas e minúsculas no site. A diferenciação entre maiúsculas e minúsculas na coluna posterior foi transmitida e armazenada no cookie virtual ou processada ao mesmo tempo que o conjunto de relatórios.

## Os bots são filtrados pelas regras de bot do Admin Console nos feeds de dados?

Os feeds de dados não incluem bots filtrados pelas [regras de bot do Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/bot-removal/bot-removal.html).

## Por que vejo vários valores `000` na coluna `event_list` ou `post_event_list` do feed de dados?

Alguns editores de planilha, especialmente o Microsoft Excel, arredondam automaticamente grandes números. A coluna `event_list` contém muitos números delimitados por vírgulas, às vezes fazendo com que o Excel os considere números grandes. Ele arredonda os últimos vários dígitos para `000`.

A Adobe recomenda não abrir automaticamente arquivos `hit_data.tsv` no Microsoft Excel. Em vez disso, use a caixa de diálogo Importar dados do Excel e verifique se todos os campos são tratados como texto.

## Por que as informações estão faltando na coluna de domínio para algumas operadoras? {#section_B7508D65370442C7A314EAED711A2C75}

Algumas operadoras de celular (tais como T-Mobile e O1) não fornecem mais informações de domínio de pesquisas de DNS Reverso. Sendo assim, os dados não estão disponíveis para relatório de domínio.

## Por que não posso extrair arquivos &quot;por hora&quot; de dados que têm mais de 7 dias?

Para dados com mais de 7 dias, os arquivos &quot;Por hora&quot; de um dia são combinados em um único arquivo &quot;Diariamente&quot;.

Exemplo: Um novo Feed de dados é criado em 9 de março de 2021, e os dados de 1º de janeiro de 2021 a 9 de março são entregues como &quot;Por hora&quot;. No entanto, os arquivos &quot;por hora&quot; antes de 2 de março de 2021 são combinados em um único arquivo &quot;diário&quot;. Você pode extrair arquivos &quot;por hora&quot; somente de dados com menos de 7 dias a partir da data de criação. Nesse caso, de 2 de março a 9 de março.

## Qual é o impacto do horário de verão nos feeds de dados por hora? {#section_70E867D942054DD09048E027A9474FFD}

Para certos fusos horários, o tempo muda duas vezes por ano devido às definições de horário de verão. Os feeds de dados seguem o fuso horário em que o conjunto de relatórios é configurado. Se o fuso horário do conjunto de relatórios não tiver horário de verão, a entrega do arquivo continuará normalmente como qualquer outro dia. Se o fuso horário do conjunto de relatórios usar horário de verão, a entrega do arquivo será alterada para a hora em que ocorreu a alteração de horário (normalmente às 02:00).

Ao fazer as transições de horário padrão -> horário de verão (&quot;Spring Forward&quot;, primavera em diante), o cliente recebe apenas 23 arquivos. A hora ignorada na transição do horário de verão é omitida. Por exemplo, se a transição ocorrer às 2:00, eles receberão um arquivo pela 1:00 hora e um arquivo pela 3:00 hora. Não há arquivo 2:00 porque, às 2:00 do horário padrão, ele se torna 3:00 do horário de verão.

Ao fazer as transições de horário de verão -> horário padrão, (&quot;Fall Back&quot;, outono para trás), o cliente recebe 24 arquivos. No entanto, o horário de transição realmente inclui o equivalente a duas horas de dados. Por exemplo, se a transição ocorrer às 2:00, o arquivo para 1:00 será atrasado em uma hora, mas conterá dados para duas horas. Ele contém dados do horário de verão de 1:00 às 2:00 do horário padrão (que teria sido 3:00 do horário de verão). O próximo arquivo começa às 2:00 do horário padrão.

## Como o Analytics lida com falhas de transferência de FTP? {#section_4BD44E9167F0494FB2B379D2BA132AD8}

Se uma transferência de FTP falhar (devido a um logon negado, conexão perdida, erro de fora da cota ou outro problema), o Adobe tenta automaticamente se conectar e envia os dados até três vezes. Se a falha continuar, o feed é marcado como falho e um email de notificação é enviado.

Se uma transferência falhar, você poderá executar uma tarefa novamente até que seja concluída com sucesso.

Se tiver problemas para que um feed de dados apareça no site FTP, consulte [Solucionar problemas de tarefas](jobs-troubleshooting.md).

## Como faço para reenviar um trabalho? {#section_BFD4447B0B5946CAAEE4F0F03D42EDFD}

Depois de verificar/corrigir o problema de entrega, execute novamente o trabalho para obter os arquivos.

## Qual é a configuração BucketOwnerFullControl para feeds de dados do Amazon S3? {#BucketOwnerFullControl}

**BucketOwnerFullControl** fornece direitos entre contas para criar objetos em outros buckets.

O caso de uso comum da Amazon S3 é que o proprietário da conta da Amazon Web Services (AWS) cria um bucket e, em seguida, cria um usuário com permissões para criar objetos nele, além de fornecer credenciais para esse usuário. Nesse caso, os objetos de um usuário pertencem à mesma conta, e o proprietário da conta tem o controle total do objeto (ler, excluir e assim por diante). Esse processo é semelhante à forma como a entrega por FTP funciona.

O AWS também possibilita que um usuário crie objetos em um compartimento que pertence a uma conta de usuário diferente. Por exemplo, digamos que dois usuários do AWS, o usuárioA e o usuárioB, não pertençam à mesma conta do AWS, mas desejam criar objetos em outros buckets. Se o usuárioA criar um bucket chamado &quot;bucketA&quot;, ele poderá criar uma política de bucket que permita explicitamente que o usuárioB crie objetos no bucketA, mesmo que o usuário não seja o proprietário do bucket. Essa política pode ser vantajosa porque não requer que o usuárioA e o usuárioB troquem credenciais. Em vez disso, o usuárioB fornece ao usuárioA o número da conta, e o usuárioA cria uma política de bucket que essencialmente diz “permitir que o usuárioB crie objetos do bucketA”.

No entanto, objetos não herdam permissões do bucket pai. Portanto, se o usuárioB carregar um objeto no bucket do usuárioA, o usuárioB ainda será &quot;proprietário&quot; desse objeto e, por padrão, o usuárioA não receberá permissões para esse objeto, mesmo que o usuárioA seja proprietário do bucket. O usuárioB deve conceder permissões para o usuárioA, pois o primeiro ainda é o proprietário do objeto. Para conceder essa permissão, o usuárioB deve carregar o objeto com uma ACL BucketOwnerFullControl, que especifica que o proprietário do bucket (usuárioA) recebe permissões completas para o objeto (ler, gravar, excluir e assim por diante), mesmo que o objeto seja &quot;de propriedade&quot; do usuárioB.

>[!NOTE]
>
>[!DNL Analytics] não determina se o bucket tem uma política que requer que o proprietário do bucket tenha total controle de novos objetos, ou mesmo se o proprietário do bucket estiver em uma conta diferente da do usuário que está gravando os dados. Em vez disso, [!DNL Analytics] adiciona automaticamente o proprietário do bucket à ACL BucketOwnerFullControl com cada upload de feed.

>[!MORELIKETHIS]
>
>* [Solução de problemas de tarefas](jobs-troubleshooting.md)

