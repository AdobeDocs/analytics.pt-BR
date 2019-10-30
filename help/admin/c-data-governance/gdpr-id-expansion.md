---
description: 'As IDs enviadas nem sempre cobrem todos os dados de ocorrências que o Analytics pode associar ao titular dos dados. O Analytics pode criar um conjunto expandido de IDs para incluir esses dados associados nas solicitações de Privacidade de dados. Essa opção pode ser solicitada com um parâmetro opcional referente à solicitação de Privacidade de dados enviada adicionado à solicitação JSON '
seo-description: 'As IDs enviadas nem sempre cobrem todos os dados de ocorrências que o Analytics pode associar ao titular dos dados. O Analytics pode criar um conjunto expandido de IDs para incluir esses dados associados nas solicitações de Privacidade de dados. Essa opção pode ser solicitada com um parâmetro opcional referente à solicitação de Privacidade de dados enviada adicionado à solicitação JSON '
seo-title: Expansão de ID
title: Expansão de ID
uuid: 2672d17d-c957-4e08-8dd9-16d54bf2be18
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Expansão de ID

As IDs enviadas nem sempre cobrem todos os dados de ocorrências que o Analytics pode associar ao titular dos dados. O Analytics pode criar um conjunto expandido de IDs para incluir esses dados associados nas solicitações de Privacidade de dados. Essa opção pode ser solicitada com um parâmetro opcional referente à solicitação de Privacidade de dados enviada adicionado à solicitação JSON:

```
"expandIds": true
```

Consulte o [Exemplo de solicitação de JSON](/help/admin/c-data-governance/gdpr-submit-access-delete.md#sample-json-request) para saber como incluir essa opção com a solicitação. Para obter mais detalhes, consulte a [Documentação da API da Privacidade de dados.](https://www.adobe.io/apis/experienceplatform/gdpr.html)

<table id="table_A10CA8DC8C1643CF84A4DF30A6740D51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo </th> 
   <th colname="col2" class="entry"> Considerações </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Expansão de ID de cookies </p> </td> 
   <td colname="col2"> <p>Originalmente, muitos clientes do Analytics usavam o <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_analytics.html" format="html" scope="external">Cookie do Analytics</a> (herdado), mas agora usam o <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Serviço de identidade (ECID) </a>, conhecido anteriormente como Serviço da Marketing Cloud ID (MCID). Somente a ECID existe para os visitantes do site que acessaram pela primeira vez após a transição. No entanto, para aqueles que visitaram anteriormente quando somente o Cookie herdado estava disponível, mas não retornaram: alguns dados terão ambos os cookies, mas os dados mais antigos terão apenas o Cookie do Analytics e, em casos raros, os dados mais recentes terão somente uma ECID. </p> <p>Certifique-se de encontrar todos os dados referentes a um visitante identificado por meio de um Cookie (ID do visitante) do Analytics ou uma ECID. Portanto, se você usa a ECID e anteriormente usava o Cookie do Analytics, quando enviar uma solicitação usando qualquer um dos dois tipos de ID, deverá incluir ambas as IDs na solicitação ou especificar a opção expandIDs. Quando você especifica expandIDs, a Adobe verificará outras ECIDs ou Cookies do Analytics que correspondem a qualquer ID de cookie que você fornecer. A solicitação será expandida automaticamente para incluir essas IDs de cookie recentemente identificadas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID personalizada para expansão de ID de cookies </p> </td> 
   <td colname="col2"> <p>Em sites de comércio eletrônico, não é incomum que um visitante navegue pelo site, adicione itens ao carrinho e inicie o processo de finalização antes de fazer logon. Se a ID usada para identificar usuários referentes a uma solicitação de Privacidade de dados estiver armazenada em uma variável personalizada somente quando o usuário estiver conectado, essa atividade pré-logon não será associada à ID. Usando a ID de cookies do Analytics, os clientes podem optar por associar a navegação realizada antes do logon com a compra após o logon, pois a ID de cookies persiste durante o logon. </p> <p>Suponhamos que sua implementação armazene uma ID de logon (CRM ID, nome de usuário, número de fidelidade, endereço de email etc., ou um hash referente a qualquer um desses valores) em uma variável personalizada (prop ou eVar) ou ID de visitante personalizada, e usa essa ID para uma solicitação de acesso de Privacidade de dados. O titular dos dados pode se surpreender com o fato de que as informações sobre toda a navegação não são retornadas como parte de uma solicitação de acesso, especialmente se tiver promovido itens visualizados, mas ainda não comprados. </p> <p>Desta forma, o processamento da Privacidade de dados do Analytics suporta a expansão de ID, na qual o Analytics encontra todas as IDs de cookies que ocorram na mesma ocorrência de qualquer ID personalizada e, em seguida, expande a solicitação para também incluir essas IDs. </p> <p>Quando expandIDs é especificada junto com qualquer namespace que não seja um namespace de cookie, a solicitação será expandida para incluir quaisquer IDs de cookie (ECID ou Cookie do Analytics), encontrados em ocorrências contendo qualquer uma das IDs especificados. A expansão da ID do cookie, conforme descrito acima, será executada em qualquer ID de cookie recentemente encontrada. </p> <p>Quando a opção expandIDs é usada para uma solicitação de acesso e a ID especificada tiver um rótulo ID-PERSON, dois conjuntos de arquivos serão retornados. O primeiro conjunto (o conjunto de pessoas) conterá dados somente de ocorrências onde a ID especificada foi encontrada. O segundo conjunto (o conjunto de dispositivos) conterá apenas os dados das ocorrências das IDs expandidas, onde a ID especificada não estava presente. </p> </td> 
  </tr> 
 </tbody> 
</table>

Depois que a Privacidade de dados entrou em vigor, durante os primeiros meses, a grande maioria de solicitações de Privacidade de dados do Analytics não solicitaram expansão de ID, mas cabe a você determinar o valor apropriado referente à sua organização. Pergunte à sua equipe jurídica se a expansão de ID é exigida para seus dados com as IDs que você usa e os dados coletados no Adobe Analytics. Uma consideração primária é que, em um dispositivo compartilhado pelo qual varios usuários visitaram o seu site, usar a expansão de ID incluirá dados de ocorrências de outros usuários do dispositivo em dados retornados pelas solicitações de acesso (no arquivo do dispositivo). Mesmo se você tiver seguido as práticas recomendadas de rotulagem, de modo que nenhum dado privado seja incluído no arquivo do dispositivo (por exemplo, páginas visitadas), o arquivo do dispositivo conterá o número de páginas visitadas e o horário de cada uma dessas visitas. Essa informação pode ser compartilhada com alguém que não é o visitante?

Para uma solicitação de exclusão, onde a expansão de ID não é usada, se você usar uma ID que não é de cookie (qualquer ID diferente da ECID ou do cookie do Analytics) para identificar ocorrências que devem ser excluídas e essa ID tiver um rótulo ID-DEVICE, a contagem de visitantes únicos em relatórios será alterada, porque somente algumas instâncias das IDs de cookie serão anonimizadas, enquanto outras permanecerão sem alterações. Se você não estiver especificando a expansão de ID, recomenda-se usar uma ID de cookie para solicitações ou IDs com um rótulo ID-PERSON.

Quando a Adobe executa a expansão de ID, pode exigir uma análise de dados completa, que aumentará o tempo que a Adobe leva para concluir a solicitação. Esse tempo de processamento adicional pode chegar a até uma semana. 

## Outros sinalizadores de solicitação de Privacidade de dados

Além do sinalizador "expandIDs", o Analytics suporta dois outros sinalizadores que podem ser transmitidos como parte de uma solicitação de Privacidade de dados. Esses sinalizadores e seus valores padrão são:

```
"analyticsDeleteMethod": "anonymize"
"priority": "normal"
```

Futuramente, o "analyticsDeleteMethod" poderá suportar um valor "purge" em adição ao valor padrão "anonymize". Quando suportado, fará com que toda a ocorrência seja excluída em vez de apenas atualizar os valores de campos de ocorrência com guias DEL.

Além do valor padrão, o campo de prioridade também suporta o valor "low". Especifique esse valor para solicitações que não são o resultado de uma solicitação do titular dos dados e não possui um requisito legal a ser concluído em 30 dias. Observe que a Adobe não incentiva o uso da API da Privacidade de dados para propósitos diferentes de solicitações iniciadas por titulares dos dados. A API da Privacidade de dados não é uma ferramenta adequada para a limpeza ou reparo de dados, e terá consequências não intencionais.

[!NOTE]A [API da Privacidade de dados](https://www.adobe.io/apis/experienceplatform/gdpr.html) foi fornecida para ajudar a atender à solicitações de Privacidade de dados, que são sensíveis ao tempo. O uso dessa API para outros propósitos não é suportado pela Adobe e pode afetar a capacidade da Adobe de fornecer solicitações de Privacidade de dados iniciadas por usuários com inversão de alta prioidade para outros clientes da Adobe. Pedimos que você não use a API do Serviço de privacidade para outros propósitos, como limpar dados enviados por acidente para grandes grupos de visitantes.

Além disso, esteja ciente de que os usuários que têm uma ocorrência excluída (atualizada ou em anonimato) como o resultado de uma solicitação de exclusão da Privacidade de dados terão as informações de estado redefinidas. A próxima vez que o visitante retornar ao site, ele será um novo visitante. Todas as atribuições de eVar serão iniciadas novamente, assim como informações como números de visita, referenciadores, primeira página visitada etc. Esse efeito colateral não é desejável para situações em que você deseja limpar campos de dados, e realça o motivo pelo qual a API do Serviço de privacidade é imprópria para este uso.

Entre em contato com o Gerente de conta (CSM) para coordenar com nossa equipe de consultoria de Arquiteto de engenharia para revisão adicional e para empenhar esforços para remover qualquer problema de PII ou dados.

