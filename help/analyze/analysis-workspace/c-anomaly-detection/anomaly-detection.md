---
description: Entenda como visualizar e analisar anomalias de dados de forma contextual no Analysis Workspace.
title: Visão geral da Detecção de anomalias
feature: Anomaly Detection
role: User, Admin
exl-id: b1625206-c774-40ef-9d92-25ee8ff1478d
source-git-commit: d37fa0aff0b1bbe196b943bc26e86b1e79936184
workflow-type: tm+mt
source-wordcount: '1300'
ht-degree: 68%

---

# Visão geral da Detecção de anomalias

É possível ver e analisar anomalias de dados de forma contextual no Analysis Workspace. A Análise de contribuição trabalha com a Detecção de anomalias para ajudar a identificar o que contribuiu para a anomalia.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Detecção de anomalias](https://video.tv.adobe.com/v/25444?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]

>[!IMPORTANT]
>
>Os clientes do Adobe Analytics Select e do Adobe Analytics Foundation têm acesso somente à *granularidade diária* Detecção de anomalias na Workspace. Para obter mais informações, consulte [Direitos de Detecção de anomalias e Análise de contribuição](#anomaly-detection-and-contribution-analysis-entitlements).

## Detecção de anomalias

A Detecção de anomalias oferece um método estatístico para determinar como uma certa métrica foi alterada com relação aos dados anteriores.

A Detecção de anomalias permite separar os &quot;sinais verdadeiros&quot; do &quot;barulho&quot; e identificar possíveis fatores que contribuem para os sinais ou as anomalias. Em outras palavras, ele permite identificar quais flutuações estatísticas importam ou não. Assim, você pode identificar a causa raiz de uma verdadeira anomalia. Além disso, é possível obter previsões de métrica confiáveis (KPI).

Exemplos de anomalias que você pode investigar incluem:

* Quedas drásticas no valor médio de pedido
* Picos em pedidos com receita baixa
* Picos ou quedas em registros de avaliação
* Quedas em visualizações da página inicial
* Picos em eventos de buffer de vídeo
* Picos em taxas de vídeo baixas

A Detecção de anomalias e a [Análise de contribuição](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/anomaly-detection/anomaly-detection) são fluxos de trabalho principais no Analysis Workspace. Você pode executar a Análise de contribuição em relação a qualquer anomalia diária e incorporar o resultado ao projeto do Analysis Workspace.

O algoritmo de detecção de anomalias do Analysis Workspace inclui

* Oferece suporte para granularidade horária, semanal e mensal, além da granularidade diária existente.
* Oferece conscientização de sazonalidade (como “Black Friday”) e feriados.

## Análise de contribuição

A Análise de contribuição revela padrões ocultos nos dados para explicar anomalias estatísticas e identificar correlações por trás

* ações inesperadas do cliente,
* valores fora do limite e
* picos ou declínios repentinos

para métricas selecionadas em segmentos convergentes do público.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Análise de contribuição](https://video.tv.adobe.com/v/25443?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


Algo aconteceu? Por quê? Seu relatório de Detecção de anomalias mostra um pico incomum em pedidos e você quer saber por quê. O que aconteceu fora do comum? Quem é responsável por qual campanha ou indicação? Algo se tornou viral? Quais são os fatores específicos que contribuíram para essa anomalia? E talvez o mais importante: como posso obter informações importantes sobre meu cliente e repetir esse desempenho? (Ou no caso de um declínio em uma métrica ou um aumento em uma métrica negativa, como evitar isso no futuro?)

A Análise de contribuição ajuda a avaliar seus dados imediatamente para identificar a causa de uma anomalia. Ela analisa o que contribuiu para uma anomalia em segundos, o que antes levaria semanas, fornecendo padrões para os segmentos do público-alvo e ajudando a desenvolver uma narrativa para interações com os clientes. Você pode empregar a Análise de contribuição estrategicamente para identificar e capturar associações significativas. Em seguida, use essas associações estrategicamente para desenvolver novos segmentos de público-alvo ou taticamente para identificar atividades fora do limite ou fraudulentas que acionam um alerta.

A [Detecção de anomalias](#anomaly-detection) identifica picos de dados e declínios estatísticos extremos com base em métricas selecionadas e segmentos de público-alvo selecionados. A Detecção de anomalias define uma norma histórica com base em um período de treinamento e, em seguida, representa deslocamentos extremos relacionados a eventos específicos. A detecção de anomalias pode relatar um aumento acentuado em uma métrica positiva de Pedidos ou um aumento em uma métrica negativa de Rejeições, ou declínios em ambos, capturando pontos de dados estatisticamente relevantes para serem avaliados pela Análise de contribuição. Quando a anomalia estatística é identificada, a Análise de contribuição permite detalhar e avaliar variáveis relevantes de marketing e da campanha em todos os pontos de dados anômalos. Ela executa processos de aprendizado automático e de algoritmos avançados para avaliar associações que contribuíram para um pico ou declínio significativo. Esses cálculos são exibidos em visualizações interativas projetadas para apresentar diversas perspectivas que ajudam a responder por que algo aconteceu e o que fazer a respeito.

A Análise de contribuição ajuda a desenvolver uma narrativa para descrever por que ocorreu uma anomalia. E como responder a anomalias, capturando métricas relevantes e identificando pontos ocultos que fornecem um motivo geral para interações de público-alvo e interesses de clientes em tendência. Às vezes, é fácil visualizar e corrigir uma anomalia, como um pedido equivocado de 2000 caiaques. Outras vezes é complexo, como identificar uma tendência crescente ao longo de um período em uma região que reage apenas a uma campanha direcionada específica. Reunir os itens de contribuição nas métricas para várias dimensões e suas associações dá uma ideia geral das interações do público-alvo e ajuda a contextualizar os pontos de dados anômalos.

Estes são alguns casos de uso:

* Identificar o potencial de recomercialização monitorando as alterações na demanda do produto.
* Melhorar a experiência do cliente, respondendo aos interesses específicos do público-alvo.
* Identificar rápido os pedidos fraudulentos através de um relatório de pedidos fora dos limites.
* Proteger-se da espionagem corporativa, identificando usos e downloads excessivos.
* Monitore operações, como relatórios de tags JavaScript ausentes.

Após uma análise abrangente de uma anomalia, será gerado um Resumo das contribuições para os itens superiores de acordo com o total de ocorrências e a porcentagem dos valores de contribuição de cada item. A Pontuação de contribuição normalizada facilita comparações, contrastes e associações com outros itens de dimensão importantes.

## Tokens da análise de contribuição

Todos os clientes com direitos constituídos à Análise de contribuição podem executar Análises de contribuição completas um número limitado de vezes por mês no Analysis Workspace. A Análise de contribuição **exclui** clientes de produtos isolados (SiteCatalyst 15), clientes do Analytics Foundation e clientes do Analytics Select, que não têm direito à Análise de contribuição.

O número de execuções por empresa é limitado por tokens mensais gerados com base no produto do Adobe Analytics adquirido pela sua empresa. O número de execuções por empresa inclui a capacidade de restringir o acesso à Análise de contribuição para evitar o uso indevido do token.

## Perguntas frequentes

| Pergunta | Resposta |
| --- | --- |
| Por que a Adobe apresentou os tokens? | A Análise de contribuição é um dos recursos mais importantes do Adobe Analytics. Com um pequeno número de execuções completas por mês (em vez de apenas 3 dimensões para alguns produtos do Analytics), você pode ver o que a Análise de contribuição completa e ilimitada pode fazer por você. |
| Como funcionam os tokens na Análise de contribuição? Custa um token para carregar um projeto com uma Análise de contribuição já existente ou apenas ao executar uma nova? | Cada logon da empresa (não de cada usuário) recebe um certo número de tokens por mês, que permitem executar Análises de contribuição completas no Analysis Workspace.  Cada vez que uma nova Análise de contribuição for gerada, um token é pago. Carregar projetos com Análises de contribuição pré-executadas não custa um token. |
| Se os tokens da minha empresa acabaram e minha empresa deseja executar Análises de contribuição adicionais, o que fazer? | É possível atualizar para outro produto do Adobe Analytics, por exemplo do Standard (2 tokens mensais) para o Ultimate (20 tokens mensais). Não é possível comprar mais tokens. Você deve atualizar dentro da estrutura de pacotes existente. |
| Como restringir o acesso à Análise de contribuição? | Por padrão, somente os administradores têm acesso para executar Análises de contribuição. No entanto, os administradores podem conceder acesso a outros usuários criando um grupo de permissões no [Adobe Admin Console](https://experienceleague.adobe.com/pt-br/docs/analytics/admin/admin-console/home). Conceda permissão de uso da Análise de contribuição somente aos usuários com uma razão legítima para usá-la e que não abusarão de seu acesso. A permissão é chamada [!UICONTROL Análise de contribuição] em [!UICONTROL Ferramentas do conjunto de relatórios]. [Saiba mais](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-console/permissions/report-suite-tools) |
| Como posso saber a quantos tokens minha empresa tem direito por mês e quantos tokens minha empresa usou no mês atual? | Acesse [!UICONTROL Administrador] > [!UICONTROL Todos os administradores] > [!UICONTROL Página inicial das configurações da empresa] > [!UICONTROL Exibir níveis de acesso ao recurso]. Procurar em<ul><li>Análise de contribuição: número de tokens de uso mensais</li><li>Análise de contribuição: número de tokens de uso usados neste mês</li></ul> |

## Direitos de Detecção de anomalias e Análise de contribuição

Abaixo há uma lista dos direitos de Detecção de anomalias e Análise de contribuição no Analysis Workspace.

<table id="table_5C9B7E4AE82640B5A913519E576889B5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Direitos constituídos do Adobe Analytics </th> 
   <th colname="col2" class="entry"> Detecção de anomalias </th> 
   <th colname="col3" class="entry"> Análise de contribuição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Foundation </p> </td> 
   <td colname="col2"> <p>Apenas granularidade diária </p> </td> 
   <td colname="col3" colsep="1"> <p>Sem tokens </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://business.adobe.com/products/analytics/compare-adobe-analytics-packages.html?promoid=B4XQ3X7G&amp;mv=other"  >Select</a> </p> </td> 
   <td colname="col2"> <p>Apenas granularidade diária </p> </td> 
   <td colname="col3"> <p>Sem tokens </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://business.adobe.com/products/analytics/compare-adobe-analytics-packages.html?promoid=91BF51TR&amp;mv=other"  >Prime</a> </p> </td> 
   <td colname="col2"> <p>Sim </p> </td> 
   <td colname="col3"> <p>10 tokens por mês </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://business.adobe.com/products/analytics/compare-adobe-analytics-packages.html?promoid=8N4B5F1V&amp;mv=other"  > Ultimate</a> </p> </td> 
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
