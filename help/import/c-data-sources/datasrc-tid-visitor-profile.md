---
description: 'null'
seo-description: 'null'
seo-title: ID de transação e perfis de visitante
solution: Analytics
title: ID de transação e perfis de visitante
topic: Desenvolvedor e implementação
uuid: 7 a 72779 c -7 f 67-4872-ad 5 e-edf 298 d 53 cac
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# ID de transação e perfis de visitante

Esta seção contém informações importantes sobre os dados no perfil de visitante que são usados ao carregar dados usando uma ID de transação.

## ID da transação {#section_B248FA93ECC84F6290D237EB83618070}

Quando uma ID da transação é registrada, um "instantâneo" do perfil de visitante atual é salvo e associado à ID da transação. Esse "instantâneo" contém todos os valores de variável definidos atualmente para o visitante, incluindo variáveis persistentes (como eVars e campanhas). Os valores nesse instantâneo recebem atribuição para os eventos de sucesso, eventos de compra e receita carregados posteriormente usando essa mesma ID de transação.

Após a criação do "instantâneo" do perfil de visitante, ele não é carregado quando o perfil de visitante atual é alterado (devido ao comportamento online), e sim somente com os dados que são carregados usando as fontes de dados da ID da transação. Se você definir o mesmo valor de ID de transação em várias páginas durante a mesma visita, o carregamento da fonte de dados que ocorre posteriormente é associado ao "instantâneo" criado na primeira vez em que a ID foi definida.

**Vários uploads**

Várias linhas de dados podem ser carregadas na mesma ID da transação na janela de expiração da ID da transação (veja abaixo).

**Expiração da variável**

A expiração da variável não é considerada para os fins de IDs de transação, visto que os dados do perfil de visitante associados têm por objetivo refletir o estado do visitante no momento da transação. Por exemplo, se a eVar1 é configurada para expirar após a visita, o valor no "instantâneo" do perfil de visitante recebe crédito mesmo que o valor tenha expirado ou sido substituído no perfil de visitante atual quando os dados da ID da transação são carregados.

**Produtos**

Como as informações do produto (em `s.products`) não estão presentes no “instantâneo” do perfil de visitante, você deve carregar todos os dados do produto associados no arquivo de fonte de dados juntamente com a ID da transação. Observe que é possível especificar somente um produto por linha, sendo necessário carregar várias linhas com a mesma ID de transação para incluir todos os produtos.

**Persistência de eVar carregada**

As eVars carregadas com fontes de dados da ID da transação são adicionadas ao "instantâneo" do perfil de visitante, não ao perfil de visitante ou cookie virtual atual. Isso significa que o comportamento online que ocorre após o upload não é creditado nas eVars carregadas, visto que esses valores não fazem parte do perfil de visitante atual.

**Janela de expiração da ID da transação**

O "instantâneo" do perfil de visitante associado à ID de transação pode ser excluído após 90 dias, embora a programação da exclusão real varie. Caso necessário, entre em contato com o Atendimento ao cliente da Adobe para estender o período de expiração. Se uma linha for carregada após a janela de expiração da ID da transação, os dados na linha serão registrados, mas nenhum dos dados no "instantâneo" do perfil de visitante será creditado se o perfil tiver sido excluído.

## Detalhamentos e segmentação com IDs de transação {#section_A4D39291200A42C496122FDB9EF6EF68}

As eVars carregadas com fontes de dados podem ser usadas para detalhar as eVars contidas no "instantâneo" do perfil de visitante. Como esses dados estão separados do perfil de visitante atual, não é possível detalhar por outras eVars que tenham sido definidas antes ou depois da definição da ID de transação, mas que não fazem parte do “instantâneo”.

Existem algumas maneiras de visualizar os dados associados ao visitante que talvez não estejam disponíveis em um detalhamento. Nos relatórios do data warehouse, é possível visualizar os dados da ID de transação com uma ID de visitante que corresponda a outras ocorrências do visitante. Embora essas linhas da ID de transação sejam excluídas na contagem de visitas/visitantes por dia, são usadas no cálculo da maioria das métricas e em segmentos.

Assim, é possível criar um segmento de visitantes que realizam algum evento offline que tenha sido carregado com fontes de dados da ID de transação. Tudo que o visitante fez antes e depois do evento da ID de transação será retornado.

Da mesma forma, a participação do visitante permite ver como as propriedades e eVars da ID de transação antecedem um evento online, ou como as propriedades e eVars online antecedem um evento da ID de transação.
