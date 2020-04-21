---
description: As Sessões sensíveis ao contexto em conjuntos de relatórios virtuais mudam a forma como o Adobe Analytics calcula as visitas de dispositivos móveis. Este artigo descreve as implicações do processamento de ocorrências em segundo plano e dos eventos de inicialização de aplicativos (ambos definidos pelo SDK móvel) na forma como as visitas móveis são definidas.
title: Sessões sensíveis ao contexto
uuid: d354864a-9163-4970-a3a0-f2e9729bdbe3
translation-type: tm+mt
source-git-commit: 3997889ae72920d719203edbb159b55b983158e7

---


# Sessões sensíveis ao contexto

As sessões sensíveis ao contexto em conjuntos de relatórios virtuais mudam a forma como o Adobe Analytics calcula as visitas de qualquer dispositivo. Este artigo também descreve as implicações de processamento das ocorrências em segundo plano e dos eventos de inicialização do aplicativo (ambos definidos pelo SDK móvel) em como as visitas móveis são definidas.

Você pode definir uma visita da maneira que desejar sem alterar os dados subjacentes, para corresponder à forma como seus visitantes interagem com suas experiências digitais.

## Parâmetro do URL de perspectiva do cliente 

O processo de coleta de dados do Adobe Analytics permite que você defina um parâmetro de string de query que especifica a perspectiva do cliente (denotado como o parâmetro de string de query &quot;cp&quot;). Esse campo especifica o estado do aplicativo digital do usuário final. Isso ajuda você a saber se uma ocorrência foi gerada enquanto um aplicativo móvel estava em segundo plano.

## Processamento de ocorrências em segundo plano 

Uma ocorrência em segundo plano é um tipo de ocorrência enviada para o Analytics a partir do Adobe Mobile SDK versão 4.13.6 e superior quando o aplicativo faz uma solicitação de rastreamento em segundo plano. Exemplos típicos disso incluem:

* Dados enviados durante a travessia da cerca geográfica
* Uma interação de notificação por push

Os exemplos a seguir descrevem a lógica usada para determinar quando uma visita é start e termina para qualquer visitante quando a configuração &quot;Impedir ocorrências em segundo plano de iniciar uma nova visita&quot; está ou não ativada para um conjunto de relatórios virtual.

**Se “Impedir ocorrências em segundo plano de iniciar uma nova visita” não estiver ativado:**

Se esse recurso não estiver habilitado para um conjunto de relatórios virtual, as ocorrências em segundo plano serão tratadas como qualquer outra ocorrência, o que significa que elas start novas visitas e agem exatamente como ocorrências em primeiro plano. Por exemplo, se uma ocorrência em segundo plano ocorrer menos de 30 minutos (o tempo limite de sessão padrão para um conjunto de relatórios) antes de um conjunto de ocorrências em primeiro plano, a ocorrência em segundo plano fará parte da sessão.

![](assets/nogood1.jpg)

Se a ocorrência em segundo plano ocorrer mais de 30 minutos antes de qualquer ocorrência em primeiro plano, a ocorrência em segundo plano criará sua própria visita, para uma contagem total de visitas de 2.

![](assets/nogood2.jpg)

**Se “Impedir ocorrências em segundo plano de iniciar uma nova visita” estiver ativado:**

Os exemplos a seguir ilustram o comportamento das ocorrências em segundo plano quando esse recurso está habilitado.

Exemplo 1: uma ocorrência em segundo plano ocorre em algum período de tempo (t) antes de uma série de ocorrências em primeiro plano.

![](assets/nogoodexample1.jpg)

Neste exemplo, se *t* for maior que o tempo limite de visita configurado para o conjunto de relatórios virtual, a ocorrência em segundo plano será excluída da visita formada pelas ocorrências em primeiro plano. Por exemplo, se o tempo limite de visita do conjunto de relatórios virtual for definido como 15 minutos e *t* for 20 minutos, a visita formada por essa série de ocorrências (mostradas pelo contorno verde) excluirá a ocorrência em segundo plano. Isso significa que todas as eVars definidas com uma expiração de &quot;visita&quot; na ocorrência em segundo plano **não** persistem na visita a seguir, e um container de segmento de visita incluiria apenas as ocorrências em primeiro plano dentro do contorno verde.

![](assets/nogoodexample1-2.jpg)

Por outro lado, se *t* for menor que o tempo limite de visita configurado para o conjunto de relatórios virtual, a ocorrência em segundo plano será incluída como parte da visita como se fosse uma ocorrência em primeiro plano (mostrada pelo contorno verde):

![](assets/nogoodexample1-3.jpg)

Isso significa que:

* Quaisquer eVars definidas com expiração de &quot;visita&quot; na ocorrência em segundo plano persistem seus valores nas outras ocorrências nesta visita.
* Quaisquer valores definidos na ocorrência em segundo plano são incluídos na avaliação lógica do container de segmento no nível da visita.

Em ambos os casos, a contagem total de visitas seria 1.

Exemplo 2: se uma ocorrência em segundo plano ocorre após uma série de ocorrências em primeiro plano, o comportamento é semelhante:

![](assets/nogoodexample2.jpg)

Se a ocorrência em segundo plano ocorrer após o tempo limite configurado para o conjunto de relatórios virtual, a ocorrência em segundo plano não fará parte de uma sessão (contornada em verde):

![](assets/nogoodexample2-1.jpg)

Da mesma forma, se o período de tempo *t* for menor que o tempo limite configurado para o conjunto de relatórios virtual, a ocorrência em segundo plano será incluída na visita formada pelas ocorrências em primeiro plano anteriores:

![](assets/nogoodexample2-2.jpg)

Isso significa que:

* Quaisquer eVars definidas com expiração de &quot;visita&quot; nas ocorrências anteriores em primeiro plano persistem em seus valores na ocorrência em segundo plano nesta visita.
* Quaisquer valores definidos na ocorrência em segundo plano são incluídos na avaliação lógica do container de segmento no nível da visita.

Como antes, a contagem total de visitas em ambos os casos seria 1.

Exemplo 3: em algumas circunstâncias, uma ocorrência em segundo plano pode fazer com que duas visitas separadas sejam combinadas em uma única visita. No seguinte cenário, uma ocorrência em segundo plano é precedida e seguida por uma série de ocorrências em primeiro plano:

![](assets/nogoodexample3.jpg)

Se, neste exemplo, *t1* e *t2* forem menores que o tempo limite de visita configurado para o conjunto de relatórios virtual, todas essas ocorrências serão combinadas em uma única visita, mesmo se *t1* e *t2* estiverem juntas, forem maiores que o tempo limite de visita:

![](assets/nogoodexample3-1.jpg)

No entanto, se *t1* e *t2* forem maiores que o tempo limite configurado para o conjunto de relatórios virtual, essas ocorrências serão separadas em duas visitas distintas:

![](assets/nogoodexample3-2.jpg)

Da mesma forma (como em nossos exemplos anteriores), se *t1* for menor que o tempo limite e *t2* for menor que o tempo limite, a ocorrência em segundo plano será incluída na primeira visita:

![](assets/nogoodexample3-3.jpg)

Se *t1* for maior que o tempo limite e *t2* for menor que o tempo limite, a ocorrência em segundo plano será incluída na segunda visita:

![](assets/nogoodexample3-4.jpg)

Exemplo 4: em cenários em que uma série de ocorrências em segundo plano ocorrem dentro do tempo limite de uma visita do conjunto de relatórios virtual, as ocorrências formam uma “visita em segundo plano” invisível que não é contabilizada na contagem de visitas e não pode ser acessada usando um contêiner de segmentação de visitas.

![](assets/nogoodexample4.jpg)

Mesmo que isso não seja considerado uma visita, qualquer conjunto de eVars com expiração de visita manterá seus valores para a outra ocorrência em segundo plano nesta “visita em segundo plano”.

Exemplo 5: para cenários em que várias ocorrências em segundo plano ocorrem sucessivamente após uma série de ocorrências em primeiro plano, é possível (dependendo da configuração de tempo limite) que as ocorrências em segundo plano mantenham uma visita ativa por mais tempo do que o tempo limite. Por exemplo, se *t1* e *t2* juntos fossem maiores que o tempo limite de visita do conjunto de relatórios virtual, mas individualmente menores que o tempo limite, a visita ainda se estenderia para incluir as duas ocorrências em segundo plano:

![](assets/nogoodexample5.jpg)

Da mesma forma, se uma série de ocorrências em segundo plano ocorrerem antes de uma série de eventos em primeiro plano, um comportamento semelhante ocorre:

![](assets/nogoodexample5-1.jpg)

As ocorrências em segundo plano se comportam dessa maneira para preservar os efeitos de atribuição de eVars ou outras variáveis definidas durante as ocorrências em segundo plano. Isso permite que eventos de conversão de primeiro plano downstream sejam atribuídos a ações realizadas enquanto um aplicativo estava em segundo plano. Também permite que um container de segmento de visita inclua ocorrências em segundo plano que resultaram em uma sessão em primeiro plano downstream, útil para medir a eficácia da mensagem de push.

## Comportamento da métrica de visitas 

A contagem de visitas baseia-se exclusivamente na contagem de visitas que incluem pelo menos uma ocorrência em primeiro plano. Isso significa que quaisquer ocorrências em segundo plano órfãs ou &quot;visitas em segundo plano&quot; não contam para a métrica Visita.

## Comportamento métrico de tempo gasto por visita 

O tempo gasto ainda é calculado de forma análoga à forma como está sem ocorrências em segundo plano usando o tempo entre as ocorrências. Embora, se uma visita incluir ocorrências em segundo plano (porque ocorreram perto o suficiente das ocorrências em primeiro plano), essas ocorrências são incluídas no cálculo do tempo gasto por visita como se fossem uma ocorrência em primeiro plano.

## Configurações de processamento de ocorrências em segundo plano 

Como o processamento de ocorrências em segundo plano está disponível apenas para conjuntos de relatórios virtuais usando Processamento de tempo de relatório, o Adobe Analytics oferece suporte a duas formas de processamento de ocorrências em segundo plano para preservar as contagens de visitas no conjunto de relatórios base que não usa o Processamento de tempo de relatório. Para acessar essa configuração, navegue até o Admin Console do Adobe Analytics, vá para as configurações do conjunto de relatórios base aplicável, navegue até o menu &quot;Gerenciamento móvel&quot; e, em seguida, para o submenu &quot;Relatórios do aplicativo móvel&quot;.

1. &quot;Processamento herdado ativado&quot;: Essa é a configuração padrão para todos os conjuntos de relatórios. Deixar o processamento herdado em processa as ocorrências em segundo plano como ocorrências normais em nosso pipeline de processamento no que diz respeito ao conjunto de relatórios base de Atribuição de tempo de não relatório. Isso significa que todas as ocorrências em segundo plano que aparecem no conjunto de relatórios base incrementam as visitas como uma ocorrência normal. Se você não quiser que as ocorrências em segundo plano apareçam no conjunto de relatórios base, altere essa configuração para &quot;Desligado&quot;.
1. &quot;Processamento herdado desativado&quot;: Com o processamento herdado para ocorrências em segundo plano desativado, todas as ocorrências em segundo plano enviadas para o conjunto de relatórios base são ignoradas pelo Conjunto de relatórios base e só são acessíveis quando um conjunto de relatórios virtual criado nesse conjunto de relatórios base é configurado para usar o Processamento de tempo do relatório. Isso significa que todos os dados capturados por ocorrências em segundo plano enviadas para este conjunto de relatórios base só aparecem em um conjunto de relatórios virtual habilitado para Processamento de tempo de relatório.

   Essa configuração destina-se a clientes que desejam aproveitar o novo processamento de ocorrências em segundo plano sem alterar as contagens de visitas de seu conjunto de relatórios base.

Em ambos os casos, as ocorrências em segundo plano são faturadas ao mesmo custo de qualquer outra ocorrência enviada ao Analytics.

## Iniciar novas visitas em cada inicialização de aplicativo 

Além do processamento de ocorrências em segundo plano, os conjuntos de relatórios virtuais podem forçar uma nova visita ao start sempre que o SDK móvel envia um evento de inicialização do aplicativo. Com essa configuração ativada, sempre que um evento de inicialização de aplicativo é enviado do SDK, ele força uma nova visita ao start, independentemente de uma visita aberta ter atingido seu tempo limite. A ocorrência que contém o evento de inicialização do aplicativo é incluída como a primeira ocorrência na próxima visita e aumenta a contagem de visitas e cria um container de visita distinto para segmentação.
