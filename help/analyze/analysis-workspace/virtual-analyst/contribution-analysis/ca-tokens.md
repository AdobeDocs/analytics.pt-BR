---
description: Use a Análise de contribuição para identificar anomalias e correlações estatísticas nos dados.
title: Visão geral da análise de contribuição
uuid: 2bd295b0-c5ce-4443-86af-024efd20c021
feature: Ferramentas AI
role: Business Practitioner, Administrator
exl-id: 86fc8696-90a8-4626-b1c7-6413d3f8a648
translation-type: tm+mt
source-git-commit: 6588896cd47e15127b1b1d0a2d229e0ed2dbaaaa
workflow-type: tm+mt
source-wordcount: '1164'
ht-degree: 91%

---

# Visão geral da análise de contribuição

A Análise de contribuição revela padrões ocultos nos dados para explicar anomalias estatísticas e identificar correlações por trás das ações inesperadas do cliente, dos valores fora do limite e dos picos ou declínios repentinos nas métricas selecionadas em segmentos convergentes do público-alvo.

Algo aconteceu? Por quê? Seu relatório de Detecção de anomalias mostra um pico incomum em pedidos e você quer saber por quê. O que aconteceu fora do comum? Quem é responsável por qual campanha ou indicação? Algo se tornou viral? Quais são os fatores específicos que contribuíram para essa anomalia? E talvez o mais importante: como posso obter informações importantes sobre meu cliente e repetir esse desempenho? (Ou no caso de um declínio em uma métrica ou um aumento em uma métrica negativa, como evitar isso no futuro?)

A Análise de contribuição ajuda a avaliar seus dados imediatamente para identificar a causa de uma anomalia. Ela analisa o que contribuiu para uma anomalia em segundos, o que antes levaria semanas, fornecendo padrões para os segmentos do público-alvo e ajudando a desenvolver uma narrativa para interações com os clientes. Você pode empregar a Análise de contribuição de forma estratégica para identificar e obter associações significativas com o objetivo de desenvolver novos segmentos do público-alvo, ou usá-la taticamente para identificar atividade fora do comum ou fraudulenta que aciona um alerta.

A [Detecção de anomalias](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) identifica picos de dados e declínios estatísticos extremos com base em métricas selecionadas e segmentos de público-alvo selecionados. Ela define uma norma histórica com base em um período de treinamento e, em seguida, representa deslocamentos extremos relacionados a eventos específicos. Ela pode relatar um aumento acentuado em uma métrica positiva de Pedidos ou um aumento em uma métrica negativa de Rejeições, ou declínios em ambos, capturando pontos de dados estatisticamente relevantes para serem avaliados pela Análise de contribuição. Quando a anomalia estatística é identificada, a Análise de contribuição permite detalhar e avaliar variáveis relevantes de marketing e da campanha em todos os pontos de dados anômalos. Ela executa processos de aprendizado automático e de algoritmos avançados para avaliar associações que contribuíram para um pico ou declínio significativo. Esses cálculos são exibidos em visualizações interativas projetadas para apresentar diversas perspectivas que ajudam a responder por que aconteceu uma anomalia e o que deve ser feito.

A Análise de contribuição ajuda a elaborar uma narrativa para descrever por que uma anomalia aconteceu e como reagir, obtendo métricas relevantes e identificando pontos ocultos que apresentam uma razão geral para as interações do público-alvo e as tendências dos interesses dos clientes. Às vezes, é fácil visualizar e corrigir uma anomalia, como um pedido equivocado de 2000 caiaques. Outras vezes é complexo, como identificar uma tendência crescente ao longo de um período em uma região que reage apenas a uma campanha direcionada específica. Reunir os itens de contribuição nas métricas para várias dimensões e suas associações dá uma ideia geral das interações do público-alvo e ajuda a contextualizar os pontos de dados anômalos.

Estes são alguns casos de uso:

* Identificar o potencial de recomercialização monitorando as alterações na demanda do produto.
* Melhorar a experiência do cliente, respondendo aos interesses específicos do público-alvo.
* Identificar rápido os pedidos fraudulentos através de um relatório de pedidos fora dos limites.
* Proteger-se da espionagem corporativa, identificando usos e downloads excessivos.
* Monitorar operações, por exemplo, através do relatório de tags de javascript ausentes.

Após uma análise abrangente de uma anomalia, será gerado um Resumo das contribuições para os itens superiores de acordo com o total de ocorrências e a porcentagem dos valores de contribuição de cada item. A Pontuação de contribuição normalizada facilita comparações, contrastes e associações com outros itens de dimensão importantes.

## Tokens da análise de contribuição - visão geral {#section_3EF8D2BBCE6E4C309D753BCF04A453D0}

>[!IMPORTANT]
>
>A Análise de contribuição foi removida do conjunto de recursos do Reports &amp; Analytics e agora está disponível apenas no Analysis Workspace.

Todos os clientes com direitos constituídos à Análise de contribuição podem executar Análises de contribuição completas um número limitado de vezes por mês no Analysis Workspace. Isso **exclui** clientes pontuais de produtos (SiteCatalyst 15), clientes da Analytics Foundation e clientes Analytics Select que não têm acesso à Análise de contribuição.

O número de execuções por empresa é limitado por tokens mensais gerados com base no produto do Adobe Analytics adquirido pela sua empresa. Isso inclui a capacidade de restringir o acesso à Análise de contribuição para evitar o uso inadequado de tokens.

## Perguntas frequentes {#section_11D0431AD2014B96AB9561CA66A367CE}

| Pergunta | Resposta |
| --- | --- |
| Por que a Adobe apresentou os tokens? | A Análise de contribuição é um dos recursos mais importantes do Adobe Analytics. Com um pequeno número de execuções completas por mês (em vez de apenas 3 dimensões para alguns produtos do Analytics), você pode ter uma ideia melhor do que a Análise de contribuição completa e ilimitada pode fazer. |
| Como a tokenização funciona na Análise de contribuição? Custa um token para carregar um projeto com uma Análise de contribuição já existente ou apenas ao executar uma nova? | Cada logon da empresa (não de cada usuário) recebe um certo número de tokens por mês, que permitem executar Análises de contribuição completas no Analysis Workspace.  Cada vez que uma nova Análise de contribuição for gerada, um token é pago. Carregar projetos com Análises de contribuição pré-executadas não custa um token. |
| Os tokens se aplicam à Análise de contribuição no Reports &amp; Analytics? | Não. A Análise de contribuição não é mais oferecida no Reports &amp; Analytics a partir de abril de 2018. |
| Se os tokens da minha empresa acabaram e ainda queremos executar Análises de contribuição adicionais, o que podemos fazer? | É possível atualizar para outro produto do Adobe Analytics, por exemplo do Standard (2 tokens mensais) para o Ultimate (20 tokens mensais). Não é possível apenas comprar mais tokens, é necessário atualizar dentro da estrutura de pacotes existente. |
| Como restringir o acesso à Análise de contribuição? | Por padrão, somente os administradores têm acesso para executar Análises de contribuição. No entanto, os administradores podem conceder acesso a outros usuários criando um grupo de permissões no [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html). É importante dar permissão de uso para a Análise de contribuição somente aos usuários com uma razão legítima para usá-la e que não abusarão de seu acesso. A permissão é chamada [!UICONTROL Análise de contribuição] em [!UICONTROL Ferramentas do conjunto de relatórios]. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/report-suite-tools.html) |
| Como posso saber a quantos tokens minha empresa tem direito por mês e quantos já usamos no mês atual? | Vá para [!UICONTROL Admin] > [!UICONTROL Todos os Admin] >[!UICONTROL Página inicial das configurações da empresa] >[!UICONTROL Exibir níveis de acesso a recursos]. Procure debaixo<ul><li>Análise de contribuição: número de tokens de uso mensais</li><li>Análise de contribuição: número de tokens de uso usados neste mês</li></ul> |

## Direitos de Detecção de anomalias e Análise de contribuição {#section_9278D58F21A840AA9B1ED1BD07A1EF0A}

Abaixo há uma lista dos direitos de Detecção de anomalias e Análise de contribuição no Analysis Workspace.

>[!IMPORTANT]
>
>A Detecção de anomalias e a Análise de contribuição foram removidas do conjunto de recursos do Reports &amp; Analytics e agora estão disponíveis apenas por meio da Analysis Workspace. Observe que os clientes do Adobe Analytics Select e do Adobe Analytics Foundation só têm acesso à Detecção de anomalias de “granularidade diária” no Workspace.

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
   <td colname="col1"> <p><a href="https://www.adobe.com/br/data-analytics-cloud/analytics/select.html?promoid=B4XQ3X7G&amp;mv=other"  >Select</a> </p> </td> 
   <td colname="col2"> <p>Apenas granularidade diária </p> </td> 
   <td colname="col3"> <p>Sem tokens </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.adobe.com/br/data-analytics-cloud/analytics/prime.html?promoid=91BF51TR&amp;mv=other"  >Prime</a> </p> </td> 
   <td colname="col2"> <p>Sim </p> </td> 
   <td colname="col3"> <p>10 tokens por mês </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.adobe.com/br/data-analytics-cloud/analytics/ultimate.html?promoid=8N4B5F1V&amp;mv=other"  > Ultimate</a> </p> </td> 
   <td colname="col2"> <p>Sim </p> </td> 
   <td colname="col3"> <p>20 tokens por mês </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>+Predictive Workbench </p> </td> 
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
   <td colname="col1"> <p>Premium (Complete, <a href="https://www.adobe.com/br/data-analytics-cloud/analytics/predictive-intelligence.html"  >Predictive Intelligence</a>) </p> </td> 
   <td colname="col2"> <p>Sim </p> </td> 
   <td colname="col3"> <p>Tokens ilimitados </p> </td> 
  </tr> 
 </tbody> 
</table>
