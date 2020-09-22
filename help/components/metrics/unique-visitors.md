---
title: Visitantes únicos
description: O número de indivíduos únicos (ou dispositivos).
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '563'
ht-degree: 100%

---


# Visitantes únicos

A métrica “Visitantes únicos” mostra o número de IDs de visitante para o item de dimensão. É uma das métricas mais comuns usadas ao determinar o tráfego, pois fornece uma visão geral de alto nível da popularidade de um item de dimensão. Por exemplo, um visitante pode chegar ao seu site todos os dias por um mês, mas ainda assim contam como um único visitante exclusivo.

Se você usar a [Análise entre dispositivos](../cda/overview.md), essa métrica será renomeada para &quot;Dispositivos exclusivos&quot;.

## Visitantes únicos diários, semanais, mensais, trimestrais e anuais

O Reports &amp; Analytics fornece opções para visitantes únicos diários, semanais, mensais, trimestrais e anuais. Em vez de contar um único visitante exclusivo para todo o período de tempo, visitantes únicos são contados com base na métrica selecionada. Por exemplo, você quer observar visitantes únicos diários do site. Se um visitante chegar ao seu site de manhã e de noite, ele será contado como um único visitante diário. Se um visitante vier ao seu site na segunda-feira e novamente na terça-feira, ele será contado como dois visitantes únicos diários.

O Analysis Workspace trata visitantes únicos com base na granularidade do relatório. Por exemplo, se você usar a dimensão [Dia](../dimensions/day.md), verá visitantes únicos diários para cada item de dimensão. No entanto, para o total do relatório, ele é desduplicado em visitantes exclusivos para o intervalo de datas da tabela de forma livre.

## Como essa métrica é calculada

Essa métrica conta o número de IDs de visitante exclusivas para um determinado item de dimensão. Ela usa vários mecanismos avançados para identificar visitantes únicos, já que há várias maneiras de identificá-los. A tabela a seguir lista a forma como um visitante é identificado, juntamente com sua prioridade. Algumas ocorrências podem ter vários métodos de identificação de visitantes; nestes casos, é utilizado o método de prioridade mais alta.

| Pedido usado | Parâmetro do query (método de coleta) | Apresentar quando |
| --- | --- | --- |
| 1 | `vid` | A variável [`visitorID`](/help/implement/vars/config-vars/visitorid.md) está definida. |
| 2 | `aid` | O Visitante tem um cookie [`s_vi`](https://docs.adobe.com/content/help/pt-BR/core-services/interface/ec-cookies/cookies-analytics.html) existente. Definido em implementações sem ou antes da implementação do serviço de ID do visitante. |
| 3 | `mid` | O Visitante tem um cookie [`s_ecid`](https://docs.adobe.com/content/help/pt-BR/core-services/interface/ec-cookies/cookies-analytics.html) existente. Defina as implementações usando o serviço [Adobe Experience Cloud Identity](https://docs.adobe.com/content/help/pt-BR/id-service/using/home.html). |
| 4 | `fid` | O Visitante tem um cookie [`s_fid`](https://docs.adobe.com/content/help/pt-BR/core-services/interface/ec-cookies/cookies-analytics.html) existente, ou se `aid` e `mid` não puderem ser definidos por algum motivo. |
| 5 | Endereço IP, Agente do usuário, Endereço IP de gateway | Último recurso para identificar um visitante exclusivo se o navegador do visitante não aceitar cookies. |

>[!NOTE]
>
>Cada ID de visitante do Analytics está vinculada a um perfil nos servidores da Adobe. Os perfis do visitante são excluídos depois de pelo menos 13 meses de inatividade, independentemente de qualquer expiração de cookie da ID do visitante.

## Comportamento que afeta a contagem exclusiva de visitantes

Identificadores de visitante exclusivos normalmente são armazenados em um cookie de navegador. Um novo visitante exclusivo é contado se executar qualquer um dos seguintes procedimentos:

* Limpa o cache a qualquer momento
* Abre um navegador diferente no mesmo computador. Um visitante único é contado por navegador.
* A mesma pessoa que navega no seu site em diferentes dispositivos. Um visitante exclusivo separado é contado por dispositivo. Você pode usar a [Análise entre dispositivos](../cda/overview.md) para combinar visitantes usando a métrica [Pessoas](people.md).
* Abre uma sessão de navegação privada (como a guia Incógnito do Chrome).

Um novo visitante exclusivo *não* é contado, desde que o identificador do cookie seja preservado:

* Fecha o navegador por um período estendido
* Atualiza o navegador para a versão mais recente
