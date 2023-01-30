---
description: As IDs enviadas nem sempre cobrem todos os dados de ocorrências que o Analytics pode associar ao titular dos dados. O Analytics pode criar um conjunto expandido de IDs para incluir esses dados associados nas solicitações de Privacidade de dados. Essa opção pode ser solicitada com um parâmetro opcional referente à solicitação de Privacidade de dados enviada adicionado à solicitação JSON
title: Expansão de ID
feature: Data Governance
exl-id: 312a249f-e0e7-44da-bb3d-b19f1bb4c706
source-git-commit: e9fffe62d3e53ae075610b1feec9a9071d925433
workflow-type: tm+mt
source-wordcount: '1327'
ht-degree: 47%

---

# Expansão de ID

As IDs enviadas nem sempre cobrem todos os dados de ocorrências que o Analytics pode associar ao titular dos dados. O Analytics pode criar um conjunto expandido de IDs para incluir esses dados associados nas solicitações de Privacidade de dados. Essa opção pode ser solicitada com um parâmetro opcional referente à solicitação de Privacidade de dados enviada adicionado à solicitação JSON:

```
"expandIds": true
```

Para obter mais detalhes, consulte a [Documentação da API da Privacidade de dados](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=pt-BR).


| Tipo | Considerações |
| --- | --- |
| Expansão de ID de cookies | Originalmente, muitos clientes do Analytics usavam o (Herdado) [Cookie do Analytics](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-privacy.html?lang=en), mas agora estão usando o [Serviço de identidade do Experience Cloud (ECID)](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR). Somente a ECID existe para os visitantes do site que acessaram pela primeira vez após a transição. No entanto, para aqueles que visitaram pela primeira vez quando apenas o Cookie herdado estava disponível, mas desde então visitaram: alguns de seus dados têm cookies. No entanto, os dados mais antigos têm apenas o Cookie do Analytics e, em casos raros, os dados mais recentes podem ter apenas uma ECID.<p>Certifique-se de encontrar todos os dados para um visitante identificado por meio de um Cookie (ID de visitante) do Analytics ou uma ECID. Se você usa a ECID e anteriormente usou o Cookie do Analytics, sempre que enviar uma solicitação usando qualquer tipo de ID, você deve incluir ambas as IDs na solicitação ou especificar a variável `expandIds` opção. Ao especificar `expandIds`, o Adobe verifica outras ECIDs ou Cookies do Analytics que correspondem a quaisquer IDs de cookie fornecidas. A solicitação é expandida automaticamente para incluir essas IDs de cookie recentemente identificadas. |
| ID personalizada para expansão de ID de cookies | Em sites de comércio eletrônico, não é incomum que um visitante navegue pelo site, adicione itens ao carrinho e inicie o processo de finalização antes de fazer logon. Se a ID usada para identificar usuários em uma solicitação de Privacidade de dados for armazenada em uma variável personalizada somente quando o usuário estiver conectado, essa atividade de pré-logon não será associada à ID. Usando a ID de cookies do Analytics, os clientes podem optar por associar a navegação realizada antes do logon com a compra após o logon, pois a ID de cookies persiste durante o logon.<p>Suponhamos que sua implementação armazene uma ID de logon (CRM ID, nome de usuário, número de fidelidade, endereço de email etc., ou um hash referente a qualquer um desses valores) em uma variável personalizada (prop ou eVar) ou ID de visitante personalizada, e usa essa ID para uma solicitação de acesso de Privacidade de dados. O titular dos dados pode se surpreender com o fato de que as informações sobre toda a navegação não são retornadas como parte de uma solicitação de acesso, especialmente se tiver promovido itens que foram visualizados, mas ainda não comprados. Desta forma, o processamento da Privacidade de dados do Analytics suporta a expansão de ID, na qual o Analytics encontra todas as IDs de cookies que ocorram na mesma ocorrência de qualquer ID personalizada e, em seguida, expande a solicitação para também incluir essas IDs.<p>When `expandIDs` for especificada junto com qualquer namespace diferente de um namespace de cookie, a solicitação será expandida para incluir quaisquer IDs de cookie (ECID ou Cookie do Analytics), encontrados em ocorrências que contenham qualquer uma das IDs especificadas. A expansão da ID de cookie, conforme descrito acima, é executada em qualquer ID de cookie recém-encontrada.<p>Quando a variável `expandIDs` é usada para uma solicitação de acesso e a ID especificada tem um rótulo ID-PERSON, então dois conjuntos de arquivos serão retornados. O primeiro conjunto (o conjunto de pessoas) conterá dados somente de ocorrências onde a ID especificada foi encontrada. O segundo conjunto (o conjunto de dispositivos) conterá apenas os dados das ocorrências das IDs expandidas, onde a ID especificada não estava presente. |

{style=&quot;table-layout:auto&quot;}

## Quando usar a expansão de ID

Durante os primeiros meses após a Privacidade de dados entrar em vigor, a grande maioria das solicitações de Privacidade de dados do Analytics não solicitaram expansão de ID. No entanto, cabe a você determinar o valor apropriado para sua organização. Consulte a equipe jurídica para saber se a expansão de ID é necessária para seus dados com as IDs que você usa e os dados coletados no Adobe Analytics.

Uma consideração primária deve ser: Em um dispositivo compartilhado, do qual vários usuários visitaram seu site, o uso da expansão de ID inclui dados de ocorrências de outros usuários do dispositivo, em dados retornados por solicitações de acesso (no arquivo do dispositivo). Mesmo que você tenha seguido as práticas recomendadas de rotulagem (por exemplo, nenhum dado privado é incluído no arquivo do dispositivo, como páginas visitadas), o arquivo do dispositivo contém o número de páginas visitadas e os horários de cada uma dessas visitas. Pergunte a si mesmo: Está tudo bem se você compartilhar essas informações com alguém que pode não ter sido o visitante?

Quando a expansão de ID é *not* usado para uma solicitação de exclusão: se você usar uma ID que não seja de cookie (qualquer ID diferente da ECID ou do cookie do Analytics) para identificar ocorrências que devem ser excluídas e essa ID tiver um rótulo ID-DEVICE, a contagem de visitantes únicos nos relatórios será alterada. Isso ocorre porque somente algumas instâncias das IDs de cookie serão anonimizadas, enquanto outras permanecerão inalteradas. Se você não estiver especificando a expansão de ID, recomendamos que use uma ID de cookie para solicitações ou IDs com um rótulo ID-PERSON.

Quando o Adobe executa a expansão de ID, ele pode exigir uma verificação de dados completa adicional. Isso aumenta o tempo que leva Adobe para concluir a solicitação, normalmente adicionando uma semana ao tempo de processamento.

## Outros sinalizadores de solicitação de Privacidade de dados

Além do sinalizador “expandIDs”, o Analytics suporta dois outros sinalizadores que podem ser transmitidos como parte de uma solicitação de Privacidade de dados. Esses sinalizadores e seus valores padrão são:

```
"analyticsDeleteMethod": "anonymize"
"priority": "normal"
```

No futuro, o `analyticsDeleteMethod` pode suportar um valor de &quot;purge&quot; além do valor padrão de &quot;anonymize&quot;. Quando suportado, fará com que toda a ocorrência seja excluída em vez de simplesmente atualizar os valores de campos de ocorrência que têm rótulos DEL.

Além do valor padrão, a variável `priority` O campo também suporta um valor &quot;low&quot;. Especifique esse valor para solicitações que não são o resultado de uma solicitação do titular dos dados e não possui um requisito legal a ser concluído em 30 dias.

## Usos da API do Privacy Service

>[!IMPORTANT]
>
>Adobe desencoraja o uso da [API Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=pt-BR) por motivos que não sejam solicitações iniciadas por titulares dos dados. A API da Privacidade de dados não é uma ferramenta adequada para a limpeza ou reparo de dados, e terá consequências não intencionais. A API do Privacy Service foi fornecida para ajudar a atender à solicitações de Privacidade de dados, que são sensíveis ao tempo. O uso dessa API para outros propósitos não é suportado pela Adobe e pode afetar a capacidade da Adobe de fornecer solicitações de Privacidade de dados iniciadas por usuários com inversão de alta prioridade para outros clientes da Adobe. Pedimos que você não use a API do Serviço de privacidade para outros propósitos, como limpar dados enviados por acidente para grandes grupos de visitantes.

Além disso, esteja ciente de que os usuários que têm uma ocorrência excluída (atualizada ou em anonimato) como o resultado de uma solicitação de exclusão da Privacidade de dados terão as informações de estado redefinidas. A próxima vez que o visitante retornar ao site, ele será um novo visitante. Todas as atribuições de eVar serão iniciadas novamente, assim como informações como números de visita, referenciadores, primeira página visitada etc. Esse efeito colateral não é desejável para situações em que você deseja limpar campos de dados, e realça o motivo pelo qual a API do Serviço de privacidade é imprópria para este uso.

Entre em contato com seu Gerente de conta (CSM) para coordenar com nossa equipe de consultores de Arquitetura e engenharia para analisar e fornecer um nível de esforço e remover qualquer problemas de PII ou de dados.
