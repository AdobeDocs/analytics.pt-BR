---
description: Exemplos de rótulos de privacidade de dados para variáveis do Adobe Analytics
title: Rótulos de privacidade de dados para variáveis do Analytics
feature: Data Governance
exl-id: b8c2143a-6e8e-465a-979b-aa8176e8d4e8
source-git-commit: c774d05ca3b1f9f45ec118b0e7b8a839a03b87e3
workflow-type: tm+mt
source-wordcount: '3558'
ht-degree: 100%

---

# Rótulos de privacidade de dados para variáveis do Analytics

## Por que rotular os dados? {#why-label}

Os clientes da Adobe, como controladores de dados, são responsáveis por cumprir as leis aplicáveis de privacidade de dados, como o GDPR e a CCPA. Os clientes devem consultar suas próprias equipes jurídicas para determinar como os dados devem ser tratados para cumprir as leis de privacidade de dados. A Adobe entende que cada um de seus clientes tem necessidades exclusivas relacionadas à privacidade, por isso ela permite que seus clientes personalizem as configurações desejadas para o processamento de dados de privacidade. Isso permite que cada cliente único processe solicitações de Privacidade de dados da maneira mais adequada para sua marca e conjunto de dados exclusivo.

O Adobe Analytics fornece ferramentas para rotulação de dados de acordo com sua sensibilidade e restrições contratuais. Os rótulos são importantes para: (1) identificar os titulares de dados; (2) determinar quais dados retornar como parte de uma solicitação de acesso; e (3) identificar campos de dados que devem ser excluídos como parte de uma solicitação de exclusão.

Antes de descobrir quais rótulos devem ser aplicados a quais campos/variáveis, é necessário [compreender as IDs](/help/admin/admin/c-data-governance/data-labeling/gdpr-analytics-ids.md) que você está capturando nos dados do Analytics e decidir quais serão usadas nas solicitações de Privacidade de dados.

A implementação da Privacidade de dados do Adobe Analytics oferece suporte aos seguintes rótulos para dados de identidade, dados sensíveis e governança de dados.

## Rótulos de dados de identidade {#identity-data-labels}

Os rótulos “I” de dados de identidade são usados para classificar dados que podem identificar ou permitir o contato com uma pessoa específica.

| Rótulo | Definição | Outros requisitos |
| --- | --- | --- |
| I1 | Diretamente identificável: dados que podem identificar especificamente ou permitem o contato direto com um indivíduo, como um nome ou um endereço de email. | <ul><li>Não pode ser definido em eventos</li><li>Não pode ser definido nas eVars de merchandising</li></ul> |
| I2 | Indiretamente identificáveis: dados que podem ser usados em combinação com outros dados para identificar ou permitir o contato direto com um indivíduo ou dispositivo.  Não permitem a identificação de um indivíduo por si só, mas podem ser combinados com outras informações (que podem ou não estar em sua posse) para identificar alguém. Exemplos incluem um número de fidelidade do cliente ou uma ID usada pelo sistema de CRM de uma empresa, única para cada um de seus clientes. | <ul><li>Não pode ser definido em eventos</li><li>Não pode ser definido nas eVars de merchandising</li></ul> |

{style="table-layout:auto"}

## Rótulos de dados confidenciais {#sensitive-data-labels}

Os rótulos “S” de dados sensíveis são usados para classificar dados sensíveis, como dados geográficos. Os rótulos de dados confidenciais adicionais serão introduzidos no futuro para identificar outros tipos de informações confidenciais.

| Rótulo | Definição |
| --- | --- |
| S1 | Dados precisos de localização geográfica relacionados à latitude e longitude que podem ser usados para determinar a localização exata de um dispositivo (em 100 metros ou menos). |
| S2 | Dados de localização geográfica que podem ser usados para determinar uma área geográfica delimitada amplamente definida. |

{style="table-layout:auto"}

## Rótulos de governança de dados (Privacidade de dados) {#data-governance-labels}

Os rótulos de governança de dados oferecem aos usuários a capacidade de classificar dados que refletem considerações relativas à privacidade e condições contratuais, a fim de auxiliar os clientes da Adobe a manter a conformidade com os regulamentos e as políticas corporativas.

### Rótulos de acesso da privacidade de dados

| Rótulo | Definição | Outros requisitos |
| --- | --- | --- |
| Nenhum | Selecione esta opção se essa variável não contiver dados que devem ser incluídos nos dados retornados ao titular de dados, como parte de uma solicitação de acesso da privacidade de dados. |  |
| ACC-ALL | Os valores neste campo devem ser incluídos em todas as solicitações de acesso da Privacidade de dados. Se essa ocorrência vier de um dispositivo compartilhado por vários indivíduos, ao aplicar esse rótulo, você, como controlador de dados, estará indicando que é aceitável compartilhar os dados desse campo com qualquer pessoa que tenha acesso ao dispositivo compartilhado. | Os campos com este rótulo serão retornados para todas as solicitações de Privacidade de dados. |
| ACC-PERSON | Os valores deste campo devem apenas ser incluídos em solicitações de acesso da privacidade de dados quando você estiver razoavelmente certo de que a ocorrência originou-se do titular de dados, o que pode ser confirmado pelo fato de a ID da solicitação de privacidade de dados corresponder ao valor do campo ID-PERSON. | Você também deve ter um rótulo ID-PERSON definido em alguma variável dentro desse conjunto de relatórios e enviar solicitações usando essa ID, caso contrário esse rótulo nunca será aplicado. |

{style="table-layout:auto"}

Embora poucas variáveis recebam qualquer um dos outros rótulos, espera-se que os rótulos de acesso sejam aplicados em muitas de suas variáveis. No entanto, cabe a você, com a orientação de sua equipe jurídica, decidir quais dados coletados devem ser compartilhados com os titulares de dados.

### Rótulos de exclusão da privacidade de dados

Ao contrário dos outros rótulos, esses rótulos de Exclusão não são mutuamente exclusivos. Você pode selecionar ambos ou nenhum. Um rótulo [!UICONTROL Nenhum] separado não é necessário, pois o valor [!UICONTROL Nenhum] pode ser indicando simplesmente por não selecionar as opções de exclusão.

Um rótulo de exclusão é necessário apenas para campos que contenham um valor que permita a associação de uma ocorrência ao titular de dados (ou seja, que permita a identificação do titular de dados). Outras informações pessoais (favoritos, histórico de navegação/compras, condições de integridade etc.) não precisam ser excluídas, já que a associação com o titular de dados será encerrada.

| Rótulo | Definição | Outros requisitos |
| --- | --- | --- |
| DEL-DEVICE | Para solicitações de exclusão da Privacidade de dados, os valores nesse campo devem ser anonimizados apenas para as solicitações em que uma ID-DEVICE especificada esteja presente na ocorrência.  Se o mesmo valor aparecer em outras ocorrências que não estão sendo excluídas, essas outras instâncias não serão alteradas. Isso resultará na alteração das contagens nos relatórios que processam contagens específicas neste campo. Em dispositivos compartilhados, isso pode remover identificadores de outros indivíduos, além do titular de dados.  As contagens não são alteradas se esse campo também tiver um rótulo ID-DEVICE e o valor nele for usado como uma ID na solicitação de Privacidade de dados. | <ul><li>Também exige o rótulo I1 ou I2 ou S1</li><li>Não pode ser definido em eventos</li><li>Não pode ser definido nas eVars de merchandising</li></li><li>Não pode ser definido nas Classificações</li><li>É necessário enviar solicitações usando um ID-DEVICE ou definir expandIDs como true, ou esse rótulo nunca será aplicado.</li></ul> |
| DEL-PERSON | Para solicitações de exclusão da Privacidade de dados, os valores nesse campo devem ser anonimizados apenas para as solicitações em que uma ID-PERSON especificada esteja presente na ocorrência.  Se o mesmo valor aparecer em outras ocorrências que não estão sendo excluídas, esses outros valores não serão alterados. Isso resultará na alteração das contagens nos relatórios que processam contagens específicas neste campo. As contagens não são alteradas se esse campo também tiver um rótulo ID-PERSON e o valor nele for usado como uma ID na solicitação de Privacidade de dados. | <ul><li>Também exige o rótulo I1 ou I2 ou S1</li><li>Não pode ser definido em eventos</li><li>Não pode ser definido nas eVars de merchandising</li></li><li>Não pode ser definido nas Classificações</li><li>Você também deve enviar pedidos utilizando um rótulo ID-PERSON definido em alguma variável dentro desse conjunto de relatórios e enviar solicitações usando essa ID, caso contrário esse rótulo nunca será aplicado.</li></ul> |

{style="table-layout:auto"}

### Rótulos de identidade da privacidade de dados

| Rótulo | Definição | Outros requisitos |
| --- | --- | --- |
| Nenhum | Esta variável não contém uma ID que será usada para solicitações de Privacidade de dados. | Você precisa definir um desses outros rótulos somente se esse campo contiver uma ID que será usada ao enviar as solicitações de acesso ou exclusão por meio da [API do Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=pt-BR) ou da interface. |
| ID-DEVICE | Este campo contém uma ID que pode ser usada para identificar um dispositivo para uma solicitação de privacidade de dados, mas não pode distinguir entre usuários diferentes de um dispositivo compartilhado.  Você não precisa especificar este rótulo para todas as variáveis que contenham IDs (os rótulos I1/I2 são destinados a isso). Use esse rótulo se enviar solicitações de Privacidade de dados usando IDs armazenadas nessa variável e quiser pesquisá-la para a ID especificada. | Também exige o rótulo I1 ou I2.<ul><li>Não pode ser definido em eventos</li><li>Não pode ser definido nas eVars de merchandising</li><li>Não pode ser definido nas Classificações</li></ul> |
| ID-PERSON | Este campo contém uma ID que pode ser usada para identificar um usuário autenticado (uma pessoa específica) em uma solicitação de Privacidade de dados.  Você não precisa especificar este rótulo para todas as variáveis que contenham IDs (os rótulos I1/I2 são destinados a isso). Use esse rótulo se for enviar solicitações de Privacidade de dados usando IDs armazenadas nessa variável e quiser pesquisá-la para a ID especificada. | <ul><li>Também exige o rótulo I1 ou I2.</li><li>Não pode ser definido em eventos</li><li>Não pode ser definido nas eVars de merchandising</li><li>Não pode ser definido nas Classificações</li></ul> |

{style="table-layout:auto"}

## Fornecer um namespace ao rotular uma variável como ID-DEVICE ou ID-PERSON {#provide-namespace}

Ao rotular uma variável como ID-DEVICE ou ID-PERSON, você receberá uma solicitação para fornecer um namespace. Você pode usar um namespace definido anteriormente ou definir um novo.

### Usar um namespace definido anteriormente

Se você atribuiu anteriormente um rótulo de ID a outras variáveis em qualquer um dos conjuntos de relatórios na empresa de logon, será possível selecionar um desses namespaces existentes. Reutilize o namespace se essa variável contiver o mesmo tipo de IDs que outras variáveis já rotuladas com esse namespace e você desejar pesquisar todos eles ao enviar uma solicitação.

1. Clique em **[!UICONTROL Selecionar namespace]** e selecione um dos namespace existentes.
1. Clique em **[!UICONTROL Aplicar]**.

![](assets/namespace.png)

### Definir um novo namespace

Você também pode definir um novo namespace. Recomendamos que as sequências de caracteres do namespace sejam limitadas a caracteres alfanuméricos, além de caracteres com sublinhado, traço e espaço. Elas serão inteiramente convertidas para letras minúsculas.

1. Clique em **[!UICONTROL Selecionar namespace]** e digite o título do namespace.

   ![](assets/namespace2.png)

1. Pressione **[!UICONTROL Enter]** para adicionar este namespace. O botão Aplicar será ativado somente agora.
1. Clique em **[!UICONTROL Aplicar]**.

A sequência de caracteres especificada como namespace é a mesma que deve ser usada ao enviar solicitações por meio da API da privacidade de dados como o valor do parâmetro “namespace”. A solicitação fará com que o Adobe Analytics pesquise todas as variáveis em todos os conjuntos de relatórios que compartilham esse namespace com a ID especificada na solicitação.

Você não precisa especificar os rótulos de ID-DEVICE ou ID-PERSON para todas as variáveis que contenham IDs (os rótulos I1/I2 são destinados a isso). Use esse rótulo se for enviar solicitações de Privacidade de dados usando IDs armazenadas nessa variável e quiser pesquisá-la para a ID especificada. Por exemplo, se eVar1 puder conter um endereço de email e eVar2 um nome de usuário de logon, mas as solicitações serão enviadas usando somente o nome de usuário, será possível rotular eVar1 como I1, ACC-PERSON, DEL-PERSON, mas eVar2 como I2, ACC-PERSON, DEL-PERSON, ID-PERSON com o namespace “nome de usuário”. Em seguida, você pode enviar uma solicitação com um bloco JSON da seção do usuário, como:

```
{
     "namespace": "user name",
     "type": "analytics",
     "value": "rocketman123"
}
```

É aceitável usar o mesmo namespace para variáveis diferentes no mesmo conjunto de relatórios. Por exemplo, algumas implementações personalizadas armazenam uma ID do CRM em uma prop e uma eVar. Se a ID do CRM sempre aparecer em uma delas (como a eVar), e apenas ocasionalmente na outra (a prop), ou seja, nunca nas duas ao mesmo tempo, então apenas a eVar exigirá um rótulo de ID e um namespace, já que a Adobe poderá pesquisar a ID apenas nessa eVar. No entanto, se a ID do CRM ocorrer às vezes em uma variável e, ocasionalmente, na outra, as duas deverão ter o mesmo namespace e a Adobe pesquisará em ambas por ocorrências da ID especificada, como parte de uma solicitação de Privacidade de dados com esse namespace. Você ainda deve ter os rótulos DEL em todas essas variáveis, para que o valor torne-se anônimo independentemente de onde ocorrer.

Como outro exemplo, você pode ter uma ID do CRM que, às vezes, é enviada pela eVar1 e outras pela prop7. Em seguida, você tem uma regra de processamento que copia o valor da eVar1, se existir, para a eVar3. Caso contrário, ela copia o valor da prop7 para a eVar3. Nesse cenário, a eVar3 sempre conterá a ID do CRM, se for conhecida. Portanto, somente a eVar3 exigirá um rótulo de ID-PERSON.

>[!CAUTION]
>
>Os namespaces “visitorId” e “customVisitorId” são reservados para identificar o cookie de rastreamento herdado do Analytics e a ID de visitante do cliente do Analytics. Não use esses namespaces para tráfego personalizado ou variáveis de conversão.

## Tipos de variáveis e seus rótulos de privacidade de dados compatíveis {#variable-types}

A rotulagem da privacidade de dados afeta quatro grandes classes de variáveis do Analytics. Nem todas as variáveis são compatíveis com todos os rótulos. Esta tabela mostra quais variáveis são compatíveis ou não com quais rótulos.

| Tipo de variável | Rótulos suportados | Rótulos não suportados |
|--- |--- |--- |
| <ul><li>Eventos bem-sucedidos personalizados</li><li>eVars de merchandising</li><li>Variáveis com valores múltiplos (mvVars)</li><li>Variáveis de hierarquia</li></ul> | <ul><li>S1/S2</li><li>ACC-ALL, ACC-PERSON</li></ul> | <ul><li>I1/I2</li>  <li>ID-DEVICE, ID-PERSON</li><li>DEL-DEVICE, DEL-PERSON</li></ul> |
| Classificações | <ul><li>I1/I2, S1/S2</li><li>ACC-ALL, ACC-PERSON</li></ul> | <ul><li>ID-DEVICE, ID-PERSON</li><li>DEL-DEVICE, DEL-PERSON</li></ul> |
| <ul><li>Variáveis de tráfego (props)</li><li>Variáveis de comércio (eVars que não são de merchandising)</li></ul> | Todos os rótulos | - |
| Maioria das outras variáveis    (*Consulte as exceções na tabela abaixo*) | ACC-ALL, ACC-PERSON | <ul><li>I1/I2, S1/S2</li><li>ID-DEVICE, ID-PERSON</li><li>DEL-DEVICE, DEL-PERSON)</li></ul> |

{style="table-layout:auto"}

## Variáveis às quais outros rótulos, além de ACC-ALL/ACC-PERSON, podem ser atribuídos ou modificados {#variables}

<table id="table_0972910DB2D7473588F23EA47988381D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Grupo </th> 
   <th colname="col2" class="entry"> Variáveis </th> 
   <th colname="col3" class="entry"> Rótulos modificáveis </th> 
   <th colname="col4" class="entry"> Comentários </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> 
    <ul id="ul_62FA1BAA3B9245909509566D8C03F900"> 
     <li id="li_38F7C4E18ECB42C292370713F502B8EB">Dimensões de conversão </li> 
     <li id="li_41CB61F927CB4402AAB4A62E219CD153">Dimensões de tráfego personalizadas </li> 
    </ul> </td> 
   <td colname="col2"> <p>Todas, exceto classificações </p> </td> 
   <td colname="col3"> <p>Todas </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Classificações </p> </td> 
   <td colname="col3"> <p>Nenhum / I1 / I2 </p> <p>Nenhum / S1 / S2 </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eventos de conversão </p> </td> 
   <td colname="col2"> <p>Todas </p> </td> 
   <td colname="col3"> <p>Nenhum / S1 / S2 </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dimensões e eventos da solução </p> </td> 
   <td colname="col2"> <p>Link para o Activity Map, </p> <p>Página do Activity Map </p> </td> 
   <td colname="col3"> <p>Nenhum / I1 / I2 </p> <p>Nenhum/DEL-DEVICE/DEL-PERSON </p> </td> 
   <td colname="col4"> <p>As variáveis podem conter parâmetros de URL, que podem incluir dados direta ou indiretamente identificáveis. Se a sua implementação não coletar dados identificáveis direta ou indiretamente nessas variáveis, elas não precisarão de rótulos de identidade ou de exclusão. </p> <p>Observe que a exclusão limpa os parâmetros de URL, mas preserva o URL de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dimensões de processamento de dados </p> </td> 
   <td colname="col2"> <p>ID de visitante personalizada </p> </td> 
   <td colname="col3"> <p>ID-DEVICE/ID-PERSON </p> <p>DEL-DEVICE/DEL-PERSON </p> </td> 
   <td colname="col4"> <p>Não é possível remover os rótulos de ID ou DEL (definidos como Nenhum), mas você pode alterá-los para as variantes DEVICE ou PERSON, dependendo da implementação da ID personalizada. </p> <p>Se você não usa a ID de visitante personalizada, essa configuração não é importante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> 
    <ul id="ul_5EB0193732D44A20AEA08CE9DFE01DBD"> 
     <li id="li_F70D969F83314A94BD8567449968EE2F">Dimensões padrão </li> 
     <li id="li_6046764B19FF4679B51E55671C2C0ADB">Dimensões de processamento de dados </li> 
    </ul> </td> 
   <td colname="col2"> <p>Endereço IP </p> <p>Endereço IP 2 </p> </td> 
   <td colname="col3"> <p>DEL-DEVICE/DEL-PERSON </p> </td> 
   <td colname="col4"> <p>Você não pode remover o rótulo de DEL, mas pode alterá-lo para DEL-DEVICE ou DEL-PERSON, ou ambos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Ação do ClickMap (herdado), </p> <p>Contexto do ClickMap (herdado), </p> <p>Página, </p> <p>URL da página, </p> <p>URL da página de entrada original, </p> <p>Referenciador, </p> <p>URL da página de início da visita </p> </td> 
   <td colname="col3"> <p>Nenhum / I1 / I2 </p> <p>Nenhum/DEL-DEVICE/DEL-PERSON </p> </td> 
   <td colname="col4"> <p>As variáveis podem conter parâmetros de URL, que podem incluir dados direta ou indiretamente identificáveis. Se a sua implementação não coletar dados identificáveis direta ou indiretamente nessas variáveis, elas não precisarão de rótulos de identidade ou de exclusão. </p> <p>Observe que a exclusão limpa os parâmetros de URL, mas preserva o URL de base. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Lidar com exclusões {#deletion}

O suporte do Adobe Analytics para solicitações de exclusão da Privacidade de dados foi projetado para minimizar os impactos a relatórios. Na maioria dos casos, as métricas exibidas nos relatórios não devem ser alteradas. Um relatório histórico que foi executado antes de uma exclusão da Privacidade de dados corresponderá ao mesmo relatório executado depois da exclusão. Isso é feito ao desvincular completamente os dados excluídos do titular dos dados, porém mantendo os dados não identificáveis para que os valores relatados permaneçam consistentes.

A tabela a seguir descreve como as variáveis são “excluídas”. Esta não é uma lista completa.

| Variáveis | Método de exclusão |
| --- | --- |
| <ul><li>Variáveis de tráfego (props)</li><li>Variáveis de comércio (eVars)</li></ul> | O valor existente é substituído por um novo valor com a forma “Data Privacy-356396D55C4F9C7AB3FBB2F2FA223482”, onde o valor hexadecimal de 32 dígitos que procede o prefixo “Data Privacy-” é um número aleatório de 128 bits de forte criptografia.<p>Como será substituído por uma sequência de caracteres aleatória, não há como determinar o valor original a partir desse novo valor, nem como derivar o novo valor sabendo o valor original.  Para uma determinada variável, se o valor idêntico ao que está sendo substituído estiver presente em outras ocorrências que também estão sendo excluídas como parte da mesma solicitação de Privacidade de dados, todas as instâncias desse valor serão substituídas pelo mesmo valor novo.<p>Se algumas instâncias de um valor forem substituídas por uma solicitação de exclusão, e uma solicitação posterior excluir outras (novas) instâncias do valor original, o novo valor de substituição será diferente do valor de substituição original. |
| ID de compra | O valor existente é substituído por um novo valor de forma “G-7588FCD8642718EC50”, onde os 18 dígitos hexadecimais que procedem o prefixo “G-” são os primeiros 18 dígitos de um número aleatório de 128 bits criptograficamente forte. Todos os comentários que aplicam-se a variáveis de comércio e à exclusão de tráfego são aplicáveis a essa situação.<p>A ID de compra é uma ID de transação cuja finalidade principal é garantir que uma compra não seja creditada duas vezes, por exemplo quando alguém atualizar a página de confirmação da compra. A ID propriamente dita pode vincular a compra a uma linha no seu próprio banco de dados, onde a compra é registrada. Na maioria dos casos, não é necessário excluir essa ID, portanto ela não é excluída por padrão.<p>Caso ainda seja possível vincular a compra a um usuário depois da solicitação de exclusão da Privacidade de dados de seus dados, pode ser necessário excluir este campo, para que os dados do Analytics referentes ao visitante não possam ser vinculados ao comprador. |
| ID de visitante | O valor é um inteiro de 128 bits e é substituído por um número aleatório de 128 bits criptograficamente forte. |
| <ul><li>MCID</li><li>ID de visitante personalizada</li><li>Endereço IP</li><li>Endereço IP 2 | O valor é limpo (definido como uma cadeia de caracteres vazia ou 0, dependendo do tipo da variável). |
| <ul><li>Ação do ClickMap (herdado)</li><li>Contexto do ClickMap (herdado)</li><li>Página</li><li>URL da página</li><li>URL da página de entrada original</li><li>Referenciador</li><li>URL da página de início da visita</li></ul> | Os parâmetros de URL são limpos/removidos. Se o valor não tiver a aparência de um URL, ele será limpo (definido como uma sequência de caracteres em branco). |
| <ul><li>Latitude</li><li>Longitude</li></ul> | A precisão é reduzida para não ter mais de 1 km. |

{style="table-layout:auto"}

## Variáveis que podem não ser compatíveis com os rótulos de exclusão esperados {#no-delete-support}

Esta seção pretende esclarecer informações sobre as variáveis do Analytics que podem não ter suporte à exclusão. Às vezes, essas variáveis são excluídas por usuários que não usam o Analytics (como a equipe jurídica), os quais não compreendem os tipos de dados contidos na variável e fazem apenas suposições com base no nome da variável.

É importante entender quais tipos de dados estão contidos em cada variável antes de tomar uma decisão sobre rotulagem ou exclusão, e não depender apenas do nome da variável. Veja a seguir uma lista de algumas dessas variáveis e por que elas podem não exigir a exclusão, ou por que elas podem não exigir um rótulo de exclusão específico:

| Variável | Comentários |
| --- | --- |
| [!UICONTROL ID de novo visitante] | A ID de novo visitante é um booleano definido como “true” na primeira vez que vemos uma certa ID de visitante. Não é necessário excluí-la quando a ID do visitante for tornar-se anônima. Depois da anonimização, ela corresponde à primeira vez que vimos essa ID anonimizada. |
| [!UICONTROL Código postal]<p>[!UICONTROL Código postal geográfico (Zip codes)] | Os códigos postais (Zip codes) são definidos somente para ocorrências originadas nos EUA. Eles não são definidos para ocorrências provenientes da UE. Mesmo quando definidos, eles só fornecem uma área geográfica ampla que dificulta a reidentificação do titular de dados. |
| [!UICONTROL Latitude geográfica]<p>[!UICONTROL Longitude geográfica] | Fornecem um local aproximado derivado do endereço IP. A precisão é geralmente semelhante à do código postal (zip code), dentro de algumas dezenas de quilômetros do local real. |
| [!UICONTROL Agente do usuário] | O Agente do usuário identifica a versão do navegador que foi usada. |
| [!UICONTROL ID de usuário] | Especifica o conjunto de relatórios do Analytics (como um número) que contém os dados. |
| [!UICONTROL ID do conjunto de relatórios] | Especifica o nome do conjunto de relatórios do Analytics que contém os dados. |
| [!UICONTROL ID de visitante]<p>[!UICONTROL MCID] / [!UICONTROL ECID] | Essas IDs têm um rótulo DEL-DEVICE, mas o rótulo DEL-PERSON não pode ser adicionado. Se especificar a [!UICONTROL Expansão de ID] em cada solicitação, essas IDs serão automaticamente excluídas para todas as solicitações de exclusão, mesmo aquelas que usam um ID-PERSON.<p>Se você não usar a Expansão de ID, mas desejar que essas IDs de cookie sejam anonimizadas em ocorrências que contenham uma ID correspondente em uma prop ou eVar, poderá contornar essa limitação de rotulação, modificando a prop ou eVar com um rótulo ID-DEVICE, mesmo que isso realmente identifique uma pessoa (todos os rótulos DEL-PERSON também precisam ser alterados para rótulos DEL-DEVICE). Nesse caso, já que somente algumas instâncias da ID de visitante ou da ECID estão sendo anonimizadas, as contagens de visitantes únicos mudarão em um relatório histórico. |
| [!UICONTROL ID do AMO] | A Adobe Advertising Cloud ID é uma variável de solução que tem um rótulo [!UICONTROL DEL-DEVICE] não modificável. Ela é preenchida a partir de um cookie, assim como a ID do visitante e a MCID. Ela deve ser excluída das ocorrências sempre que essas outras IDs forem excluídas. Consulte a descrição referente a essas variáveis para obter mais detalhes. |

{style="table-layout:auto"}

## Campos de data para solicitações de acesso {#access-requests}

Há cinco variáveis padrão que contêm carimbos de data e hora:

| Carimbo de data e hora | Definição |
| --- | --- |
| Horário da ocorrência em UTC | O horário que o Adobe Analytics recebeu a ocorrência. |
| Horário personalizado da ocorrência em UTC | O horário da ocorrência, que para alguns aplicativos móveis e outras implementações pode ser anterior ao horário em que foi recebida. Por exemplo, se uma conexão de rede não estava disponível no momento em que ocorreu, o aplicativo pode manter a ocorrência e enviá-la quando uma conexão for disponibilizada. |
| Data e hora | Mesmo valor de Horário personalizado da ocorrência em UTC, mas no fuso horário do conjunto de relatórios, em vez de GMT. |
| Horário da primeira ocorrência (GMT) | O valor de Horário personalizado da ocorrência em UTC referente à primeira ocorrência recebida para o valor de ID de visitante desta ocorrência. |
| Horário inicial da visita em UTC | O valor de Horário personalizado da ocorrência em UTC referente à primeira ocorrência recebida para a visita atual para esta ID de visitante. |

{style="table-layout:auto"}

O código para geração de arquivos retornados por solicitações de Privacidade de dados de acesso exige que pelo menos uma das primeiras três variáveis de carimbo de data e hora sejam incluídas na solicitação de acesso (tenham um rótulo ACC aplicável ao tipo de solicitação). Se não forem incluídas, o Horário personalizado da ocorrência em UTC será tratado como se tivesse um rótulo ACC-ALL.

O arquivo CSV em nível de ocorrência retornado para solicitações de acesso da Privacidade de dados converterá os valores desses campos de carimbos de data e hora unix em campos de data e hora no formato AAAA-MM-DD HH:MM:SS (por exemplo, 2018-05-01 13:49:22). No arquivo HTML de resumo, esses valores de carimbos de data e hora serão truncados para incluir somente a data, no formato AAAA-MM-DD, para reduzir o número de valores únicos que ocorrem para tais campos.
