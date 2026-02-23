---
description: Saiba mais sobre a detecção de anomalias de dados no Analysis Workspace.
title: Visão geral da Detecção de anomalias
feature: Anomaly Detection
role: User, Admin
exl-id: b1625206-c774-40ef-9d92-25ee8ff1478d
source-git-commit: 8b1e25b9633b6db3e49da079f7014e6b7b595474
workflow-type: tm+mt
source-wordcount: '1294'
ht-degree: 99%

---

# Visão geral da Detecção de anomalias

É possível ver e analisar anomalias de dados de forma contextual no Analysis Workspace. A análise de contribuição trabalha em conjunto com a detecção de anomalias para ajudar a identificar o que contribuiu para a anomalia.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Detecção de anomalias](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]

>[!IMPORTANT]
>
>Os clientes do Adobe Analytics Select e do Adobe Analytics Foundation têm acesso apenas à detecção de anomalias com *granularidade diária* no espaço de trabalho. Para obter mais informações, consulte [Direitos de detecção de anomalias e análise de contribuição](#anomaly-detection-and-contribution-analysis-entitlements).

## Detecção de anomalias

A Detecção de anomalias oferece um método estatístico para determinar como uma certa métrica foi alterada com relação aos dados anteriores.

A Detecção de anomalias permite separar os &quot;sinais verdadeiros&quot; do &quot;barulho&quot; e identificar possíveis fatores que contribuem para os sinais ou as anomalias. Em outras palavras, permite identificar quais flutuações estatísticas são relevantes ou não. Em seguida, você pode identificar a causa raiz de uma anomalia verdadeira. Além disso, você pode obter previsões de métricas confiáveis (KPI).

Exemplos de anomalias que você pode investigar incluem:

* Quedas drásticas no valor diário de pedidos
* Picos em pedidos com baixa receita
* Picos ou quedas em registros de avaliação
* Quedas nas exibições da página de destino
* Picos em eventos de buffer de vídeo
* Picos em taxas de bits de vídeo baixas

A Detecção de anomalias e a [Análise de contribuição](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) são fluxos de trabalho principais no Analysis Workspace. Você pode executar a Análise de contribuição em relação a qualquer anomalia diária e incorporar o resultado ao projeto do Analysis Workspace.

O algoritmo de detecção de anomalias do Analysis Workspace inclui

* Suporte para granularidade horária, semanal e mensal, além da granularidade diária já existente.
* Percepção da sazonalidade (como “Black Friday”) e feriados.

## Análise de contribuição

A Análise de contribuição revela padrões ocultos nos dados para explicar anomalias estatísticas e identificar correlações por trás de

* ações inesperadas do cliente,
* valores fora do limite e
* picos ou declínios repentinos

de métricas selecionadas em segmentos convergentes do público-alvo.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Análise de contribuição](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/data-science/contribution-analysis-workspace){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


Algo aconteceu? Por quê? Seu relatório de Detecção de anomalias mostra um pico incomum em pedidos e você quer saber por quê. O que aconteceu fora do comum? Quem é responsável por qual campanha ou indicação? Algo se tornou viral? Quais são os fatores específicos que contribuíram para essa anomalia? E talvez o mais importante: como posso obter informações importantes sobre meu cliente e repetir esse desempenho? (Ou no caso de um declínio em uma métrica ou um aumento em uma métrica negativa, como evitar isso no futuro?)

A Análise de contribuição ajuda a avaliar seus dados imediatamente para identificar a causa de uma anomalia. Em segundos, analisa os fatores que contribuem para uma anomalia, algo que antes levava semanas, fornecendo padrões para segmentos de público-alvo e ajudando você a desenvolver uma narrativa para as interações com os clientes. Você pode usar a Análise de contribuição estrategicamente para identificar e capturar associações significativas. Em seguida, use essas associações estrategicamente para desenvolver novos segmentos de público-alvo ou taticamente para identificar atividades fora do limite ou fraudulentas que acionam um alerta.

A [Detecção de anomalias](#anomaly-detection) identifica picos de dados e declínios estatísticos extremos com base em métricas selecionadas e segmentos de público-alvo selecionados. A Detecção de anomalias define uma norma histórica com base em um período de treinamento e, em seguida, representa os desvios extremos que se correlacionam com eventos específicos. A Detecção de anomalias pode indicar um aumento repentino em uma métrica positiva de Pedidos ou um aumento em uma métrica negativa de Devoluções, ou quedas em ambas, capturando pontos de dados estatisticamente relevantes para serem avaliados pela Análise de contribuição. Uma vez identificada uma anomalia estatística, a Análise de contribuição permite explorar e avaliar as variáveis relevantes de marketing e campanha em todos os pontos de dados anômalos. Ela executa algoritmos avançados e processos de aprendizado de máquina para avaliar associações que contribuíram para um pico ou declínio significativo. Esses cálculos são exibidos em visualizações interativas projetadas para apresentar diversas perspectivas que ajudam a responder por que algo aconteceu e o que fazer a respeito.

A Análise de contribuição ajuda a desenvolver uma narrativa para descrever por que ocorreu uma anomalia. E como responder a anomalias, capturando métricas relevantes e identificando pontos ocultos que fornecem uma visão geral dos motivos das interações do público-alvo e das tendências de interesse dos clientes. Às vezes, uma anomalia é fácil de identificar e corrigir, como um pedido equivocado de 2.000 caiaques. Às vezes, é complexo, como identificar uma nova tendência em um período em uma região que reage apenas a uma campanha direcionada específica. Unir os itens de contribuição em métricas para várias dimensões e suas associações fornece uma ideia geral das interações do público-alvo e ajuda a fornecer contexto para pontos de dados anômalos.

Estes são alguns casos de uso:

* Identificar o potencial de recomercialização monitorando as alterações na demanda do produto.
* Melhorar a experiência do cliente, respondendo aos interesses específicos do público-alvo.
* Identificar rápido os pedidos fraudulentos através de um relatório de pedidos fora dos limites.
* Proteger-se da espionagem corporativa, identificando usos e downloads excessivos.
* Monitorar operações como a geração de relatórios de tags JavaScript ausentes.

Após uma análise abrangente de uma anomalia, será gerado um Resumo das contribuições para os itens superiores de acordo com o total de ocorrências e a porcentagem dos valores de contribuição de cada item. A Pontuação de contribuição normalizada facilita comparações, contrastes e associações com outros itens de dimensão importantes.

## Tokens da Análise de contribuição

Todos os clientes com direitos à análise de contribuição podem executar análises de contribuição completas um número limitado de vezes por mês no Analysis Workspace. A Análise de contribuição **exclui** clientes de produtos isolados (SiteCatalyst 15), clientes do Analytics Foundation e clientes do Analytics Select, que não têm direito à Análise de contribuição.

O número de execuções por empresa é limitado por tokens mensais concedidos com base no produto do Adobe Analytics que sua empresa adquiriu. O número de execuções por empresa inclui a capacidade de restringir o acesso à Análise de contribuição para evitar o uso indevido do token.

## Perguntas frequentes

| Pergunta | Resposta |
| --- | --- |
| Por que a Adobe apresentou os tokens? | A análise de contribuição é um dos recursos mais importantes do Adobe Analytics. Com um pequeno número de execuções completas por mês (em vez de apenas 3 dimensões para alguns produtos do Analytics), você pode ter uma ideia melhor do que a Análise de contribuição completa e ilimitada pode fazer. |
| Como os tokens funcionam na Análise de contribuição? Custa um token para carregar um projeto com uma Análise de contribuição já existente ou apenas ao executar uma nova? | Cada logon da empresa (não de cada usuário) recebe um certo número de tokens por mês, que permitem executar Análises de contribuição completas no Analysis Workspace.  Cada vez que uma nova Análise de contribuição é gerada, você paga um token. O carregamento de projetos com Análises de contribuição pré-executadas não consomem um token. |
| Se minha empresa estiver sem tokens e quiser executar Análises de contribuição adicionais, o que podemos fazer? | É possível atualizar para outro produto do Adobe Analytics, por exemplo, do Standard (2 tokens/mês) para o Ultimate (20 tokens/mês). Não é possível comprar mais tokens. Você deve atualizar dentro da estrutura de pacotes existente. |
| Como restringir o acesso à Análise de contribuição? | Por padrão, somente os administradores têm acesso para executar Análises de contribuição. No entanto, os administradores podem conceder acesso a outros usuários criando um grupo de permissões no [Adobe Admin Console](/help/admin/admin-console/home.md). É importante dar permissão de uso para a Análise de contribuição somente aos usuários com uma razão legítima para usá-la e que não abusarão do acesso. A permissão é chamada [!UICONTROL Análise de contribuição] em [!UICONTROL Ferramentas do conjunto de relatórios]. [Saiba mais](/help/admin/admin-console/permissions/report-suite-tools.md) |
| Como posso saber a quantos tokens minha empresa tem direito por mês e quantos já usamos no mês atual? | Acesse [!UICONTROL Administrador] > [!UICONTROL Todos os administradores] > [!UICONTROL Página inicial das configurações da empresa] > [!UICONTROL Exibir níveis de acesso ao recurso]. Procurar em<ul><li>Análise de contribuição: número de tokens de uso mensais</li><li>Análise de contribuição: número de tokens de uso usados neste mês</li></ul> |

## Direitos de Detecção de anomalias e Análise de contribuição

Abaixo há uma lista dos direitos de Detecção de anomalias e Análise de contribuição no Analysis Workspace.

<table id="table_5C9B7E4AE82640B5A913519E576889B5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Direito de uso do Adobe Analytics </th> 
   <th colname="col2" class="entry"> Detecção de anomalias </th> 
   <th colname="col3" class="entry"> Análise de contribuição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Foundation </p> </td> 
   <td colname="col2"> <p>Somente granularidade diária </p> </td> 
   <td colname="col3" colsep="1"> <p>Nenhum token </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://business.adobe.com/products/analytics/compare-adobe-analytics-packages.html?promoid=B4XQ3X7G&mv=other"  >Select</a> </p> </td> 
   <td colname="col2"> <p>Somente granularidade diária </p> </td> 
   <td colname="col3"> <p>Nenhum token </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://business.adobe.com/products/analytics/compare-adobe-analytics-packages.html?promoid=91BF51TR&mv=other"  >Prime</a> </p> </td> 
   <td colname="col2"> <p>Sim </p> </td> 
   <td colname="col3"> <p>10 tokens por mês </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://business.adobe.com/products/analytics/compare-adobe-analytics-packages.html?promoid=8N4B5F1V&mv=other"  > Ultimate</a> </p> </td> 
   <td colname="col2"> <p>Sim </p> </td> 
   <td colname="col3"> <p>20 tokens por mês </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Complemento do Predictive Workbench </p> </td> 
   <td colname="col2"> <p>Sim </p> </td> 
   <td colname="col3"> <p>Tokens ilimitados </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standard </p> 
    <ul id="ul_73D52020793B44868C9CE0F90893075D"> 
     <li id="li_21EE0871C87E43C8B781219B2BA0FA74">Adobe Analytics Core </li> 
     <li id="li_AB3593200F33439BAEE8FEB13CAE57F4">Adobe Analytics OD </li> 
     <li id="li_2B7D625519BC4A4CB598C95F15D3029B">Adobe Analytics MA </li> 
    </ul> </td> 
   <td colname="col2"> <p>Sim </p> </td> 
   <td colname="col3"> <p>2 tokens por mês </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium (360, Attribution) </p> </td> 
   <td colname="col2"> <p>Sim </p> </td> 
   <td colname="col3"> <p>2 tokens por mês </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium (Complete, <a href="https://business.adobe.com/products/analytics/predictive-analytics.html"  >Predictive Intelligence</a>) </p> </td> 
   <td colname="col2"> <p>Sim </p> </td> 
   <td colname="col3"> <p>Tokens ilimitados </p> </td> 
  </tr> 
 </tbody> 
</table>
