---
description: As variáveis de página populam diretamente um relatório, como pageName, Propriedades de lista, Variáveis de lista, entre outros.
keywords: Analytics Implementation
subtopic: Variables
title: Variáveis de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# timestamp

Esta variável permite personalizar a marca de data e hora de uma ocorrência semelhante às bibliotecas AppMeasurement para outras plataformas.


<!-- 

timestamp.xml

 -->

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 4 bytes | Data/Hora | Não informado diretamente. | Definido por servidores de coleta de dados. |

**Sintaxe** {#section_1DF752B1202C4412A301AC7CC10874DF}

```js
s.timestamp="UNIX or ISO-8601 format timestamp"
```

A variável *`timestamp`* deve estar no formato explicado na próxima seção.

>[!IMPORTANT]
>
>O Atendimento ao cliente deve ativar o carimbo de data e hora do conjunto de relatórios, antes que você possa usar a variável *`timestamp`*. Após ativar o suporte ao carimbo de data e hora, todos os hits enviados para esse conjunto de relatórios do JavaScript devem ter um carimbo de data e hora definido manualmente (usando *`s.timestamp`*) ou os hits não serão registrados.
>
>Além disso, se você ativar o suporte ao carimbo de data e hora em um conjunto de relatório para suporte ao rastreamento offline, todas as ocorrências enviadas para este conjunto de relatórios do JavaScript também devem ter um carimbo de data e hora definido manualmente (usando *`s.timestamp`*). Não é possível enviar ocorrências com e sem carimbo de data e hora para o mesmo conjunto de relatórios.
>
>Também é possível usar a configuração [Carimbos opcionais de data e hora](/help/implement/js-implementation/timestamps-overview.md) para combinar dados com e sem carimbos de data e hora no mesmo conjunto de relatórios global, enviar dados com carimbos de data e hora de um aplicativo para dispositivos móveis para um conjunto de relatórios global ou atualizar aplicativos para usar carimbos de data e hora sem precisar criar um novo conjunto de relatórios.

**Formatos de marcas de data e hora** {#section_C12CBCECCD7047D38EF63A5800761CE9}

As marcas de data e hora devem estar em formato UNIX (segundos desde 1 de janeiro de 1970) ou ISO-8601, com as seguintes restrições sobre o formato ISO-8601 aceito:

* A data e a hora devem ser fornecidas, separadas por "T"
* A data deve ser uma data de calendário com total precisão (dia, mês e ano). . Não há suporte para datas semanais e datas ordinais.
* A data pode estar em formato padrão ou estendido (`YYYY-MM-DD` ou `YYYYMMDD`), mas deve sempre incluir a hora e o minuto. Os segundos são opcionais (`HH:MM`, `HH:MM:SS`, `HHMM` ou `HHMMSS`). Os minutos e os segundos fracionais podem ser mencionados, mas a parte fracional será omitida.

* Pode-se especificar um fuso horário opcional no formato padrão ou estendido (`±HH`, `±HH:MM`, `±HH`, `±HHMM` ou Z)

As marcas de data e hora UNIX continuam sendo suportados (segundos desde 1° de janeiro de 1970).

**Exemplos** {#section_FA19C53D70DE4CF2AF259A5B968B84C3}

```js
s.timestamp=Math.round((new Date()).getTime()/1000);
```

```js
s.timestamp="2012-04-20T12:49:31-0700";
```

A lista a seguir contém exemplos de marcas de data e hora válidas no formato ISO-8601:

```
2013-01-01T12:30:05+06:00 
2013-01-01T12:30:05Z 
2013-01-01T12:30:05 
2013-01-01T12:30
```

**Configurações** {#section_5275D206F2CB4009B3681E8C4457124A}

É necessário ativar um conjunto de relatórios para aceitar carimbos de data e hora personalizados pelo Atendimento ao cliente antes de usar essa variável. Depois que as marcas de data e hora personalizadas são ativadas, todas as ocorrências enviadas para o conjunto de relatórios devem conter uma marca de data e hora ou são descartadas.

**Armadilhas, dúvidas e dicas** {#section_EFDE8F67D13C4775A461E0B00D30AFD7}

* As marcas de data e hora são usadas principalmente para rastrear os dados offline em plataformas móveis. As marcas de data e hora personalizadas geralmente ficam desativadas, a menos que você colete dados da Web e do aplicativo offline no mesmo conjunto de relatórios.
* Os dados têm carimbo de data e hora quando os dados offline são ativados no SDK móvel (configuração padrão) ou sempre que um conjunto de relatórios é configurado para aceitar dados com carimbo de data e hora. Os dados coletados offline podem ser enviados horas ou semanas após a data em que o evento ocorreu originalmente. Essas ocorrências podem ser consultadas na plataforma do Analytics para minutos ou horas superiores às ocorrências, sem carimbos de data e hora:

   * Para dados com carimbos de data e hora enviados muito próximos à hora atual, o atraso provável é de 10 a 15 minutos.
   * Para dados com carimbo de data e hora enviados ontem, o atraso provável é de aproximadamente 2 horas.
   * Para dados com carimbos de data e hora enviados mais antigos que ontem, cada dia adiciona cerca de 2 horas de atraso, até um máximo de 48 horas.

