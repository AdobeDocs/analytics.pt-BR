---
description: 'null'
seo-description: 'null'
seo-title: Enviar solicitações de acesso e de exclusão
title: Enviar solicitações de acesso e de exclusão
uuid: d 006 cd 5 c-e 3 cd -4385-8683-acaf 73 cb 681 b
translation-type: tm+mt
source-git-commit: 9bc170ed53f4ebbe212878f884cd77350bd1d620

---


# Enviar solicitações de acesso e de exclusão


## Visão geral {#section_BD70882995894C1CA19C205C49FEC23C}

Se seus clientes (consumidores/titulares de dados) quiserem saber quais dados você mantém sobre eles ou decidirem que desejam ser excluídos de suas propriedades do Analytics, você, como o controlador dos dados, é responsável por responder a essas solicitações. O controlador de dados determina como sua organização interage com titulares de dados (por exemplo, por meio de um portal de usuário do titular dos dados) e gerencia as interações com eles. Também é responsabilidade do controlador fechar o ciclo com o titular dos dados quando a solicitação for atendida. Em outras palavras, a Adobe Experience Cloud, como processador de dados, não aceitará solicitações diretamente dos titulares dos dados nem retornará dados diretamente para eles. Em vez disso, a Adobe receberá solicitações e retornará dados somente para você, o controlador dos dados.

Você também pode querer garantir que seus aplicativos e sites para dispositivos móveis tenham avisos pop-up relevantes e materiais de apoio sobre os direitos dos titulares de dados em relação a seus dados direta ou indiretamente identificáveis, além de outros dados que você coletar.

## Gerenciar o consentimento do consumidor {#section_3012015E7E8942519FB9279CF7057EAB}

Você, como o controlador de dados, é responsável por obter consentimento explícito de seus titulares de dados antes de coletar dados sobre eles (possivelmente incluindo dados do Adobe Analytics) e por [implementar um mecanismo de recusa](https://marketing.adobe.com/resources/help/en_US/dtm/opt-in.html) no seu site. Isso permite que seus titulares de dados optem por cancelar a coleta de dados futura da Adobe Experience Cloud.

## Validar usuários e seus dados {#section_AFB2CC225AA94AF6A3CE9F24EF788358}

Você, como controlador de dados, é responsável por verificar se o titular dos dados é quem diz ser e se tem direito aos dados que está solicitando. Além disso, é sua responsabilidade garantir que os dados corretos sejam devolvidos ao titular dos dados e que ele não receba, inadvertidamente, dados sobre outros titulares de dados.

Isso inclui revisar os dados retornados pelo Adobe Analytics como parte de uma solicitação de acesso do GDPR antes de enviá-los ao titular dos dados. Cuidado especial deve ser tomado se estiver usando IDs de pessoa e retornando não somente os dados nos quais essa ID está presente, como também os dados de outras ocorrências em um dispositivo compartilhado no qual essa ID estava ocasionalmente presente ([Expansão de ID](../../admin/c-data-governance/gdpr-analytics-ids.md#section_D55C0722BC834118BE6F958C30AD5913)).

Cada arquivo combina dados de todos os seus conjuntos de relatórios, removendo automaticamente cópias adicionais de ocorrências replicadas. Você pode decidir quais desses arquivos retornar ao titular dos dados. Ou você pode extrair alguns desses dados e combiná-los com dados de outros sistemas antes de retorná-los ao titular dos dados.

## Enviar solicitações {#section_F70F4D91B7FF4242876338A66D2125C3}

Você pode enviar as solicitações de acesso e exclusão do GDPR por meio de nosso [portal de interface do usuário do GDPR](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/using-gdpr-ui.md) ou de nossa [API do GDPR](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md).

>[!NOTE]
>
>A API GI suporta envios em lote para vários usuários em uma única solicitação. O limite suportado atualmente é de 1.000 usuários separados (podem ter várias IDs por usuário) em um único arquivo JSON de solicitação.

## Solicitação JSON de exemplo {#section_DB9DE6492FE740918F91D413E7BAB88F}

Este é o JSON que pode ser enviado por meio da API do GDPR ou da interface do usuário, solicitando o processamento do GDPR para três usuários.

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
            "key": "GDPR-1234", 
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
            "key": "GDPR-1235", 
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
            "key": "GDPR-1236", 
            "action": ["access","delete"], 
            "userIDs": [ 
                { 
                    "namespace": "CRM-ID", 
                    "type": "analytics", 
                    "description": "namespace defined on eVar17 in some report suites", 
                    "value": "ACME-12345678", 
                }, 
                { 
                    "namespace": "email address", 
                    "type": "analytics", 
                    "description": "namespace defined on eVar23 in some report suites", 
                    "value": "john@mail.com", 
                } 
            ] 
        } 
    ], 
    "expandIds": true 
} 
```

Observe que há três blocos na seção do usuário, representando três solicitações separadas, provavelmente, para três titulares de dados separados.

* A primeira solicitação é de acesso, usando uma ID de cookie tradicional do Adobe Analytics (AAID).
* A segunda solicitação também é de acesso, mas usa um cookie MCID/ECID.
* A terceira solicitação é de acesso e exclusão para as IDs especificadas. Embora a Expansão de ID seja especificada para todas as solicitações, isso terá o maior impacto nesta terceira solicitação, pois é a única que usa IDs que não são de cookies. Como resultado, essa solicitação também descobrirá as IDs de cookies associadas a qualquer dispositivo com essa ID do CRM especificada ou endereço de email e também expandirá a solicitação para inclui-las.

Lembre-se

* O valor “5D7236525AA6D9580A495C6C@AdobeOrg” na seção “companyContexts” deve ser atualizado com o valor da própria organização da Experience Cloud.
* Os campos “type” e “namespace” são descritos em mais detalhes na seção [Namespaces](../../admin/c-data-governance/gdpr-namespaces.md#concept_26C6392D92194BC1BA3986A144AF285D).
* Os campos “description” são ignorados.
* Os campos “key” podem conter qualquer valor desejado. Se tiver uma ID interna que esteja usando para rastrear as solicitações do GDPR, insira esse valor para facilitar a correspondência das solicitações do sistema da Adobe com as de seus próprios sistemas.

## Detalhes de resposta {#section_93F554F65DBB48A18B75EB5784056C96}

Esta seção apresenta detalhes sobre respostas de acesso e de exclusão.

**Detalhes de resposta do acesso**

Os dados retornados em uma solicitação de acesso fornecem a você, o controlador de dados, um URL que pode ser usado para baixar um arquivo ZIP que contenha um diretório para cada produto da Adobe que possui. Na pasta do Analytics, pode haver:

* Arquivos de pessoa - Derivados de ocorrências que contêm um rótulo ID-PERSON correspondente

   * Um arquivo CSV com uma linha para cada ocorrência correspondente e uma coluna para cada campo com um rótulo de ACC-ALL ou ACC-PERSON, classificado por carimbo de data e hora.
   * Um arquivo HTML de resumo com uma entrada para cada rótulo de ACC-ALL ou ACC-PERSON. Cada entrada lista todos os valores exclusivos para esse campo e o número de vezes que cada um ocorreu. Os campos que contêm os carimbos de data e hora são arredondados para especificar apenas dias exclusivos.

* Arquivos de dispositivo - derivados de ocorrências em que um dos campos correspondeu a uma ID especificada, mas nenhum correspondeu a uma ID especificada

   * Um arquivo CSV com uma linha para cada ocorrência correspondente e uma coluna para cada campo com um rótulo de ACC-ALL, classificado por carimbo de data e hora.
   * Arquivo HTML de resumo com uma entrada para cada rótulo de ACC-ALL. Cada entrada listará todos os valores exclusivos para esse campo e o número de vezes que cada um ocorreu. Os campos que contêm os carimbos de data e hora são arredondados para especificar apenas dias exclusivos.

Cada arquivo combina dados de todos os seus conjuntos de relatórios, removendo automaticamente cópias adicionais de ocorrências replicadas.

Você pode decidir qual deles retornar ao titular dos dados. Ou você pode extrair alguns desses dados e combiná-los com dados de outros sistemas antes de retorná-los ao titular dos dados.

**Detalhes de resposta da exclusão**

Nenhum dado é retornado nas solicitações de exclusão; apenas um status para a API do GDPR de que a solicitação foi concluída com êxito.

## Teste do processamento de GDPR em seus dados {#section_FBA843DBFAE64D979D8DB8A3C56784D7}

Normalmente, os clientes do Analytics configurarão alguns conjuntos de relatórios de teste para verificar a funcionalidade antes que ela seja disponibulizada para o público em geral. Sites da web ou aplicativos em pré-produção enviarão dados para esses conjuntos de relatórios de teste/desenvolvimento/QA para avaliar como as coisas funcionarão quando o código for lançado antes que o tráfego real seja enviado para os conjuntos de relatórios de produção.

No entanto, com uma configuração normal, o processamento de solicitação de GDPR não pode ser testado primeiro nesses conjuntos de relatórios de teste, antes de aplicar solicitações a conjuntos de relatórios de produção. O motivo é que uma solicitação de GDPR é aplicada automaticamente a todos os conjuntos de relatórios na Organização da Experience Cloud, que geralmente engloba todos os conjuntos de relatórios da sua empresa.

Há algumas maneiras de testar o processamento do GDPR antes de aplicá-lo a todos os seus conjuntos de relatórios:

* Uma opção é configurar uma Organização da Experience Cloud separada que contenha somente conjuntos de relatórios de teste. Use essa organização da Experience Cloud para realizar testes de GDPR e sua organização normal da Experience Cloud para processamentos de GDPR.
* Outra opção é atribuir namespaces diferentes à IDs nos conjuntos de relatórios de teste, em comparação com aqueles em seus conjuntos de relatórios de produção.

   Por exemplo, você pode adicionar prefixos "qa-" a cada namespace nos conjuntos de relatórios de teste. Quando você enviar solicitações do GDPR com apenas namespaces com o prefixo "qa", essas solicitações só são executadas em relação aos conjuntos de relatórios de teste. Posteriormente, quando você enviava solicitações sem o prefixo "qa", elas eram aplicadas aos conjuntos de relatórios de produção. **Essa é a abordagem recomendada, a menos que você use os namespaces visitorId, AAID, ECID ou customVisitorId, pois esses são codificados e não podem especificar nomes alternativos para eles em seus conjuntosde relatórios de teste**.
