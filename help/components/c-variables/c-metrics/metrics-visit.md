---
description: A sequência de exibições de página em uma sessão. A métrica de visitas normalmente é usada em relatórios que exibem o número de sessões de usuário no intervalo selecionado.
keywords: visit
title: Visita
topic: Metrics
uuid: 91317487-f116-4546-8cd2-421418c49a7a
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Visita

A sequência de exibições de página em uma sessão. A métrica de visitas normalmente é usada em relatórios que exibem o número de sessões de usuário no intervalo selecionado.

> [!NOTE] Para obter informações sobre como as visitas e inicializações de aplicativos móveis são calculadas, consulte o artigo sobre [Comparação de visitas e inicializações de aplicativos móveis](https://helpx.adobe.com/br/analytics/kb/compare-visits-and-mobile-app-launches.html) na Base de conhecimento.

A métrica de visita é sempre associada com um período de tempo, para que você saiba quando contar uma nova visita caso o mesmo visitante retorne ao site. Uma sessão é iniciada quando o usuário chega ao site pela primeira vez e é encerrada com umas das três possíveis situações:

* **30 minutos de inatividade:** Quase todas as seções encerram desta maneira. Se passarem mais de 30 minutos entre as solicitações de imagem, uma nova visita é iniciada.
* **12 horas de atividade consistente:** Se um usuário dispara solicitações de imagem sem um intervalo de 30 ou mais minutos por 12 horas, uma nova visita inicia automaticamente.
* **2500 hits:** se um usuário gera um número grande de hits sem iniciar uma nova sessão, uma nova visita é contabilizada após 2500 solicitações de imagem.
* **100 hits em 100 segundos**: se uma visita consiste em mais de 100 hits que ocorrem em menos de 100 segundos, a visita se encerra automaticamente. Geralmente, esse comportamento indica atividade bot, e essa limitação é imposta para impedir que essas visitas de processamento intenso aumentem a latência e o tempo que leva para que o relatórios sejam gerados.

> [!NOTE] A definição de uma visita pode ser resumida por um conjunto de relatórios se solicitado especificamente, mas ela não pode ser ampliada. Faça com que um dos usuários suportados de sua organização entre em contato com o atendimento ao cliente para solicitar essa alteração.

As situações a seguir não iniciam uma nova visita:

* O usuário fechando a guia, a reabrindo e navegando de volta ao site dentro de 30 minutos. Os usuários também podem fechar seus navegadores ou reiniciar o computador e ainda serem contados como uma visita única (dado que o visitante retorna ao site dentro de um período de 30 minutos).
* Usuários navegando do site em diversas guias. Navegar com várias guias não aumenta o número de visitas ou visitantes, mas usar um navegador separado, sim. Isso acontece porque as guias diferentes fazem referência aos mesmos cookies, mas não navegadores separados.

Uma visita não precisa necessariamente coincidir com uma sessão de navegador. Por exemplo, se um visitante fecha e reabre o navegador e visita site cinco minutos depois, a visita é considerada a mesma. Isso também significa que, se um visitante permanecer em uma página por 35 minutos, a visita terá sido fechada e processada e uma nova visita será iniciada se ele clicar em outra página.

Quando uma visita termina, todas as variáveis com uma expiração de visita expiram e não continuam. A métrica de número de visitas sofrerá aumento na próxima visita do visitante.

> [!NOTE] Se estiver utilizando o Analytics como fonte de relatório do Adobe, consulte [Redução de visitas aumentadas e contagem de visitantes no A4T](https://marketing.adobe.com/resources/help/pt_BR/target/a4t/minimizing-inflated-visit-and-visitor-counts-a4t.html) na documentação do [!DNL Target].

Para obter mais informações, consulte [Identificação de visitantes únicos](https://marketing.adobe.com/resources/help/pt_BR/sc/implement/visid_overview.html) No Guia de implementação do Adobe Analytics.

**Períodos de tempo**

Uma visita relatada em qualquer período de tempo no qual uma atividade ocorreu. Por exemplo, suponha que uma visita começa às 23h45 no dia 01 de dezembro, e continua até às 12h30 do dia 02 de dezembro. A visita é contada em 1º de dezembro e 2 de dezembro. Esse relato se aplica a outros períodos de tempo, inclusive semanal, mensal, trimestral e anual.
