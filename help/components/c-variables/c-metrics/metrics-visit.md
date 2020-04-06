---
description: Uma sequência de visualizações de página em uma sessão. A métrica de visitas normalmente é usada em relatórios que exibem o número de sessões de usuário no intervalo selecionado.
keywords: visit
title: Visita
topic: Metrics
uuid: 91317487-f116-4546-8cd2-421418c49a7a
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Visita

Uma sequência de visualizações de página em uma sessão. A métrica de visitas normalmente é usada em relatórios que exibem o número de sessões de usuário no intervalo selecionado.

>[!NOTE] Para obter informações sobre como as visitas e inicializações de aplicativos móveis são calculadas, consulte o artigo sobre [Comparação de visitas e inicializações de aplicativos móveis](https://helpx.adobe.com/br/analytics/kb/compare-visits-and-mobile-app-launches.html) na Base de conhecimento.

A métrica de visita é sempre associada com um período de tempo, para que você saiba quando contar uma nova visita caso o mesmo visitante retorne ao site. Uma sessão é start quando o usuário chega ao seu site pela primeira vez e termina em um dos seguintes cenários:

* **30 minutos de inatividade:** Quase todas as sessões terminam dessa maneira. Se passarem mais de 30 minutos entre as solicitações de imagem, uma nova visita será iniciada.
* **12 horas de atividade consistente:** Se um usuário dispara solicitações de imagens sem um intervalo de mais de 30 minutos por 12 horas, uma nova visita é automaticamente start.
* **2500 ocorrências:** Se um usuário gera um grande número de ocorrências sem iniciar uma nova sessão, uma nova visita é contada após 2500 solicitações de imagem.
* **100 ocorrências em 100 segundos**: Se uma visita consiste em mais de 100 ocorrências que ocorrem em menos de 100 segundos, a visita é encerrada automaticamente. Esse comportamento normalmente indica atividade de bot, e essa limitação é imposta para impedir que essas visitas de processamento intensivo aumentem a latência e aumentem o tempo necessário para gerar relatórios.

>[!NOTE] A definição de uma visita pode ser resumida por um conjunto de relatórios se solicitado especificamente, mas ela não pode ser ampliada. Faça com que um dos usuários suportados de sua organização entre em contato com o Atendimento ao cliente para solicitar essa alteração.

Os seguintes cenários não start uma nova visita:

* O usuário fechando a guia, reabrindo-a e navegando de volta para o seu site dentro de 30 minutos. O usuário também pode fechar seu navegador ou reinicializar o computador e ainda ser contado como uma visita única (dado que o visitante retorna ao site dentro de um período de 30 minutos).
* Usuários que navegam em seu site em várias guias. Embora a navegação com várias guias não incremente visitas ou visitantes, usar um navegador separado faz isso. Isso ocorre porque as guias diferentes fazem referência aos mesmos cookies, mas navegadores separados não.

Uma visita não necessariamente coincide com uma sessão do navegador. Por exemplo, se um visitante fechar o navegador, reabrir o navegador e chegar ao site cinco minutos depois, ele será reconhecido como uma continuação da mesma visita. Isso também significa que, se um visitante permanecer em uma página por 35 minutos, a visita terá sido fechada e processada e uma nova visita será start se ele clicar em outra página.

Quando uma visita termina, todas as variáveis com uma expiração de visita expiram e não persistem mais. A métrica de número de visita será aumentada na próxima visita para este visitante.

>[!NOTE] Se estiver utilizando o Analytics como fonte de relatório do Adobe, consulte [Redução de visitas aumentadas e contagem de visitantes no A4T](https://marketing.adobe.com/resources/help/pt_BR/target/a4t/minimizing-inflated-visit-and-visitor-counts-a4t.html) na documentação do [!DNL Target].

Para obter mais informações, consulte [Identificação de Visitantes](https://marketing.adobe.com/resources/help/pt_BR/sc/implement/visid_overview.html) únicos no Guia de implementação do Adobe Analytics.

**Períodos de tempo**

Uma visita é relatada em cada período em que ocorreu atividade. Por exemplo, suponha que uma visita comece às 23:45 do dia 1º de dezembro e continue até as 12:30 do dia 2 de dezembro. A visita é contada em 1º de dezembro e 2 de dezembro. Este relatórios se aplica a outros períodos de tempo, incluindo semanal, mensal, trimestral e anual.
