---
description: Lista diversos motivos pelos quais podem ocorrer discrepâncias de dados entre os relatórios do Adobe Analytics e do DFA.
keywords: DFA
seo-description: Lista diversos motivos pelos quais podem ocorrer discrepâncias de dados entre os relatórios do Adobe Analytics e do DFA.
seo-title: Possíveis motivos de discrepâncias
solution: Analytics
title: Possíveis motivos de discrepâncias
topic: Conectores de dados
uuid: fd 414 cc 6-d 568-491 e -9 b 1 c -5 d 493 dcfbe 45
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Possíveis motivos de discrepâncias{#possible-reasons-for-discrepancies}

Lista diversos motivos pelos quais podem ocorrer discrepâncias de dados entre os relatórios do Adobe Analytics e do DFA.

## Usuários que usam navegador Safari e outros navegadores que bloqueiam cookies de terceiros {#section-4b0dc429a54a4744a33976b0bb2d1b2a}

A aceitação de cookies de terceiros é normalmente o principal motivo de discrepância entre o Adobe Analytics e o DFA. O Safari e alguns outros navegadores bloqueiam cookies de terceiros por padrão. Isso significa que, por padrão, o Safari aceita os cookies proprietários usados pela maioria das implementações do Analytics, mas rejeita os cookies de terceiros usados pelo DFA.

Uma amostra de dados de nossos clientes do Analytics 15 beta mostrou que menos de 0.5% dos usuários normalmente rejeitam cookies primários, enquanto 5-12 % rejeitam cookies de terceiros (muitas dessas rejeições são provavelmente causadas por configurações padrão do navegador).

Essa discrepância pode resultar em uma grande diferença nos dados coletados pelo Analytics e pelo DFA.

## Por que as impressões relatadas no DFA podem ser mais altas que as impressões relatadas no Adobe Analytics? {#section-db0ad070a65a4985bcc589b2d0d30b90}

* O DFA envia dados para os servidores de coleta de dados da Adobe em um lote noturno, então os dados de impressões no Analytics podem ter até 2 dias de atraso em relação aos relatórios do DFA.
* A Adobe usa as classificações SAINT para classificar códigos de rastreamento do DFA importados em vários níveis de agregação (nome da campanha, nome do posicionamento, nome do anúncio etc.). Se a discrepância aparecer durante a execução de um relatório de classificação, realize um teste simples para verificar se as classificações ainda não alcançaram as métricas importadas:

   * No relatório de classificação, localize um item de linha chamado “Nenhum”.
   * Faça um detalhamento desse item de linha pela mesma variável, usando o relatório bruto da ID do DFA (por exemplo, ID da campanha).
   * Nesse relatório, tome nota de todos os códigos de rastreamento do DFA não classificados que estejam no formato DFA:XXXXX:XXXXX ...
   * Se houver muitos desses códigos de rastreamento, investigue o processo noturno de classificação SAINT.

## Por que os cliques do DFA podem ser maiores do que os click-throughs do Adobe Analytics? {#section-2fce4608ed044bdc9cf812cb719d5d35}

* O DFA registra um clique antes de o visitante chegar ao site do cliente. O Analytics registra click-throughs depois que a página de aterrissagem é carregada e executa o beacon de JavaScript da Adobe. Normalmente, as discrepâncias ocorrem porque o visitante não está chegando à página de aterrissagem depois que o DFA rastreia um clique ou porque o temporizador *`s.maxDelay`* termina.
* Verifique se todos os posicionamentos e criações na configuração do Floodlight incluem o parâmetro clickThroughParam no URL da página de aterrissagem (por exemplo, “?CID=1”). Deixar de definir esse parâmetro fará com que o JavaScript do Adobe Analytics ignore todos os click-throughs que ocorrerem depois da primeira visita.
* Verifique se todos os posicionamentos e criações têm uma página de aterrissagem marcada com o JavaScript e o módulo DFA Integrate, bem como se a ID de configuração do Floodlight nessa página de aterrissagem coincide com a ID de configuração do Floodlight nos anúncios veiculados. As discrepâncias frequentemente ocorrem porque a página de aterrissagem dos anúncios é definida para um site de terceiros ou para os anúncios veiculados.
* Se você usa anúncios Rich Media ou anúncios Flash (swf), verifique se, quando o rastreador de cliques do DFA é acessado, o navegador do visitante também é redirecionado para a página de aterrissagem com o parâmetro `clickThroughParam` incluído na sequência de consulta. O não redirecionamento do navegador impedirá o registro de um click-through.
* Os tempos limite representam instâncias nas quais os dados do DFA podem ter sido disponibilizados mas o JavaScript não recebeu uma resposta a tempo. Quando um visitante chega à página de aterrissagem, o JavaScript da Adobe solicita as informações do visitante do serviço fls.doubleclick.net do DFA. O parâmetro *`s.maxDelay`* determina quanto tempo o JavaScript aguarda pelos dados do Floodlight Service (FLS). If *`s.maxDelay`* is too high, visitors can leave the site before Adobe collects the hit data; meaning that no click data is recorded. If *`s.maxDelay`* is set too low, the visitor's Internet connection cannot retrieve the FLS data in time; meaning that the hit is sent to Adobe without DFA click information. See [Tuning s.maxDelay](../../dfa-data-connector-analytics/dfa-integration/dfa-tuning-s-maxlelay.md#concept-6deb28eee18e414db220d6009d449f0d) for a further discussion on this subject.

* O tráfego de robô pode aumentar o número de cliques do DFA. Os robôs podem ter funcionalidade para clicar em anúncios, mas podem não ter a complexidade para executar um beacon do Analytics ou disparar a tag de script síncrona para carregar os dados de solicitação dos servidores Floodlight. Se esses robôs não são removidos do número de cliques, isso pode ser uma fonte de discrepância.
* Os visitantes que deixarem a página antes que o *`s.maxDelay`* expire e que os dados do DFA retornem serão perdidos; nenhum dado do DFA ou de visitante será coletado para eles.
* O Analytics tenta identificar e remover click-throughs duplicados para que eles sejam contados apenas uma vez por campanha, por visita. O DFA conta os visitantes que clicam em “Voltar” e passam pelo redirecionamento do anúncio várias vezes como cliques de ACM adicionais, enquanto o Analytics não os conta como vários click-throughs.
* As tags do DFA Floodlight não dependem da habilitação do JavaScript, ao contrário do Analytics. Por esse motivo, pode haver alguns casos em que o DFA registre um hit e o Analytics não registre. Para identificar se isso pode ser um problema, use o relatório JavaScript do Analytics no menu Perfil do visitante.

## Por que as atividades pós-impressão do DFA podem ser maiores do que os view-throughs do Adobe Analytics? {#section-5daa91039c404df48b6a3447c20406f7}

* O Analytics tenta identificar e remover click-throughs duplicados para que eles sejam contados apenas uma vez por campanha, por visita. O DFA conta os visitantes que clicam em “Voltar” e passam pelo redirecionamento do anúncio várias vezes como cliques de ACM adicionais, enquanto o Analytics não os conta como vários click-throughs.
* As tags do DFA Floodlight não dependem da desabilitação do JavaScript, ao contrário do Analytics. Por esse motivo, pode haver alguns casos em que o DFA registre um hit e o Analytics não registre. 
* O DFA conta as atividades pós-impressão ao usar tags do Floodlight, que podem ser colocadas no site do cliente. O Analytics conta os view-throughs após a execução do beacon do JavaScript (solicitação de imagem). O posicionamento do código na página da Web pode determinar se o aborto do carregamento de uma página conta como atividade pós-impressão ou como view-through.

## E se as discrepâncias estiverem muito além de um limite aceitável e os possíveis motivos acima não forem aplicáveis? {#section-ca50eb75dd5d4d0396f4668b44d7547c}

Fale com seu Consultor de integração ou com o Adobe Client Care para documentar as discrepâncias e relatá-las para a equipe de engenharia dos Conectores de dados. Para acelerar sua solicitação, tenha 2 ou 3 dias de dados comparando as métricas em questão (no nível de código de uma campanha). Na solicitação, identifique todas as ações que você já tenha realizado para comparar a discrepância.
