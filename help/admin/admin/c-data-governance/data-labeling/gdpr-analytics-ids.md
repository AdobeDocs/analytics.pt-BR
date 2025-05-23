---
description: Entenda as IDs capturadas nos dados do Analytics e decida quais serão usadas para as solicitações de Privacidade de dados.
title: Práticas recomendadas de rotulagem
feature: Data Governance
role: Admin
exl-id: 00da58b0-d613-4caa-b9c1-421b1b541f47
source-git-commit: 3e87d420591405e57e57e18fda4287d5fbd3bf1b
workflow-type: ht
source-wordcount: '2287'
ht-degree: 100%

---

# Práticas recomendadas de rotulagem

A rotulagem precisa ser analisada sempre que um novo conjunto de relatórios for criado ou quando uma nova variável for habilitada em um conjunto de relatórios existente. Você também pode analisar a rotulagem quando novas integrações da solução forem ativadas, pois elas podem expor novas variáveis que podem exigir rótulos. A reimplementação de aplicativos ou sites móveis pode alterar como as variáveis existentes são usadas, o que também pode exigir atualizações nos rótulos.

Os rótulos I1, I2, S1 e S2 têm o mesmo significado que os rótulos DULE nomeados de forma correspondente na Adobe Experience Platform. No entanto, eles são usados para fins muito diferentes. No Adobe Analytics, esses rótulos são usados para ajudar a identificar campos que devem ser anonimizados como resultado de uma solicitação do serviço de privacidade. Na Adobe Experience Platform, eles são usados para controle de acesso, gerenciamento de consentimento e aplicação de restrições de marketing em campos rotulados. A Adobe Experience Platform permite vários rótulos adicionais que não são usados pelo Adobe Analytics. Se você utilizar o conector de dados do Analytics para importar os dados do Adobe Analytics para a Adobe Experience Platform, será necessário garantir que os rótulos I1, I2, S1 e S2 aplicados no Adobe Analytics também sejam aplicados aos esquemas na Adobe Experience Platform usados pelos conjuntos de relatórios importados.

## IDs identificáveis direta vs indiretamente  {#direct-vs-indirect}

Antes de descobrir quais rótulos devem ser aplicados aos campos/variáveis, primeiro é necessário compreender as IDs que você está capturando nos dados do Analytics e decidir quais serão usadas nas solicitações de Privacidade de dados. A Privacidade de dados expande o escopo do que pode ser considerado uma ID. As IDs são classificadas em duas grandes classes: diretamente identificáveis (rótulo de identidade: I1) e indiretamente identificáveis (rótulo de identidade: I2).

* **Uma ID diretamente identificável (I1)**: nomeia a pessoa ou fornece um método direto para entrar em contato com ela. Exemplos incluiriam o nome de alguém (até mesmo um nome comum como John Smith, que pode ser compartilhado por centenas de pessoas), um endereço de email ou números de telefone, entre outros. Um endereço de correspondência sem um nome pode ser considerado diretamente identificável, mesmo que só possa identificar um domicílio ou empresa, e não uma pessoa específica dentro desse agregado familiar ou empresa.
* **Uma ID indiretamente identificável (I2)**: não permite a identificação de um indivíduo por si só, mas pode ser combinada com outras informações (que podem ou não estar em sua posse) para identificar alguém. Exemplos de uma ID identificável indiretamente incluem um número de fidelização do cliente ou uma ID usada pelo sistema de CRM de uma empresa que seja única para cada um de seus clientes. Na Privacidade de dados, as IDs anônimas armazenadas nos cookies de rastreamento usados pelo Analytics podem ser consideradas como indiretamente identificáveis, embora possam identificar apenas um dispositivo e não um indivíduo. Em um dispositivo compartilhado, esses cookies não são capazes de distinguir os diferentes usuários do sistema. Por exemplo, apesar de o cookie não poder ser usado para localizar um computador que o contém, se alguém tiver acesso ao computador e localizar o cookie, esse indivíduo poderá vincular os dados de cookie do Analytics novamente ao computador.

Um endereço IP também é considerado como indiretamente identificável porque ele só pode ser atribuído a um único dispositivo em um determinado momento. No entanto, os ISPs podem mudar, e frequentemente mudam, os endereços IP para a maioria dos usuários; assim, ao longo do tempo, um endereço IP pode ter sido usado por qualquer um dos seus usuários. Também não é incomum que muitos clientes de um ISP ou vários funcionários de uma empresa que usem uma intranet compartilhem o mesmo endereço IP externo. Por causa disso, a Adobe não oferece suporte ao uso de um endereço IP como uma ID para uma solicitação de Privacidade de dados. Entretanto, quando uma ID que aceitamos for usada como parte de uma solicitação de exclusão, também apagaremos os endereços IP que ocorreram com essa ID. Você deve decidir se existem outras IDs coletadas que possam se enquadrar nessa categoria, de I1 ou I2, mas que não sejam adequadas para o uso como uma ID diferencial nas solicitações de Privacidade de dados.

Mesmo que sua empresa colete várias IDs diferentes nos dados do Analytics, é possível optar por usar apenas um subconjunto dessas IDs nas solicitações de Privacidade de dados. Os motivos disso podem incluir:

* Nos seus próprios sistemas, é possível mapear uma das IDs (por exemplo, endereço de email) a uma ID diferente (como a ID do CRM). Então, por questões de consistência, você decide usar somente a ID do CRM nas solicitações de Privacidade de dados em seu processamento da Privacidade de dados.
* Você não tem um método para validar se alguém é realmente a pessoa associada à ID. Por exemplo, pode ser muito difícil validar se um endereço IP foi usado somente por uma pessoa e se quem enviou a solicitação é realmente essa pessoa.
* Algumas IDs podem corresponder a várias pessoas e você não deseja correr o risco de retornar informações sobre uma pessoa para outra com a mesma ID. Por exemplo, mesmo se for possível verificar que o nome de alguém é John Smith, talvez você não queira retornar todos os dados sobre todos os John Smiths em seu sistema.
* Outro exemplo é uma ID de dispositivo, como a ID de cookies do Analytics. Se a ID ocorrer em um aplicativo de telefone celular, será possível decidir se todas as interações que usam essa ID devem estar disponíveis para o proprietário do telefone celular. No entanto, se acontecer em um dispositivo compartilhado, como um computador doméstico ou de uma biblioteca ou cafeteria, você pode decidir que não é possível distinguir os usuários do dispositivo e o risco de retornar dados para um usuário diferente é muito grande para permitir o uso deste tipo de ID.

## Práticas recomendadas para IDs compatíveis com o Analytics {#best-practices-an}

Use esta tabela para determinar os tipos de IDs que serão usadas ao enviar solicitações de Privacidade de dados para o Analytics. Quando souber essas informações, será mais fácil determinar os outros rótulos que deverão ser usados para as variáveis.

<table id="table_E25612E32A03449A8E5DA00B88FCEB9E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de ID </th> 
   <th colname="col2" class="entry"> Recomendações </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>IDs de cookies </p> 
    <ul id="ul_CB43CEA3054E490585CBF3AB46F95B5B"> 
     <li id="li_9174CB3910AF4EF8BA7165DB537765A5"> <a href="https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-privacy.html?lang=pt-BR">Cookie do Analytics (herdado)</a> </li> 
     <li id="li_7B6A9A788BBD47428315B3893FC07BC3"> <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR"> Cookie do serviço de identidade </a> (ECID), anteriormente conhecido como Marketing Cloud ID (MCID) </li> 
    </ul> </td> 
   <td colname="col2"> <p>Esses cookies identificam um dispositivo ou, mais especificamente, um navegador para um usuário de um dispositivo. Em um dispositivo compartilhado no qual um logon comum é usado, essa ID pode se aplicar a qualquer/todos os usuários do dispositivo. A Adobe criou alguns <a href="https://developer.adobe.com/experience-platform-apis/references/privacy-service/">JavaScript unificados</a> que você pode colocar no site para coletar esses cookies se quiser permitir que eles sejam usados nas solicitações de Privacidade de dados. </p> <p>Os usuários do SDK móvel do Adobe Analytics também têm uma Experience Cloud ID (ECID). Existem chamadas de API no SDK para ler essa ID, de forma que possa otimizar o aplicativo para coletá-la durante uma solicitação de Privacidade de dados. </p> <p>Muitas empresas consideram as IDs de cookies do navegador como IDs de dispositivos compartilhados. Como resultado, após consultarem suas equipes jurídicas, elas podem optar por não apoiar o uso delas como IDs aceitáveis nas solicitações de Privacidade de dados. Como alternativa, eles podem optar por retornar apenas uma quantidade muito limitada de dados quando essas IDs forem usadas ou podem só aceitá-las para solicitações de exclusão. </p> <p>Esses cookies têm um rótulo ID-DEVICE que não pode ser alterado (assim como os rótulos I2 e DEL-DEVICE). A configuração padrão do Adobe Analytics retornará apenas informações genéricas sobre o dispositivo, como o tipo de dispositivo, o sistema operacional, o navegador, entre outros, bem como a hora/data em que o site foi visitado ao usar essas IDs. No entanto, se optar por oferecer suporte a essas IDs nas solicitações de Privacidade de dados, conforme discutido abaixo, é possível adicionar ou remover os rótulos de ACC-ALL para configurar o conjunto exato de campos que deseja retornar em uma solicitação de acesso da Privacidade de dados. </p> <p>Se o conjunto de relatórios corresponder a um aplicativo móvel que requer logon, você pode decidir que a ID da Experience Cloud do dispositivo corresponde a um usuário específico. Nesse caso, talvez você queira rotular mais campos com o rótulo de ACC-ALL, incluindo os nomes das páginas visitadas, os produtos visualizados etc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IDs em variáveis personalizadas </p> </td> 
   <td colname="col2"> <p>Alguns clientes adicionam IDs em <a href="https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/evar.html?lang=pt-BR">variáveis de tráfego personalizadas (props) ou em variáveis de conversão personalizadas (eVars)</a>. Embora o mais comum seja um ID de CRM, outros incluem endereços de email, nomes de usuário para logon, números de fidelidade do cliente ou hashes desses valores. </p> 
    <ul id="ul_0B9492CF786046BB97E31CCF83A85FEA"> 
     <li id="li_D35B61CC6A8B485A8E09358A46D3F598">Se quiser usar uma dessas IDs nas solicitações de Privacidade de dados, deverá fornecer um rótulo ID-PERSON ao campo que a contém. </li> 
     <li id="li_94541340B054436297C5565F074413DC">(Muito menos comum) Se uma ID em uma dessas variáveis personalizadas identificar apenas um dispositivo que pode ser compartilhado por várias pessoas, será possível usar um rótulo ID-DEVICE. </li> 
     <li id="li_8115B999E8DA46CAB359BCF1F4A4DCAE">Esses campos também exigem os rótulos I1 ou I2 e devem incluir um rótulo DEL-PERSON ou DEL-DEVICE. Normalmente, a opção PERSON/DEVICE do rótulo DEL corresponderá à opção PERSON/DEVICE do rótulo de ID. </li> 
    </ul> <p> É raro um conjunto de relatórios ter mais de uma ou duas variáveis personalizadas contendo IDs que você gostaria de usar para identificar os titulares dos dados nas solicitações de Privacidade de dados. É possível ter várias variáveis com os rótulos I1 ou I2, mas tipicamente, apenas uma ou duas delas também terão os rótulos ID-PERSON ou ID-DEVICE. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de visitante personalizada </p> </td> 
   <td colname="col2"> <p>Embora isso não seja amplamente usado, o Analytics também oferece suporte a uma implementação na qual uma ID de visitante personalizada pode ser fornecida e, se presente, é usada no lugar do cookie de rastreamento herdado do Analytics. Este campo possui os rótulos I2, ID-PERSON e DEL-PERSON. </p> <p>Muitas implementações derivam essa ID de uma ID de CRM, para que ela esteja presente somente enquanto alguém estiver conectado ao site. Isso permite que uma mesma ID de visitante personalizada seja usada em vários dispositivos. Uma desvantagem técnica é que o rastreamento que acontece antes do logon do usuário não pode ser vinculado ao rastreamento coletado após o logon. Se, em vez disso, você usar a ID de visitante personalizada para simplesmente identificar um dispositivo, altere os rótulos ID-PERSON e DEL- PERSON para ID-DEVICE e DEL- DEVICE, respectivamente. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Práticas recomendadas para definir rótulos de exclusão {#best-practices-delete}

>[!NOTE]
>
>Props sempre diferenciam maiúsculas de minúsculas. As eVars não diferenciam maiúsculas de minúsculas por padrão, mas podem ser configuradas pelo Atendimento ao cliente da Adobe para fazer essa diferenciação. Se você tiver uma eVar que diferencie maiúsculas e minúsculas e que contenha uma ID, é sua responsabilidade usar a capitalização adequada ao enviar uma solicitação de Privacidade de dados, de modo que a letra usada na solicitação corresponda à letra usada nas ocorrências que contêm essas IDs.

Os rótulos de exclusão DEL-DEVICE e DEL-PERSON devem ser usados com moderação. Quando aplicada a uma variável que não contém uma ID usada como parte da solicitação de Privacidade de dados, as contagens (métricas) nos relatórios históricos do Analytics quase sempre serão alteradas.

* Recomendamos que um desses rótulos seja aplicado a qualquer variável identificada como I1, I2 ou S1. Eles não podem ser aplicados a qualquer variável que não esteja rotulada com I1, I2 ou S1.
* Os rótulos DEL resultarão na [anonimização](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md#data-governance-labels) dessas variáveis (a ID será substituída por uma sequência de caracteres aleatória com o prefixo “Privacidade de dados-”). O mesmo valor anonimizado substituirá todas as instâncias do valor original em todas as ocorrências que foram identificadas por uma ID usada na solicitação. Se o valor original desse campo for uma dessas IDs, as métricas de relatório não serão alteradas.
* Geralmente, se um campo tiver o rótulo ID-DEVICE, você também deverá atribuir o rótulo DEL-DEVICE.
* Da mesma forma, se um campo tiver o rótulo ID-PERSON, você também deverá atribuir o rótulo DEL-PERSON.
* Se um campo não tiver um rótulo de ID, mas contiver informações de identificação que você deseja anonimizar, o rótulo apropriado (DEVICE ou PERSON) dependerá da sua implementação. Se você usar apenas IDs de cookies nas solicitações de Privacidade de dados, use DEL-DEVICE.
* Se você usar IDs personalizadas em um campo diferente com um rótulo ID-PERSON e desejar que a informação seja apagada somente nas linhas em que essa ID ocorre, use DEL-PERSON.
* Observe que, se um rótulo de DEL-DEVICE ou DEL-PERSON for especificado em qualquer variável que também não seja usada como uma ID para essa solicitação (incluindo uma ID expandida), os valores únicos nessa variável serão anonimizados apenas em ocorrências que tiverem uma ID especificada (ou expandida). Se outras ocorrências contiverem o mesmo valor, elas não serão atualizadas nesses outros locais. Isso pode resultar em alterações de contagens (métricas).

  Por exemplo, se você tiver três ocorrências contendo o valor “foo” na eVar7, mas apenas uma delas também contiver uma ID em uma variável diferente que corresponde a uma exclusão, então “foo” nessa ocorrência será modificado para um valor como “Privacidade de dados-123456789” e permanecerá inalterado nas outras duas ocorrências. Um relatório que mostra o número de valores únicos para eVar7, agora, também mostrará mais um valor único. Um relatório que mostra os principais valores para eVars pode incluir “foo” com apenas duas instâncias (em vez de três, como anteriormente), e o novo valor também será exibido com uma única instância.

## Práticas recomendadas para definir rótulos de acesso {#best-practices-access}

Embora pouquíssimos campos tenham um dos outros rótulos, é comum que um grande número de campos tenha rótulos ACC. Os rótulos de acesso apropriados dependerão das IDs que você está usando nas solicitações de Privacidade de dados.

<table id="table_A5B834CC08C641D99E2691A2361997E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Se você usar... </th> 
   <th colname="col2" class="entry"> ...use estas Recomendações </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Somente IDs de dispositivos </p> </td> 
   <td colname="col2"> <p>Se as únicas IDs usadas forem IDs de cookies ou aquelas com um rótulo de ID-DEVICE, você deverá usar somente o rótulo de ACC-ALL. </p> <p>Você obterá um par de arquivos para cada solicitação de acesso: um arquivo contendo uma linha para cada ocorrência correspondente com todos os campos ACC-ALL especificados e um arquivo de resumo contendo um resumo desses dados. </p> </td> 
  </tr> 
 </tbody> 
</table>
