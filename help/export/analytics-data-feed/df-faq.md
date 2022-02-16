---
description: Perguntas frequentes sobre feeds de dados
keywords: Feed de dados;coluna pré;coluna pós;diferencia maiúsculas de minúsculas
title: Perguntas frequentes sobre feeds de dados
feature: Data Feeds
exl-id: 1bbf62d5-1c6e-4087-9ed9-8f760cad5420
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '1439'
ht-degree: 100%

---

# Perguntas frequentes sobre feeds de dados

Perguntas frequentes sobre feeds de dados.

## Os nomes dos feeds devem ser exclusivos?{#section_EF38BB51A7E240D69DAD4C07A34D9AD5}

Os nomes de arquivos do feed de dados são criados a partir da ID do conjunto de relatórios e data. Qualquer par de feeds configurados para a mesma RSID (ID do conjunto de relatórios) e data terá o mesmo nome de arquivo. Se esses feeds forem entregues na mesma localização, um arquivo sobreporá o outro. Para evitar uma sobreposição de arquivos, não é possível criar um feed com potencial para sobrepor um feed já existente na mesma localização.

Tentar criar um feed quando já existe outro com o mesmo nome de arquivo resulta na seguinte mensagem:

Se receber essa mensagem de erro, considere as seguintes soluções alternativas:

* Alterar o caminho de entrega
* Alterar as datas, se possível
* Alterar o conjunto de relatórios, se possível

## Quando os dados são processados? {#section_6346328F8D8848A7B81474229481D404}

Antes de processar dados por dia ou por hora, os feeds de dados aguardam até que todas os hits inseridos na coleta de dados no período (dia ou hora) tenham sido gravados no data warehouse. Depois que isso ocorre, os feeds de dados coletam os dados com carimbos de data e hora que correspondem ao período, compactando-os e reenviando-os via FTP. Nos feeds por hora, os arquivos são normalmente gravados no data warehouse dentro de 15 a 30 minutos depois da hora, mas não há um período de tempo definido. Se não houver dados com carimbos de data e hora correspondentes ao período, o processo tenta novamente o próximo período. O processo do feed de dados atual usa o campo `date_time` para determinar quais hits pertencem à hora. Esse campo se baseia no fuso horário do conjunto de relatórios.

## Qual é a diferença entre colunas com um prefixo `post_` e colunas sem um prefixo `post_`?

As colunas sem o prefixo `post_` contêm os dados exatamente como foram enviados para a coleção de dados. As colunas com um prefixo `post_` contêm o valor após o processamento. Exemplos que podem alterar um valor são persistência de variáveis, regras de processamento, regras VISTA, conversão de moeda ou outra lógica do lado do servidor aplicada pela Adobe. A Adobe recomenda usar a versão `post_` de uma coluna, quando possível.

Se uma coluna não tiver uma versão `post_` (por exemplo, `visit_num`), ela pode ser considerada uma coluna posterior.

## Como os feeds de dados lidam com distinção entre maiúsculas e minúsculas?

No Adobe Analytics, a maioria das variáveis não diferencia maiúsculas de minúsculas para fins de relatório. Por exemplo, &#39;neve&#39;, &#39;Neve&#39;, &#39;NEVE&#39; e &#39;nEve&#39; são considerados o mesmo valor. A diferenciação entre maiúsculas e minúsculas é mantida nos feeds de dados.

Se você vir variações de maiúsculas e minúsculas diferentes do mesmo valor entre colunas que sejam ou não de publicação (por exemplo, &quot;neve&quot; na coluna anterior e &quot;Neve&quot; na coluna posterior), sua implementação usará valores em maiúsculas e minúsculas no site. A diferenciação entre maiúsculas e minúsculas na coluna posterior foi transmitida e armazenada no cookie virtual ou processada ao mesmo tempo que o conjunto de relatórios.

## Os bots são filtrados pelas regras de bot do Admin Console nos feeds de dados?

Os feeds de dados não incluem bots filtrados pelas [regras de bot do Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/bot-removal/bot-removal.html?lang=pt-BR).

## Por que vejo vários valores `000` na coluna `event_list` ou `post_event_list` do feed de dados?

Alguns editores de planilhas, especialmente o Microsoft Excel, arredondam automaticamente números grandes. A coluna `event_list` contém muitos números delimitados por vírgulas, às vezes fazendo com que o Excel os considere números grandes. Ele arredonda os últimos vários dígitos para `000`.

A Adobe recomenda não abrir automaticamente arquivos `hit_data.tsv` no Microsoft Excel. Em vez disso, use a caixa de diálogo Importar dados do Excel e verifique se todos os campos são tratados como texto.

## Colunas como `hitid_high`, `hitid_low`, `visid_high` e `visid_low` são garantidas como exclusivas para a ocorrência ou visita?

Em quase todos os casos, a concatenação de `hitid_high` e `hitid_low` identifica exclusivamente uma ocorrência. O mesmo conceito se aplica à concatenação de `visid_high` e `visid_low` para visitas. No entanto, o processamento de anomalias raramente pode fazer com que dois hits compartilhem a mesma ID. A Adobe recomenda não criar fluxos de trabalho de feed de dados que dependam unicamente de cada hit ser exclusivo.

## Por que as informações estão faltando na coluna de domínio para algumas operadoras? {#section_B7508D65370442C7A314EAED711A2C75}

Algumas operadoras de celular (tais como T-Mobile e O1) não fornecem mais informações de domínio de pesquisas de DNS Reverso. Sendo assim, os dados não estão disponíveis para relatório de domínio.

## Por que não posso extrair arquivos &quot;por hora&quot; de dados que têm mais de sete dias?

Para dados com mais de 7 dias, os arquivos &quot;Por hora&quot; de um dia são combinados em um único arquivo &quot;Diariamente&quot;.

Exemplo: um novo Feed de dados é criado em 9 de março de 2021, e os dados de 1º de janeiro de 2021 a 9 de março são entregues como &quot;Por hora&quot;. No entanto, os arquivos &quot;Por hora&quot; anteriores a 2 de março de 2021 são combinados em um único arquivo &quot;Diário&quot;. Você pode extrair arquivos &quot;Por hora&quot; somente de dados com menos de sete dias a partir da data de criação. Nesse caso, de 2 de março a 9 de março.

## Qual é o impacto do horário de verão nos feeds de dados por hora? {#section_70E867D942054DD09048E027A9474FFD}

Em alguns fusos horários, a hora será alterada duas vezes por ano devido às definições do horário de verão. Os feeds de dados seguem o fuso horário em que o conjunto de relatórios é configurado. Se o fuso horário do conjunto de relatórios não seguir o horário de verão, a entrega do arquivo continuará normalmente como qualquer outro dia. Se o fuso horário do conjunto de relatórios seguir o horário de verão, a entrega do arquivo será alterada para a hora em que ocorreu a alteração de horário (normalmente às 2h).

Ao fazer as transições de horário padrão -> horário de verão (“Spring Forward”, horário adiantado na primavera), o cliente obterá somente 23 arquivos. O horário ignorado na transição do horário de verão é omitido. Por exemplo, se a transição ocorrer às 2h, os clientes obterão um arquivo à 1h e outro às 3h. Não haverá arquivo às 2h, visto que o horário padrão de 2h torna-se o horário de verão de 3h.

Ao fazer as transições de horário de verão -> horário padrão, (“Fall Back”, horário de outono atrasado), o cliente obterá os 24 arquivos. Contudo, o horário de transição incluirá o equivalente a horas de dados. Por exemplo, se a transição ocorrer às 2h, o arquivo para 1h será atrasado em uma hora, mas conterá os dados para duas horas. Ele conterá os dados do horário de verão de 1h às 2h do horário padrão (que teria sido 3h do horário de verão). O próximo arquivo começa às 2h do horário padrão.

## Como o Analytics lida com falhas de transferência de FTP? {#section_4BD44E9167F0494FB2B379D2BA132AD8}

Se uma transferência FTP falhar (devido a um logon negado, uma conexão perdida, um erro de cota excedida ou outro problema), a Adobe tentará automaticamente se conectar e enviar os dados até três vezes. Se a falha continuar, o feed é marcado como falho e um email de notificação é enviado.

Se uma transferência falhar, você poderá executar uma tarefa novamente até que seja concluída com sucesso.

Se tiver problemas para que um feed de dados seja exibido no site FTP, consulte [Solução de problemas com feeds de dados](troubleshooting.md).

## Como faço para reenviar um trabalho? {#section_BFD4447B0B5946CAAEE4F0F03D42EDFD}

Depois de verificar/corrigir o problema de entrega, execute novamente o trabalho para obter os arquivos.

## Qual é a configuração BucketOwnerFullControl para feeds de dados do Amazon S3? {#BucketOwnerFullControl}

**BucketOwnerFullControl** fornece direitos entre contas para criar objetos em outros buckets.

O caso de uso comum da Amazon S3 é que o proprietário da conta da Amazon Web Services (AWS) cria um bucket e, em seguida, cria um usuário com permissões para criar objetos nele, além de fornecer credenciais para esse usuário. Nesse caso, os objetos de um usuário pertencem à mesma conta, e o proprietário da conta tem controle total implícito sobre o objeto (leitura, exclusão etc). Esse processo é semelhante ao modo como a entrega por FTP funciona.

O AWS também possibilita que um usuário crie objetos em um compartimento que pertence a uma conta de usuário diferente. Por exemplo, se dois usuários do AWS, o usuário A e usuário B, não pertencem à mesma conta do AWS, mas desejam criar objetos em outros buckets. Se o usuário A cria um bucket e dá a ele o nome de &quot;bucketA&quot;, ele pode criar uma política de bucket que permite explicitamente que o usuário B crie objetos no bucketA, mesmo que não seja o proprietário do bucket. Essa política pode ser vantajosa porque não exige que o usuário A e o usuário B troquem credenciais. Em vez disso, o usuárioB fornece ao usuárioA o número da conta, e o usuárioA cria uma política de bucket que essencialmente diz “permitir que o usuárioB crie objetos do bucketA”.

No entanto, objetos não herdam permissões do bucket primário. Portanto, se o usuário B faz o upload de um objeto para o bucket do usuário A, o usuário B ainda &quot;possui&quot; esse objeto e, por padrão, o usuário A não recebe permissão para esse objeto, embora o usuário A seja o proprietário do bucket. O usuárioB deve conceder permissões para o usuárioA, pois o primeiro ainda é o proprietário do objeto. Para conceder essa permissão, o usuário B deve fazer upload do objeto com uma ACL BucketOwnerFullControl, que especifica que o proprietário do bucket (usuário A) recebe permissões totais para o objeto (leitura, gravação, exclusão etc), mesmo que o objeto seja &quot;pertencente&quot; ao usuário B.

>[!NOTE]
>
>O [!DNL Analytics] não determina se o bucket tem uma política que requer que o seu proprietário tenha total controle de novos objetos, ou mesmo se o proprietário do bucket está em uma conta diferente daquela do usuário que está gravando os dados. Em vez disso, o [!DNL Analytics] adiciona automaticamente o proprietário do bucket à ACL BucketOwnerFullControl a cada upload de feed.
