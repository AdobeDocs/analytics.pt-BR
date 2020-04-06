---
description: 'null'
title: Enviar solicitações de acesso e de exclusão
uuid: d006cd5c-e3cd-4385-8683-acaf73cb681b
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Enviar solicitações de acesso e de exclusão


## Visão geral {#section_BD70882995894C1CA19C205C49FEC23C}

Se seus clientes (consumidores/titulares de dados) quiserem saber quais dados você mantém sobre eles ou decidirem que desejam ser excluídos de suas propriedades do Analytics, você, como o controlador dos dados, é responsável por responder a essas solicitações. O controlador de dados determina como sua organização interage com titulares de dados (por exemplo, por meio de um portal de usuário do titular dos dados) e gerencia as interações com eles. Também é responsabilidade do controlador fechar o ciclo com a pessoa de dados quando a solicitação for atendida. Em outras palavras, a Adobe Experience Cloud, como processador de dados, não aceitará solicitações diretamente dos titulares dos dados nem retornará dados diretamente para eles. Em vez disso, a Adobe receberá solicitações e retornará dados somente para você como o controlador de dados.

Você também pode garantir que seus aplicativos e sites móveis tenham avisos pop-up relevantes e materiais de suporte sobre os direitos das pessoas em relação aos dados diretamente identificáveis ou indiretamente identificáveis, e outros dados coletados.

## Gerenciar o consentimento do consumidor {#section_3012015E7E8942519FB9279CF7057EAB}

Você, como o controlador de dados, é responsável por obter consentimento explícito de seus titulares de dados antes de coletar dados sobre eles (possivelmente incluindo dados do Adobe Analytics) e por [implementar um mecanismo de recusa](https://marketing.adobe.com/resources/help/pt_BR/dtm/opt-in.html) no seu site. Isso permite que seus titulares de dados optem por cancelar a coleta de dados futura da Adobe Experience Cloud.

## Validar usuários e seus dados {#section_AFB2CC225AA94AF6A3CE9F24EF788358}

Você, como controlador de dados, é responsável por verificar se o titular dos dados é quem diz ser e se tem direito aos dados que está solicitando. Além disso, é sua responsabilidade garantir que os dados corretos sejam retornados ao titular dos dados e que ele não receba, inadvertidamente, dados sobre outros titulares.

Isso inclui revisar os dados retornados pelo Adobe Analytics como parte de uma solicitação de acesso da Privacidade de dados antes de enviá-los ao titular dos dados. Cuidado especial deve ser tomado se estiver usando IDs de pessoa e retornando não somente os dados nos quais essa ID está presente, como também os dados de outras ocorrências em um dispositivo compartilhado no qual essa ID estava ocasionalmente presente. Consulte [Expansão de ID.](/help/admin/c-data-governance/gdpr-id-expansion.md)

Cada arquivo combina dados de todos os seus conjuntos de relatórios, removendo automaticamente cópias adicionais de ocorrências replicadas. Você pode decidir quais desses arquivos retornar ao titular dos dados. Ou você pode extrair alguns desses dados e combiná-los com dados de outros sistemas antes de retorná-los à pessoa em questão.

## Enviar solicitações {#submit-requests}

Você pode enviar acesso à Privacidade de dados e excluir solicitações por meio do portal da [interface do usuário da Privacidade de dados](https://www.adobe.io/apis/experienceplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md) ou por meio da nossa [API da Privacidade de dados.](https://www.adobe.io/apis/experienceplatform/gdpr.html)

>[!NOTE] A API de Privacidade de dados suporta envios em massa para vários usuários em uma única solicitação. O limite suportado atualmente é de 1.000 usuários separados (podem ter várias IDs por usuário) em um único arquivo JSON de solicitação.

## Solicitação JSON de exemplo {#sample-json-request}

Este é o JSON que pode ser enviado por meio da API da Privacidade de dados ou da interface do usuário, solicitando o processamento da Privacidade de dados para três usuários.

```
{ 
    "companyContexts": [ 
        { 
            "namespace": "imsOrgID", 
            "value": "5D7236525AA6D9580A495C6C@AdobeOrg" 
        } 
    ], 
    "users": [ 
        { 
            "key": "Data Privacy-1234", 
            "action": ["access"], 
            "userIDs": [ 
                { 
                    "namespace": "AAID", 
                    "namespaceId", 10, 
                    "type": "standard", 
                    "description": "Legacy Visitor ID", 
                    "value": "2D783E5885312539-4000010360000181", 
                } 
            ] 
        }, 
        { 
            "key": "Data Privacy-1235", 
            "action": ["access"], 
            "userIDs": [ 
                { 
                    "namespace": "ECID", 
                    "namespaceId": 4, 
                    "type": "standard", 
                    "description": "This is the ID generated by the Adobe ID service.", 
                    "value": "22470866493385587460528148368265592748", 
                } 
            ] 
        }, 
        { 
            "key": "Data Privacy-1236", 
            "action": ["access","delete"], 
            "userIDs": [ 
                { 
                    "namespace": "CRM-ID", 
                    "type": "analytics", 
                    "description": "namespace defined on eVar17 in some report suites", 
                    "value": "ACME-12345678"
                }, 
                { 
                    "namespace": "email address", 
                    "type": "analytics", 
                    "description": "namespace defined on eVar23 in some report suites", 
                    "value": "john@mail.com" 
                } 
            ] 
        } 
    ], 
    "expandIds": true 
} 
```

Observe que há três blocos na seção do usuário, representando três solicitações separadas, provavelmente, para três titulares de dados separados.

* A primeira solicitação é uma solicitação de acesso usando uma ID de cookie tradicional do Adobe Analytics (AAID).
* A segunda solicitação também é uma solicitação de acesso, mas está usando um cookie MCID/ECID.
* A terceira solicitação é de acesso e exclusão para as IDs especificadas. Embora a Expansão de ID seja especificada para todas as solicitações, isso terá o maior impacto nesta terceira solicitação, pois é a única que usa IDs que não são de cookies. Como resultado, essa solicitação também descobrirá IDs de cookie associadas a qualquer dispositivo com a CRM-ID ou endereço de email especificado e expandirá a solicitação para incluir essas IDs também.

Lembre-se

* O valor &quot;5D7236525AA6D9580A495C6C@AdobeOrg&quot; na seção &quot;companyContexts&quot; deve ser atualizado com o valor da própria organização da Experience Cloud.
* Os campos &quot;type&quot; e &quot;namespace&quot; são descritos em mais detalhes na seção [Namespaces](/help/admin/c-data-governance/gdpr-namespaces.md).
* Os campos &quot;description&quot; são ignorados.
* Os campos &quot;key&quot; podem conter qualquer valor desejado. Se tiver uma ID interna que esteja usando para rastrear as solicitações de Privacidade de dados, insira esse valor para facilitar a correspondência das solicitações do sistema da Adobe com as de seus próprios sistemas.

## Detalhes de resposta {#section_93F554F65DBB48A18B75EB5784056C96}

Esta seção contém detalhes sobre acesso e exclusão de respostas.

**Detalhes da resposta de acesso**

Os dados retornados para uma solicitação de acesso fornecem a você, o controlador de dados, um URL que você pode usar para baixar um arquivo ZIP contendo um diretório para cada produto da Adobe que você possui. Na pasta do Analytics, pode haver:

* Arquivos de pessoas - derivados de ocorrências que contêm um rótulo ID-PERSON correspondente

   * Um arquivo .CSV com uma linha para cada ocorrência correspondente e uma coluna para cada campo com um rótulo ACC-ALL ou ACC-PERSON, classificado por carimbo de data e hora.
   * Um arquivo HTML de resumo com uma entrada para cada rótulo de ACC-ALL ou ACC-PERSON. Cada entrada lista todos os valores únicos para esse campo e o número de vezes que cada um ocorreu. Os campos que contêm carimbos de data e hora são arredondados para especificar somente dias exclusivos.

* Arquivos de dispositivo - derivados de ocorrências em que um dos campos correspondia a um ID-DEVICE especificado, mas nenhum correspondia a um ID-PERSON especificado

   * Um arquivo .CSV com uma linha para cada ocorrência correspondente e uma coluna para cada campo com um rótulo ACC-ALL, classificado por carimbo de data e hora.
   * Arquivo de resumo HTML com uma entrada para cada rótulo ACC-ALL. Cada entrada lista todos os valores exclusivos para esse campo e o número de vezes que cada um ocorreu. Os campos que contêm carimbos de data e hora são arredondados para especificar somente dias exclusivos.

Cada arquivo combina dados de todos os seus conjuntos de relatórios, removendo automaticamente cópias adicionais de ocorrências replicadas.

Você pode decidir qual deles retornar para a pessoa de dados. Ou você pode extrair alguns desses dados e combiná-los com dados de outros sistemas antes de retorná-los à pessoa em questão.

**Excluir Detalhes da Resposta**

Nenhum dado é retornado nas solicitações de exclusão; apenas um status para a API da Privacidade de dados de que a solicitação foi concluída com êxito.

## Testar o processamento da Privacidade de dados em seus dados {#section_FBA843DBFAE64D979D8DB8A3C56784D7}

Normalmente, os clientes do Analytics configurarão alguns conjuntos de relatórios de teste para verificar a funcionalidade antes que ela seja disponibulizada para o público em geral. Os sites ou aplicativos de pré-produção enviarão dados para esses conjuntos de relatórios de teste/desenvolvimento/QA para avaliar como as coisas funcionarão quando o código for lançado antes que o tráfego real seja enviado para os conjuntos de relatórios de produção.

No entanto, com uma configuração normal, o processamento de solicitação de GDPR não pode ser testado primeiro nesses conjuntos de relatórios de teste, antes de aplicar solicitações a conjuntos de relatórios de produção. O motivo é que uma solicitação de Privacidade de dados é aplicada automaticamente a todos os conjuntos de relatórios na organização da Experience Cloud, que geralmente engloba todos os conjuntos de relatórios da sua empresa.

Há algumas maneiras de testar o processamento da Privacidade de dados antes de aplicá-la a todos os seus conjuntos de relatórios:

* Uma opção é configurar uma Organização da Experience Cloud separada que contenha somente conjuntos de relatórios de teste. Use essa organização da Experience Cloud para realizar testes de Privacidade de dados e sua organização normal da Experience Cloud para processamentos de Privacidade de dados.
* Outra opção é atribuir namespaces diferentes à IDs nos conjuntos de relatórios de teste, em comparação com aqueles em seus conjuntos de relatórios de produção.

   Por exemplo, você pode adicionar prefixos &quot;qa-&quot; a cada namespace nos conjuntos de relatórios de teste. Ao enviar solicitações de Privacidade de dados com apenas namespaces com o prefixo &quot;qa&quot;, essas solicitações só são executadas em relação aos conjuntos de relatórios de teste. Posteriormente, quando você enviava solicitações sem o prefixo &quot;qa&quot;, elas eram aplicadas aos conjuntos de relatórios de produção. **Essa é a abordagem recomendada, a menos que você use as namespaces visitorId, AAID, ECID ou customVisitorId, pois elas são codificadas e não é possível especificar nomes alternativos para elas nos conjuntos** de relatórios de teste.
