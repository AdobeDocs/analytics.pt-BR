---
title: Visitas
description: A sequência de exibições de página em uma sessão.
translation-type: tm+mt
source-git-commit: 178e372e63c436268a1f7028d986504983430b2f
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 5%

---


# Visitas

A métrica &quot;Visitas&quot; mostra o número de sessões em todos os visitantes do site.

## Como essa métrica é calculada

Uma visita sempre se vincula a um período, de modo que você saiba se deve contar uma nova visita se a mesma pessoa retornar ao site. Uma visita é start quando o usuário chega ao seu site pela primeira vez. Uma visita termina quando atender a qualquer um dos seguintes critérios:

* **30 minutos de inatividade**: Quase todas as sessões terminam dessa maneira. Se passarem mais de 30 minutos entre as ocorrências, uma nova visita será iniciada.
* **12 horas de atividade**: Se um usuário envia solicitações de imagem de forma consistente sem falhas de 30 minutos por mais de 12 horas, uma nova visita é automaticamente start.
* **2500 ocorrências**: Se um usuário gera um grande número de ocorrências sem iniciar uma nova sessão, uma nova visita é contada após 2500 solicitações de imagem.
* **100 hits em 100 segundos**: se uma visita consiste em mais de 100 hits que ocorrem em menos de 100 segundos, a visita se encerra automaticamente. Esse comportamento normalmente indica atividade de bot e essa limitação é imposta para ajudar a aumentar o desempenho do relatório.

Uma visita não necessariamente coincide com uma sessão do navegador devido aos critérios acima. Uma das diferenças mais comuns é onde um visitante navega até seu site, deixa a guia aberta por mais de 30 minutos e reinicia a navegação. Embora essa ação seja tecnicamente parte da mesma sessão de navegação, o Adobe considera essa ação duas visitas separadas.

## Comportamento que afeta visitas

Se um visitante executar qualquer uma dessas ações, um novo start de visita:

* Limpa a meia sessão do cache e continua a navegar no site
* Deixa o site aberto em uma guia por mais de 30 minutos e continua navegando
* Abre um navegador diferente e navega até seu site no mesmo computador
* A mesma pessoa que navega no site em dispositivos diferentes

Se um visitante executar qualquer uma dessas ações, uma nova visita **não** será start, contanto que haja menos de 30 minutos entre ocorrências consecutivas:

* Fecha o navegador e, em seguida, navega para o site novamente
* Reinicializa o computador, abre o mesmo navegador e navega para o site novamente
* Transição para uma rede diferente, como desconectar de uma docking station de rede com fio para uma rede sem fio
* Navegue pelo site em várias guias. Se um visitante alternar entre guias, cada ocorrência contará como parte da mesma visita.

## Alterar a definição de uma visita

É possível alterar a definição de uma visita para um horário que não ultrapasse 30 minutos.

* Para conjuntos [de relatórios](../vrs/vrs-about.md)virtuais, é possível alterar o tempo limite de visita usando o menu suspenso Tempo limite [!UICONTROL de] visita. Você pode alterar o tempo limite da visita para qualquer valor razoável.
* Para conjuntos de relatórios padrão, entre em contato com o Atendimento ao cliente para solicitar que a duração da visita seja reduzida para um determinado conjunto de relatórios. A duração da visita dos conjuntos de relatórios padrão não pode exceder 30 minutos, portanto, você só pode reduzi-la.

## Visitas que abrangem um limite de data

Uma visita conta para cada período envolvido. Por exemplo, se você tiver um visitante que start navegando em seu site na segunda-feira às 11:45, em seguida, envia sua última solicitação de imagem na terça-feira às 12:10, você verá uma visita atribuída tanto à segunda quanto à terça-feira. No entanto, a métrica de visita total é desduplicada, mostrando uma única visita para o intervalo de datas do projeto.

## Visitas em uma dimensão em relação ao total de visitas

Visitas no contexto de uma dimensão (por exemplo, canal [de](../dimensions/marketing-channel.md)marketing) mostram o número de visitas que continham um item de dimensão específico a qualquer momento. Vários itens de dimensão frequentemente existem em diferentes ocorrências na mesma visita. Tentar somar visitas que relatam em itens de dimensão normalmente não faz sentido.
