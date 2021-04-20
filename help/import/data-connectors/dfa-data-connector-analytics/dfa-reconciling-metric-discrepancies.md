---
description: Ocasionalmente, algumas métricas podem não se encaixar em uma diferença aceitável na comparação de métricas do Adobe Analytics com métricas do DFA. Abaixo está uma lista de definições de métricas e possíveis motivos para variações.
keywords: DFA
title: Comparação de discrepâncias de métricas
feature: Data Connectors
uuid: aa3ca006-d3cf-410e-a000-781ab17fb9e3
exl-id: bfe0f9cb-1bbc-40f9-b996-0002d5143889
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '1270'
ht-degree: 100%

---

# Comparação de discrepâncias de métricas {#reconciling-metric-discrepancies}

Ocasionalmente, algumas métricas podem não se encaixar em uma diferença aceitável na comparação de métricas do Adobe Analytics com métricas do DFA. Abaixo está uma lista de definições de métricas e possíveis motivos para variações.

Esta seção inclui os seguintes tópicos:

## Definições de Métricas {#metric-definitions}

A Adobe usa os seguintes termos ao falar sobre as métricas relacionadas à integração do DFA:

**Impressões**: as impressões se referem ao número de vezes que um anúncio foi visualizado. As impressões são registradas para cada anúncio, mas também podem ser agregadas em grupos de anúncios ou outros agrupamentos de vários anúncios. A métrica de impressões no Analytics é importada do DFA por uma importação noturna de fontes de dados.

**Cliques**: os cliques se referem ao número de vezes que um anúncio foi clicado, conforme o relatório do DFA. Os cliques são registrados na página de redirecionamento do DFA antes que o visitante chegue ao site do cliente. Assim como as impressões, a métrica de cliques no Analytics é importada do DFA por uma importação noturna de fontes de dados.

**Click-throughs**: os click-throughs se referem ao número de vezes que o usuário chegou à página de aterrissagem após clicar em um anúncio. Essa métrica pode ser ligeiramente diferente dos cliques.

**View-throughs**: os view-throughs se referem ao número de vezes que um visitante acessou o site do cliente após visualizar um anúncio, mas SEM ter clicado no anúncio. O visitante deve acessar o site dentro do período de view-through, que por padrão é definido para 30 dias. A impressão deve ter ocorrido mais recentemente do que o último clique. Os view-throughs são registrados uma vez por campanha, por visita, e são contados quando a integração preenche a eVar de view-through com a ID de campanha do DFA e o evento de view-through é definido.

## Possíveis motivos de discrepâncias {#possible-reasons-for-discrepancies}

Lista diversos motivos pelos quais podem ocorrer discrepâncias de dados entre os relatórios do Adobe Analytics e do DFA.

### Usuários que usam navegador Safari e outros navegadores que bloqueiam cookies de terceiros {#section-4b0dc429a54a4744a33976b0bb2d1b2a}

A aceitação de cookies de terceiros é normalmente o principal motivo de discrepância entre o Adobe Analytics e o DFA. O Safari e alguns outros navegadores bloqueiam cookies de terceiros por padrão. Isso significa que, por padrão, o Safari aceita os cookies proprietários usados pela maioria das implementações do Analytics, mas rejeita os cookies de terceiros usados pelo DFA.

Uma amostra de dados de nossos clientes do Analytics 15 beta mostrou que menos de 0,5% dos usuários normalmente rejeita cookies proprietários, enquanto 5% a 12% dos usuários rejeitam cookies de terceiros (muitas dessas rejeições são provavelmente causadas pelas configurações padrão do navegador).

Essa discrepância pode resultar em uma grande diferença nos dados coletados pelo Analytics e pelo DFA.

### Por que as impressões relatadas no DFA podem ser mais altas que as impressões relatadas no Adobe Analytics?  {#section-db0ad070a65a4985bcc589b2d0d30b90}

* O DFA envia dados para os servidores de coleta de dados da Adobe em um lote noturno, então os dados de impressões no Analytics podem ter até 2 dias de atraso em relação aos relatórios do DFA.
* A Adobe usa as classificações SAINT para classificar códigos de rastreamento do DFA importados em vários níveis de agregação (nome da campanha, nome do posicionamento, nome do anúncio etc.). Se a discrepância aparecer durante a execução de um relatório de classificação, realize um teste simples para verificar se as classificações ainda não alcançaram as métricas importadas:

   * No relatório de classificação, localize um item de linha chamado “Nenhum”.
   * Faça um detalhamento desse item de linha pela mesma variável, usando o relatório bruto da ID do DFA (por exemplo, ID da campanha).
   * Nesse relatório, tome nota de todos os códigos de rastreamento do DFA não classificados que estejam no formato `DFA:XXXXX:XXXXX`.
   * Se houver muitos desses códigos de rastreamento, investigue o processo noturno de classificação SAINT.

### Por que os cliques do DFA podem ser maiores do que os click-throughs do Adobe Analytics?  {#section-2fce4608ed044bdc9cf812cb719d5d35}

* O DFA registra um clique antes de o visitante chegar ao site do cliente. O Analytics registra click-throughs depois que a página de aterrissagem é carregada e executa o beacon de JavaScript da Adobe. Normalmente, as discrepâncias ocorrem porque o visitante não está chegando à página inicial depois que o DFA rastreia um clique ou porque o temporizador `s.maxDelay` termina.
* Verifique se todos os posicionamentos e criações na configuração do Floodlight incluem o parâmetro clickThroughParam no URL da página de aterrissagem (por exemplo, “`?CID=1`”). Deixar de definir esse parâmetro fará com que o JavaScript do Adobe Analytics ignore todos os click-throughs que ocorrerem depois da primeira visita.
* Verifique se todos os posicionamentos e criações têm uma página de aterrissagem marcada com o JavaScript e o módulo DFA Integrate, bem como se a ID de configuração do Floodlight nessa página de aterrissagem coincide com a ID de configuração do Floodlight nos anúncios veiculados. As discrepâncias frequentemente ocorrem porque a página de aterrissagem dos anúncios é definida para um site de terceiros ou para os anúncios veiculados.
* Se você usa anúncios Rich Media ou anúncios Flash (swf), verifique se, quando o rastreador de cliques do DFA é acessado, o navegador do visitante também é redirecionado para a página inicial com o parâmetro `clickThroughParam` incluído na sequência de consulta. O não redirecionamento do navegador impedirá o registro de um click-through.
* Os tempos limite representam instâncias nas quais os dados do DFA podem ter sido disponibilizados mas o JavaScript não recebeu uma resposta a tempo. Quando um visitante chega à página de aterrissagem, o JavaScript da Adobe solicita as informações do visitante do serviço fls.doubleclick.net do DFA. O parâmetro `s.maxDelay`determina quanto tempo o JavaScript aguarda pelos dados do Floodlight Service (FLS). Se `s.maxDelay` for muito alto, os visitantes podem deixar o site antes que a Adobe colete os dados de hit, o que significa que nenhum dado de clique é registrado. Se `s.maxDelay` é definido como muito baixo, a conexão de Internet do visitante não consegue recuperar os dados do FLS a tempo, o que significa que o hit é enviado para a Adobe sem informações de cliques do DFA.
* O tráfego de robô pode aumentar o número de cliques do DFA. Os robôs podem ter funcionalidade para clicar em anúncios, mas podem não ter a complexidade para executar um beacon do Analytics ou disparar a tag de script síncrona para carregar os dados de solicitação dos servidores Floodlight. Se esses robôs não são removidos do número de cliques, isso pode ser uma fonte de discrepância.
* Os visitantes que deixarem a página antes que o `s.maxDelay` expire e que os dados do DFA retornem serão perdidos; nenhum dado do DFA ou de visitante será coletado para eles.
* O Analytics tenta identificar e remover click-throughs duplicados para que eles sejam contados apenas uma vez por campanha, por visita. O DFA conta os visitantes que clicam em “Voltar” e passam pelo redirecionamento do anúncio várias vezes como cliques de ACM adicionais, enquanto o Analytics não os conta como vários click-throughs.
* As tags do DFA Floodlight não dependem da habilitação do JavaScript, ao contrário do Analytics. Por esse motivo, pode haver alguns casos em que o DFA registre um hit e o Analytics não registre. Para identificar se isso pode ser um problema, use o relatório JavaScript do Analytics no menu Perfil do visitante.

### Por que as atividades pós-impressão do DFA podem ser maiores do que os view-throughs do Adobe Analytics?  {#section-5daa91039c404df48b6a3447c20406f7}

* O Analytics tenta identificar e remover click-throughs duplicados para que eles sejam contados apenas uma vez por campanha, por visita. O DFA conta os visitantes que clicam em “Voltar” e passam pelo redirecionamento do anúncio várias vezes como cliques de ACM adicionais, enquanto o Analytics não os conta como vários click-throughs.
* As tags do DFA Floodlight não dependem da desabilitação do JavaScript, ao contrário do Analytics. Por esse motivo, pode haver alguns casos em que o DFA registre um hit e o Analytics não registre.
* O DFA conta as atividades pós-impressão ao usar tags do Floodlight, que podem ser colocadas no site do cliente. O Analytics conta os view-throughs após a execução do beacon do JavaScript (solicitação de imagem). O posicionamento do código na página da Web pode determinar se o aborto do carregamento de uma página conta como atividade pós-impressão ou como view-through.

### E se as discrepâncias estiverem muito além de um limite aceitável e os possíveis motivos acima não forem aplicáveis?  {#section-ca50eb75dd5d4d0396f4668b44d7547c}

Fale com seu Consultor de integração ou com o Adobe Client Care para documentar as discrepâncias e relatá-las para a equipe de engenharia dos Data Connectors. Para acelerar sua solicitação, tenha 2 ou 3 dias de dados comparando as métricas em questão (no nível de código de uma campanha). Na solicitação, identifique todas as ações que você já tenha realizado para comparar a discrepância.
