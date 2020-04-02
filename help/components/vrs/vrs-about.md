---
description: Os conjuntos de relatórios virtuais segmentam seus dados do Adobe Analytics para que você possa controlar o acesso a cada segmento.
title: Visão geral dos conjuntos de relatórios virtuais
uuid: 51c63c56-dd58-4c23-a997-ea6942480d22
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Visão geral dos conjuntos de relatórios virtuais

Os conjuntos de relatórios virtuais segmentam seus dados do Adobe Analytics para que você possa controlar o acesso a cada segmento.

Muitos clientes têm dados que fluem para um conjunto de relatórios global, mas também dados que fluem para conjuntos de relatórios menores. Eles definem uma variável para vários conjuntos de relatórios e enviam seus dados para mais de um conjunto de relatórios. Isso é referenciado como *tags de vários conjuntos* ou *conjuntos de relatórios de base/pais*.

Por exemplo, todos os dados podem ser coletados em um único conjunto de relatórios; porém, você pode configurar conjuntos de relatórios secundários para que as pessoas da empresa tenham acesso a parte dos dados, mas não a todos eles. Os dados podem ser divididos por região. Você pode ter sites diferentes para diferentes países. Outros exemplos podem ser marcas específicas que pertencem a uma empresa maior, mas que possuem suas próprias equipes de marketing.

Um *conjunto de relatórios virtual* (VRS) permite reproduzir esse conceito de ramificação usando segmentos em vez de vários conjuntos de relatórios. Os dados são enviados para um conjunto de relatórios, depois são divididos de acordo com os segmentos. Usando o exemplo de várias marcas, você pode definir uma prop para a marca à qual um item pertence. Usando os segmentos, você pode relatar os itens atribuídos a cada propriedade. Cada um desses segmentos se torna sua própria visão, criando efetivamente um novo conjunto de relatórios. Você não envia dados especificamente para esse segmento, apenas para o conjunto de relatórios global, mas ele funciona nos relatórios como se fosse um conjunto de relatórios diferente.

Um conjunto de relatórios virtual herda a maioria dos níveis de serviço do conjunto de relatórios base, como configurações de eVar, Regras de processamento, Classificações, etc. As seguintes configurações NÃO foram herdadas:

* ID do conjunto de relatórios (RSID)
* Nome do conjunto de relatórios
* Grupos de permissões (os conjuntos de relatórios virtuais podem ser atribuídos aos seus próprios grupos de permissões)

## Benefícios dos Conjuntos de relatórios virtuais  {#section_3420422FE6DF46EAB151FD9442AAFDC4}

Os clientes pagam pelas chamadas secundárias do servidor, de modo que eliminar essas chamadas pode resultar em economias significativas. Um conjunto de relatórios virtual também é completamente retroativo. Se o conjunto de relatórios global já contiver dados, os dados relevantes serão incluídos automaticamente em um novo conjunto de relatórios virtual. Um novo conjunto de relatórios secundário só começa a coletar dados depois de ser criado e, deste modo, não inclui nenhum dado histórico. Quando você implementa o Analytics, basta enviar os dados para um conjunto de relatórios; não é necessário criar implementações para o conjunto de relatórios global e cada conjunto de relatório secundário.

Os conjuntos de relatórios virtuais ajudam a:

* Simplificar a implementação ao permitir o uso de uma única ID de conjunto de relatórios (RSID) em todos os sites/domínios. A presença de todos os dados em um único conjunto de relatórios permite a análise do cliente na nova geração do Adobe Analytics.
* Os usuários comerciais da organização a sempre observar apenas os segmentos de dados relevantes para eles.
* Melhorar a segurança ao permitir que usuários administradores controlem o acesso aos dados de modo mais fácil e granular após a implementação.
* Fornecer a capacidade de participar da Device Co-op
* Métrica de pessoas
* Uma visão de um único cliente dos dados (no futuro)
* A capacidade de criar conjuntos de relatórios virtuais ilimitados para segmentar dados

## Limitações dos conjuntos de relatórios virtuais  {#section_F22A6DEBDC9848429E446F4CC2C4EEDE}

Os conjuntos de relatórios virtuais têm as seguintes limitações:

* Quaisquer limitações de segmentos aplicam-se aos conjuntos de relatórios virtuais

   Um conjunto de relatórios virtual nada mais é do que um segmento aplicado a um conjunto de relatórios. Como cada conjunto de relatórios possui seu próprio data warehouse e seu próprio feed de dados, o uso de vários conjuntos de relatórios resulta em alguns benefícios que os segmentos não fornecem.
* Relatório em tempo real
* Configurações e nomes de variáveis não podem ser personalizados como em um conjunto de relatórios completo

## Conjuntos de relatórios virtuais versus tags de vários conjuntos {#section_317E4D21CCD74BC38166D2F57D214F78}

| Recurso | Conjunto de relatórios virtuais | Tags de vários conjuntos |
|--- |--- |--- |
| Oferece relatório de “Dados atuais” ou em tempo real | Não | Sim |
| Funciona em todas as ferramentas do Analytics (Analysis Workspace, Report Builder, Ad Hoc Analysis etc.) | Sim.   Observação: você pode editá-los e identificá-los como conjuntos de relatórios virtuais somente no Reports &amp; Analytics. Entretanto, é possível selecioná-los nos menus suspensos do conjunto de relatórios nas outras ferramentas. | Sim |
| É possível enviar dados para ele (por meio de classificações, feeds de dados etc.) | Não | Sim |
| Suporta a criação de relatórios DL, marcações, painéis, alvos, alertas, segmentos, métricas calculadas... | Sim | Sim |
| Pode ser adicionado individualmente aos Grupos de permissões | Sim | Sim |
| Pode usar funções de Administrador para modificar configurações individuais neste conjunto de relatórios (Administrador > Conjuntos de relatórios) | Não (configurações herdadas do pai) | Sim |

## Combine conjuntos de relatórios virtuais e tags de vários conjuntos {#section_026FA3FCD7314DD18220E73EC5702AFF}

Em alguns casos, existem benefícios para o uso de conjuntos de relatórios virtuais e tags de vários conjuntos.

Por exemplo, um varejista pode usar um conjunto de relatórios para cada marca, e conjuntos de relatórios virtuais para cada marca para segmentar dados por região. Da mesma forma, uma organização atlética pode usar um conjunto de relatórios para cada equipe e, em seguida, usar conjuntos de relatórios virtuais para dividir os fãs na região da equipe daqueles que estão fora da região.
