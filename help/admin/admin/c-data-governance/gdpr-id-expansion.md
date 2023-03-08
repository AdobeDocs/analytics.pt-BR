---
description: As IDs enviadas nem sempre cobrem todos os dados de ocorrências que o Analytics pode associar ao titular dos dados. O Analytics pode criar um conjunto expandido de IDs para incluir esses dados associados nas solicitações de Privacidade de dados. Essa opção pode ser solicitada com um parâmetro opcional referente à solicitação de Privacidade de dados enviada adicionado à solicitação JSON
title: Expansão de ID
feature: Data Governance
exl-id: 312a249f-e0e7-44da-bb3d-b19f1bb4c706
source-git-commit: b8640d1387a475e2a9dd082759f0514bd18c1b6e
workflow-type: tm+mt
source-wordcount: '1348'
ht-degree: 100%

---

# Expansão de ID

As IDs enviadas nem sempre cobrem todos os dados de ocorrências que o Analytics pode associar ao titular dos dados. O Analytics pode criar um conjunto expandido de IDs para incluir esses dados associados nas solicitações de Privacidade de dados. Essa opção pode ser solicitada com um parâmetro opcional referente à solicitação de Privacidade de dados enviada adicionado à solicitação JSON:

```
"expandIds": true
```

Para obter mais detalhes, consulte a [Documentação da API da Privacidade de dados](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=pt-BR).


| Tipo | Considerações |
| --- | --- |
| Expansão de ID de cookies | Muitos clientes do Analytics usavam originalmente o [Cookie do Analytics](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-privacy.html?lang=br) (herdado), mas agora estão usando o [Serviço de Identidade da Experience Cloud (ECID)](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR). Somente a ECID existe para os visitantes do site que acessaram pela primeira vez após a transição. No entanto, para aqueles que visitaram pela primeira vez quando apenas o Cookie Legado estava disponível, mas visitaram desde então: alguns de seus dados têm os dois cookies. No entanto, os dados mais antigos têm apenas o Cookie do Analytics e, em casos raros, os dados mais recentes podem ter apenas uma ECID.<p>Certifique-se de encontrar todos os dados referentes a um visitante identificado por meio de um cookie (ID do visitante) do Analytics ou uma ECID. Portanto, se você usa a ECID e anteriormente usava o Cookie do Analytics, quando enviar uma solicitação usando qualquer um dos dois tipos de ID, deverá incluir ambas as IDs na solicitação ou especificar a opção `expandIds`. Ao especificar `expandIds`, a Adobe verificará outras ECIDs ou Cookies do Analytics que correspondem a qualquer ID de cookie que você fornecer. A solicitação será expandida automaticamente para incluir essas IDs de cookie recentemente identificadas. |
| ID personalizada para expansão de ID de cookies | Em sites de comércio eletrônico, não é incomum que um visitante navegue pelo site, adicione itens ao carrinho e inicie o processo de finalização antes de fazer logon. Se a ID usada para identificar usuários referentes a uma solicitação de Privacidade de dados estiver armazenada em uma variável personalizada somente quando o usuário estiver conectado, essa atividade pré-logon não será associada à ID. Usando a ID de cookies do Analytics, os clientes podem optar por associar a navegação realizada antes do logon com a compra após o logon, pois a ID de cookies persiste durante o logon.<p>Suponhamos que sua implementação armazene uma ID de logon (CRM ID, nome de usuário, número de fidelidade, endereço de email etc., ou um hash referente a qualquer um desses valores) em uma variável personalizada (prop ou eVar) ou ID de visitante personalizada, e usa essa ID para uma solicitação de acesso de Privacidade de dados. O titular dos dados pode se surpreender com o fato de que as informações sobre toda a navegação não são retornadas como parte de uma solicitação de acesso, especialmente se tiver promovido itens visualizados, mas ainda não comprados. Desta forma, o processamento da Privacidade de dados do Analytics suporta a expansão de ID, na qual o Analytics encontra todas as IDs de cookies que ocorram na mesma ocorrência de qualquer ID personalizada e, em seguida, expande a solicitação para também incluir essas IDs.<p>Quando `expandIDs` é especificada junto com qualquer namespace que não seja um namespace de cookie, a solicitação será expandida para incluir todas as IDs de cookie (ECID ou Cookie do Analytics), encontradas em ocorrências contendo qualquer uma das IDs especificadas. A expansão da ID do cookie, conforme descrito acima, será executada em qualquer ID de cookie recentemente encontrada.<p>Quando a opção `expandIDs` é usada para uma solicitação de acesso e a ID especificada tiver um rótulo ID-PERSON, dois conjuntos de arquivos serão retornados. O primeiro conjunto (o conjunto de pessoas) conterá dados somente de ocorrências onde a ID especificada foi encontrada. O segundo conjunto (o conjunto de dispositivos) conterá apenas os dados das ocorrências das IDs expandidas, onde a ID especificada não estava presente. |

{style="table-layout:auto"}

## Quando usar a expansão de ID

Durante os primeiros meses após a Privacidade de dados entrar em vigor, a grande maioria das solicitações de Privacidade de dados do Analytics não solicitaram expansão de ID. No entanto, cabe a você determinar o valor apropriado para sua organização. Pergunte à sua equipe jurídica se a expansão de ID é exigida para seus dados com as IDs que você usa e os dados coletados no Adobe Analytics.

Uma consideração principal é que, em um dispositivo compartilhado pelo qual vários usuários visitaram o seu site, usar a expansão de ID incluirá dados de ocorrências de outros usuários do dispositivo em dados retornados pelas solicitações de acesso (no arquivo do dispositivo). Mesmo que você tenha seguido as práticas recomendadas de rotulagem (por exemplo, nenhum dado privado é incluído no arquivo do dispositivo, como páginas visitadas), o arquivo do dispositivo contém o número de páginas visitadas e os tempos de cada uma dessas visitas. Talvez você queira se perguntar: tudo bem se você compartilhar essas informações com alguém que pode não ter sido o visitante?

Quando a expansão de ID *não* é usada para uma solicitação de exclusão: se você usar uma ID que não seja de cookie (qualquer ID diferente da ECID ou do cookie do Analytics) para identificar ocorrências que devem ser excluídas, e essa ID tiver um rótulo ID-DEVICE, a contagem de visitantes únicos nos relatórios será alterada. Isso ocorre porque somente algumas instâncias das IDs de cookie serão anonimizadas, enquanto outras permanecerão inalteradas. Se você não estiver especificando a expansão de ID, recomenda-se usar uma ID de cookie para solicitações ou IDs com um rótulo ID-PERSON.

Quando a Adobe executa a expansão de ID, ela pode exigir uma verificação de dados completa adicional. Isso aumenta o tempo que a Adobe leva para concluir a solicitação, normalmente adicionando uma semana ao tempo de processamento.

## Outros sinalizadores de solicitação de Privacidade de dados

Além do sinalizador “expandIDs”, o Analytics suporta dois outros sinalizadores que podem ser transmitidos como parte de uma solicitação de Privacidade de dados. Esses sinalizadores e seus valores padrão são:

```
"analyticsDeleteMethod": "anonymize"
"priority": "normal"
```

Futuramente, o `analyticsDeleteMethod` poderá suportar um valor “limpeza” além do valor padrão “anonimizar”. Quando suportado, fará com que toda a ocorrência seja excluída em vez de apenas atualizar os valores de campos de ocorrência com rótulos DEL.

Além do valor padrão, o campo  `priority` também aceita o valor “baixo”. Especifique esse valor para solicitações que não sejam o resultado de uma solicitação do titular dos dados e não possua um requisito legal a ser concluído em um período especificado.

## Usos da API Privacy Service

>[!IMPORTANT]
>
>A Adobe não permite a utilização da [API Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=pt-BR) por motivos diferentes de solicitações válidas iniciadas pelo titular dos dados. A API Privacy Service não é uma ferramenta adequada para limpeza ou reparo de dados. Qualquer uso indevido da API Privacy Service para solicitações não iniciadas por titulares de dados terá consequências não intencionais. A API Privacy Service é fornecida a clientes da Adobe para ajudar a atender a solicitações de Privacidade de dados, que têm prazo de validade. A Adobe não oferece suporte à utilização dessa API para outros propósitos, visto que isso poderia afetar a pontualidade da Adobe no que diz respeito ao atendimento de solicitações de privacidade de dados de alta prioridade iniciadas por usuários, provenientes de outros clientes da Adobe. Pedimos que você não use a API Privacy Service para outros propósitos, como limpar dados enviados por acidente para grandes grupos de visitantes.

Além disso, esteja ciente de que os usuários que têm uma ocorrência excluída (atualizada ou em anonimato) como o resultado de uma solicitação de exclusão da Privacidade de dados terão as informações de estado redefinidas. A próxima vez que o visitante retornar ao site, ele será um novo visitante. Todas as atribuições de eVar serão iniciadas novamente, assim como informações como números de visita, referenciadores, primeira página visitada etc. O resultado é indesejável para situações em que você deseja limpar os campos de dados e destaca um motivo pelo qual a API Privacy Service é inadequada para esse uso.

Entre em contato com seu Gerente de conta (CSM) para coordenar com nossa equipe de consultores de Arquitetura e engenharia para analisar e fornecer um nível de esforço e remover quaisquer problemas de PII ou de dados.
