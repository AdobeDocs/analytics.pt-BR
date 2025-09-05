---
description: Combine dados com e sem carimbos de data e hora em um único conjunto de relatórios.
title: Carimbos opcionais de data e hora
feature: Admin Tools
uuid: 0fa63658-1cc2-4adc-8d51-a0662d0aa941
exl-id: 4d64225a-5eb8-4b7b-ba13-3cdc12dd6651
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 89%

---

# Carimbos opcionais de data e hora

Combine dados com e sem carimbos de data e hora em um único conjunto de relatórios.

Os Carimbos opcionais de data e hora permitem que você:

* Combine dados com e sem carimbos de data e hora em um mesmo conjunto de relatórios global.
* Envie dados com carimbo de data e hora de um aplicativo móvel para um conjunto de relatórios global.
* Atualize os aplicativos para usar o rastreamento offline sem precisar criar um novo conjunto de relatórios.

>[!WARNING]
>
>Se você estiver usando os Carimbos opcionais de data e hora, não defina [s.visitorID](/help/implement/vars/config-vars/visitorid.md) para os dados que já apresentarem carimbos de data e hora. Isso pode causar dados desorganizados e um impacto negativo aos cálculos temporais (como valores de tempo gasto), atribuição (persistência eVar), números e contagens de visitas e relatórios de definição de caminho.

>[!NOTE]
>
>Os dados de uma sessão com carimbo de data e hora são mantidos por até 92 dias. Isso significa que uma visita/sessão será &quot;mantida aberta&quot; por 92 dias, enquanto qualquer ocorrência adicional - que não seja 30 minutos após a ocorrência anterior (em tempo de ocorrência) - ainda pode ser incluída na mesma visita/sessão. Quaisquer ocorrências &quot;antigas&quot; recebidas fora de ordem produzirão resultados &quot;desconhecidos&quot;, já que vários fatores (segmentação, alocação, expiração, etc.) influenciam se essas ocorrências serão incluídas no relatório ou não.

## Novos conjuntos de relatórios {#section_095A7CFBD280494593B9BEC1592B73A6}

* Se criado a partir de um modelo, um novo conjunto de relatórios apresentará por padrão os Carimbos opcionais de data e hora.

  (É possível criar um novo conjunto de relatórios a partir de um modelo em **Admin > Conjuntos de relatórios > Criar novo > Conjunto de relatório**.)
* Se copiado a partir de um conjunto de relatórios já existente, o novo conjunto de relatórios herdará os ajustes de carimbo de data e hora do original, incluindo:

   * **Carimbos de data e hora não permitidos** (a configuração s.visitorID é suportada)
   * **Carimbos obrigatórios de data e hora** (a configuração s.visitorID não é suportada)
   * **Carimbos opcionais de data e hora** (a configuração s.visitorID é suportada, exceto em ocorrências com carimbos de data e hora)

## Alterar conjuntos de relatórios existentes para Carimbos opcionais de data e hora {#section_40BCD3B4639241DEA716F7640ED33E72}

1. Vá para **Admin > Conjuntos de relatórios > Editar configurações > Geral > Configurações de carimbo de data e hora**.
1. Selecione a caixa **Converter os conjuntos de relatórios selecionados em Carimbos opcionais de data e hora**.

   Isso alterará seu conjunto de relatórios para Carimbos opcionais de data e hora.

>[!NOTE]
>
>Se um conjunto de relatórios foi definido como **Carimbos opcionais de data e hora**, para alterá-lo para qualquer outra configuração, entre em contato com o Atendimento ao cliente da Adobe.
