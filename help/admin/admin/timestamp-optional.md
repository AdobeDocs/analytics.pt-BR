---
description: Combine dados com e sem carimbos de data e hora em um único conjunto de relatórios.
seo-description: Combine dados com e sem carimbos de data e hora em um único conjunto de relatórios.
seo-title: Carimbos opcionais de data e hora
solution: Analytics
title: Carimbos opcionais de data e hora
topic: Ferramentas administrativas
uuid: 0 fa 63658-1 cc 2-4 adc -8 d 51-a 0662 d 0 aa 941
translation-type: tm+mt
source-git-commit: 2b7644a7af34fff95d7557382abf3d370bd2637c

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
>If you are using Timestamps Optional, then do not set [s.visitorID](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_custom) on data that is already timestamped. Isso pode causar dados desorganizados e um impacto negativo aos cálculos temporais (como valores de tempo gasto), atribuição (persistência eVar), números e contagens de visitas e relatórios de definição de caminho.

>[!NOTE]
>
>Os dados de uma sessão com carimbo de data e hora são mantidos por até 92 dias. Isso significa que uma visita/sessão será «aberta» por 92 dias enquanto qualquer ocorrência adicional - que não é 30 minutos após a ocorrência anterior (na hora da ocorrência) - ainda poderá ser incluída na mesma visita/sessão. Quaisquer ocorrências "antigas" recebidas fora do pedido produzirão resultados "desconhecidos", já que vários fatores (segmentação, alocação, expiração etc.) influência se essas ocorrências serão incluídas nos relatórios ou não.

## Novos conjuntos de relatórios {#section_095A7CFBD280494593B9BEC1592B73A6}

* Se criado a partir de um modelo, um novo conjunto de relatórios apresentará por padrão os Carimbos opcionais de data e hora.

   (É possível criar um novo conjunto de relatórios a partir de um modelo em **Admin &gt; Conjuntos de relatórios &gt; Criar novo &gt; Conjunto de relatório**.)
* Se copiado a partir de um conjunto de relatórios já existente, o novo conjunto de relatórios herdará os ajustes de carimbo de data e hora do original, incluindo:

   * **Carimbos de data e hora não permitidos** (a configuração s.visitorID é suportada)
   * **Carimbos obrigatórios de data e hora** (a configuração s.visitorID não é suportada)
   * **Carimbos opcionais de data e hora** (a configuração s.visitorID é suportada, exceto em ocorrências com carimbos de data e hora)

## Alterar conjuntos de relatórios existentes para Carimbos opcionais de data e hora {#section_40BCD3B4639241DEA716F7640ED33E72}

1. Vá para **Admin &gt; Conjuntos de relatórios &gt; Editar configurações &gt; Geral &gt; Configurações de carimbo de data e hora**.
1. Selecione a caixa **Converter os conjuntos de relatórios selecionados em Carimbos opcionais de data e hora**

   Isso alterará seu conjunto de relatórios para Carimbos opcionais de data e hora.

>[!NOTE]
>
>If a report suite was set to **Timestamps Optional**, to change this to any other setting, please contact Adobe Client Care.

