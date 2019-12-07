---
description: Combine dados com e sem carimbos de data e hora em um único conjunto de relatórios.
title: Carimbos opcionais de data e hora
topic: Admin tools
uuid: 0fa63658-1cc2-4adc-8d51-a0662d0aa941
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Carimbos opcionais de data e hora

Combine dados com e sem carimbos de data e hora em um único conjunto de relatórios.

Os Carimbos opcionais de data e hora permitem que você:

* Combine dados com e sem carimbos de data e hora em um mesmo conjunto de relatórios global.
* Envie dados com carimbo de data e hora de um aplicativo móvel para um conjunto de relatórios global.
* Atualize os aplicativos para usar o rastreamento offline sem precisar criar um novo conjunto de relatórios.

Consulte [Utilização de Carimbos opcionais de data e hora](/help/implement/js-implementation/timestamps-overview.md) para mais informações sobre as práticas recomendadas para o uso de carimbos de data e hora em seu conjunto de relatórios.

>[!IMPORTANT]
>
>Se estiver usando os Carimbos opcionais de data e hora, não defina [s.visitorID](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_custom.html) para dados que já apresentarem carimbos de data e hora. Isso pode causar dados desorganizados e um impacto negativo aos cálculos temporais (como valores de tempo gasto), atribuição (persistência eVar), números e contagens de visitas e relatórios de definição de caminho.

> [!NOTE] Os dados de uma sessão com carimbo de data e hora são mantidos por até 92 dias. Isso significa que uma visita/sessão será "mantida aberta" por 92 dias, enquanto qualquer ocorrência adicional - que não seja 30 minutos após a ocorrência anterior (em tempo de ocorrência) - ainda pode ser incluída na mesma visita/sessão. Quaisquer ocorrências "antigas" recebidas fora de ordem produzirão resultados "desconhecidos", uma vez que vários fatores (segmentação, alocação, expiração etc.) influenciam se essas ocorrências serão incluídas no relatório ou não.

## Novos conjuntos de relatórios {#section_095A7CFBD280494593B9BEC1592B73A6}

* Se criado a partir de um modelo, um novo conjunto de relatórios apresentará por padrão os Carimbos opcionais de data e hora.

   (É possível criar um novo conjunto de relatórios a partir de um modelo em **Admin &gt; Conjuntos de relatórios &gt; Criar novo &gt; Conjunto de relatório**.)
* Se copiado a partir de um conjunto de relatórios já existente, o novo conjunto de relatórios herdará os ajustes de carimbo de data e hora do original, incluindo:

   * **Carimbos de data e hora não permitidos** (a configuração s.visitorID é suportada)
   * **Carimbos obrigatórios de data e hora** (a configuração s.visitorID não é suportada)
   * **Carimbos opcionais de data e hora** (a configuração s.visitorID é suportada, exceto em ocorrências com carimbos de data e hora)

## Alterar conjuntos de relatórios existentes para Carimbos opcionais de data e hora  {#section_40BCD3B4639241DEA716F7640ED33E72}

1. Vá para **Admin &gt; Conjuntos de relatórios &gt; Editar configurações &gt; Geral &gt; Configurações de carimbo de data e hora**.
1. Selecione a caixa **Converter os conjuntos de relatórios selecionados em Carimbos opcionais de data e hora**

   Isso alterará seu conjunto de relatórios para Carimbos opcionais de data e hora.

> [!NOTE] Se um conjunto de relatórios foi definido como **Carimbos opcionais de data e hora**, para alterá-lo para qualquer outra configuração, entre em contato com o Atendimento ao cliente da Adobe.

