---
title: Visitantes únicos
description: O número de indivíduos únicos (ou dispositivos).
translation-type: tm+mt
source-git-commit: 8cfd797e336e006bf4134a2c10a89ad1003c53dc
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 10%

---


# Visitantes únicos

A métrica &#39;visitantes únicos&#39; mostra o número de IDs de visitante para o valor da dimensão. É uma das métricas mais comuns usadas ao determinar o tráfego, pois fornece uma visão geral de alto nível da popularidade de um valor de dimensão. Por exemplo, um visitante pode chegar ao seu site todos os dias por um mês, mas ainda contam como um único visitante exclusivo.

Se você usar análises [](../cda/cda-home.md)entre dispositivos, essa métrica será renomeada para &quot;Dispositivos exclusivos&quot;.

## visitantes únicos diários, semanais, mensais, trimestrais e anuais

O Relatórios e Analytics fornece opções para visitantes únicos diários, semanais, mensais, trimestrais e anuais. Em vez de contar um único visitante exclusivo para todo o período de tempo, visitantes únicos contam com base na métrica selecionada. Por exemplo, você deseja observar visitantes únicos diários do site. Se um visitante chegar ao seu site de manhã e de noite, ele contará como um único visitante diário. Se um visitante vier ao seu site na segunda-feira e novamente na terça-feira, ele contará como dois visitantes únicos diários.

Analysis Workspace trata visitantes únicos com base na granularidade do relatório. Por exemplo, se você usar a dimensão [Dia](../dimensions/day.md) , verá visitantes únicos diários para cada valor de dimensão. No entanto, para o total do relatório, ele é desduplicado em visitantes exclusivos para o intervalo de datas da tabela de forma livre.

## Como essa métrica é calculada

Essa métrica conta o número de IDs de visitante exclusivas para um determinado valor de dimensão. Ele usa vários mecanismos avançados para identificar visitantes únicos, já que há várias maneiras de identificá-los. A tabela a seguir lista a forma como um visitante é identificado, juntamente com sua prioridade. Algumas ocorrências podem ter vários métodos de identificação de visitantes; nestes casos, é utilizado o método de prioridade mais elevada.

| Pedido usado | Parâmetro do query (método de coleta) | Apresentar quando |
| --- | --- | --- |
| 1 | `vid` | A [`visitorID`](/help/implement/vars/config-vars/visitorid.md) variável está definida. |
| 2 | `aid` | O Visitante tem um [`s_vi`](https://docs.adobe.com/content/help/pt-BR/core-services/interface/ec-cookies/cookies-analytics.html) cookie existente. Definido em implementações sem ou antes da implementação do serviço de ID do Visitante. |
| 3 | `mid` | O Visitante tem um [`s_ecid`](https://docs.adobe.com/content/help/pt-BR/core-services/interface/ec-cookies/cookies-analytics.html) cookie existente. Defina as implementações usando o serviço [](https://docs.adobe.com/content/help/pt-BR/id-service/using/home.html)Adobe Experience Cloud Identity. |
| 4 | `fid` | O Visitante tem um [`s_fid`](https://docs.adobe.com/content/help/pt-BR/core-services/interface/ec-cookies/cookies-analytics.html) cookie existente ou se `aid` e não `mid` pôde ser definido por nenhum motivo. |
| 5 | Endereço IP, Agente do usuário, Endereço IP de gateway | Último recurso para identificar um visitante exclusivo se o navegador do visitante não aceitar cookies. |

>[!NOTE] Cada ID de visitante da Analytics está vinculada a um perfil nos servidores da Adobe. Esses perfis de visitante são excluídos após pelo menos 13 meses de inatividade, independentemente de qualquer expiração de cookie de ID de visitante.

## Comportamento que afeta a contagem exclusiva de visitantes

Identificadores de visitante exclusivos normalmente são armazenados em um cookie de navegador. Um novo visitante exclusivo é contado se executar qualquer um dos seguintes procedimentos:

* Limpa o cache a qualquer momento
* Abre um navegador diferente no mesmo computador. Um visitante único é contado por navegador.
* A mesma pessoa que navega no seu site em diferentes dispositivos. Um visitante exclusivo separado é contado por dispositivo. Você pode usar a análise [](../cda/cda-home.md) entre dispositivos para combinar visitantes usando a métrica [Pessoas](people.md) .
* Abre uma sessão de navegação privada (como a guia Incognito do Chrome).

Um novo visitante exclusivo *não* é contado, desde que o identificador do cookie seja preservado:

* Fecha o navegador por um período de tempo estendido
* Atualiza o navegador para a versão mais recente
