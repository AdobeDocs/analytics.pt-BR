---
description: 'null'
title: Visão geral da análise de contribuição
uuid: 2bd295b0-c5ce-4443-86af-024efd20c021
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Visão geral da análise de contribuição

A Análise de contribuição revela padrões ocultos nos dados para explicar anomalias estatísticas e identificar correlações por trás das ações inesperadas do cliente, dos valores fora do limite e dos picos ou declínios repentinos nas métricas selecionadas em segmentos convergentes do público.

Algo aconteceu? Por quê? Seu relatório de Detecção de anomalias mostra um pico incomum em pedidos e você quer saber por quê. O que aconteceu fora do comum? Quem é responsável por qual campanha ou indicação? Algo se tornou viral? Quais são os fatores específicos que contribuíram para essa anomalia? E talvez o mais importante: como posso obter informações importantes sobre meu cliente e repetir esse desempenho? (Ou no caso de um declínio em uma métrica ou um aumento em uma métrica negativa, como evitar isso no futuro?)

A Análise de contribuição ajuda a avaliar seus dados imediatamente para identificar a causa de uma anomalia. Ela analisa o que contribuiu para uma anomalia em segundos, o que antes levaria semanas, fornecendo padrões para os segmentos do público-alvo e ajudando a desenvolver uma narrativa para interações com os clientes. Você pode empregar a Análise de contribuição de forma estratégica para identificar e obter associações significativas com o objetivo de desenvolver novos segmentos do público-alvo, ou usá-la taticamente para identificar atividade fora do comum ou fraudulenta que aciona um alerta.

A [Detecção de anomalias](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) identifica picos de dados e declínios estatísticos extremos com base em métricas selecionadas e segmentos de público selecionados. Ela define uma norma histórica com base em um período de treinamento e, em seguida, representa deslocamentos extremos relacionados a eventos específicos. Ela pode relatar um aumento acentuado em uma métrica positiva de Pedidos ou um aumento em uma métrica negativa de Rejeições, ou declínios em ambos, capturando pontos de dados estatisticamente relevantes para serem avaliados pela Análise de contribuição. Quando a anomalia estatística é identificada, a Análise de contribuição permite detalhar e avaliar variáveis relevantes de marketing e da campanha em todos os pontos de dados anômalos. Ela executa processos de aprendizado automático e de algoritmos avançados para avaliar associações que contribuíram para um pico ou declínio significativo. Esses  cálculos são exibidos em visualizações interativas projetadas para apresentar diversas perspectivas que ajudam a responder por que aconteceu uma anomalia e o que deve ser feito.

A Análise de contribuição ajuda a elaborar uma narrativa para descrever por que uma anomalia aconteceu e como reagir, obtendo métricas relevantes e identificando pontos ocultos que apresentam uma razão geral para as interações do público-alvo e as tendências dos interesses dos clientes. Às vezes, é fácil visualizar e corrigir uma anomalia, como um pedido equivocado de 2000 caiaques. Outras vezes é complexo, como identificar uma tendência crescente ao longo de um período em uma região que reage apenas a uma campanha direcionada específica. Reunir os itens de contribuição nas métricas para várias dimensões e suas associações dá uma ideia geral das interações do público-alvo e ajuda a contextualizar os pontos de dados anômalos.

Veja algumas ideias:

* Identificar o potencial de recomercialização, monitorando as alterações na demanda do produto.
* Melhorar a experiência do cliente, respondendo aos interesses específicos do público.
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

<table id="table_357775E5058644099E26B15A6790E8AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pergunta </th> 
   <th colname="col2" class="entry"> Resposta </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Por que a Adobe apresentou os tokens? </b> </p> </td> 
   <td colname="col2"> <p>A Análise de contribuição é uma das capacidades mais importantes do Adobe Analytics desde seu lançamento em 2015. Com um pequeno número de execuções completas por mês (em vez de apenas 3 dimensões para alguns produtos do Analytics), você pode ter uma ideia melhor do que a Análise de contribuição completa e ilimitada pode fazer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Como a tokenização funciona na Análise de contribuição? Custa um token para carregar um projeto com uma Análise de contribuição já existente ou apenas ao executar uma nova?</b> </p> </td> 
   <td colname="col2"> <p>Cada logon da empresa (não de cada usuário) recebe um certo número de tokens por mês, que permitem executar Análises de contribuição completas no Analysis Workspace. </p> <p>Cada vez que uma nova Análise de contribuição for gerada, um token é pago. Carregar projetos com Análises de contribuição pré-executadas não custa um token. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Os tokens se aplicam à Análise de contribuição no Reports &amp; Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Não. A Análise de contribuição não é mais oferecida no Reports &amp; Analytics a partir da versão de abril de 2018. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Se os tokens da minha empresa acabaram e ainda queremos executar Análises de contribuição adicionais, o que podemos fazer?</b> </p> </td> 
   <td colname="col2"> <p>É possível atualizar para outro produto do Adobe Analytics, por exemplo do Standard (2 tokens mensais) para o Ultimate (20 tokens mensais). Não é possível apenas comprar mais tokens, é necessário atualizar dentro da estrutura de pacotes existente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Como restringir o acesso à Análise de contribuição?</b> </p> </td> 
   <td colname="col2"> <p>Por padrão, somente os administradores têm acesso para executar Análises de contribuição, mas os administradores podem conceder acesso a outros usuários criando um grupo de permissões no <a href="https://docs.adobe.com/content/help/pt-BR/core-services/interface/manage-users-and-products/admin-getting-started.html"  > Admin Console </a>. É importante dar permissão de uso para a Análise de contribuição somente aos usuários com uma razão legítima para usá-la e que não abusarão de seu acesso. </p> <p>A permissão se chama “Análise de contribuição” e está em <span class="ignoretag"><span class="uicontrol">Analytics</span> &gt; <span class="uicontrol">Admin</span> &gt; <span class="uicontrol">User Management</span> &gt; <span class="uicontrol">Editar grupos</span> &gt; <span class="uicontrol">Editar acessos a relatórios</span> &gt; <span class="uicontrol">Personalizar ferramentas do conjunto de relatórios</span> &gt; <span class="uicontrol">Ferramentas e relatórios</span></span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Como posso saber a quantos tokens minha empresa tem direito por mês e quantos já usamos no mês atual?</b> </p> </td> 
   <td colname="col2"> <p>Acesse <span class="ignoretag"><span class="uicontrol">Admin</span> &gt; <span class="uicontrol">Configurações da empresa</span> &gt; <span class="uicontrol">Exibir níveis de acesso a recursos</span></span>. Existem 2 itens novos nesta página: </p> <p><img placement="break"  src="assets/ca_access_level.png" id="image_16012FE1162C485EA768D175F43D7563" width="500px" /> </p> </td> 
  </tr> 
 </tbody> 
</table>


## Direitos de Detecção de anomalias e Análise de contribuição {#section_9278D58F21A840AA9B1ED1BD07A1EF0A}

Abaixo há uma lista dos direitos de Detecção de anomalias e Análise de contribuição no Analysis Workspace.

>[!IMPORTANT]
>
>A Detecção de anomalias e a Análise de contribuição foram removidas do conjunto de recursos do Reports &amp; Analytics e agora estão disponíveis somente no Analysis Workspace. Observe que os clientes do Adobe Analytics Select e do Adobe Analytics Foundation só têm acesso à Detecção de anomalias de “granularidade diária” no Workspace.

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
   <td colname="col1"> <p>+Worbench preditivo </p> </td> 
   <td colname="col2"> <p>Sim </p> </td> 
   <td colname="col3"> <p>Tokens ilimitados </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Padrão </p> 
    <ul id="ul_73D52020793B44868C9CE0F90893075D"> 
     <li id="li_21EE0871C87E43C8B781219B2BA0FA74">Adobe Analytics Core </li> 
     <li id="li_AB3593200F33439BAEE8FEB13CAE57F4">Adobe Analytics OD </li> 
     <li id="li_2B7D625519BC4A4CB598C95F15D3029B">Adobe Analytics MA </li> 
    </ul> </td> 
   <td colname="col2"> <p>Sim </p> </td> 
   <td colname="col3"> <p>2 tokens por mês </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium (360, Atribuição) </p> </td> 
   <td colname="col2"> <p>Sim </p> </td> 
   <td colname="col3"> <p>2 tokens por mês </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium (Completo, <a href="https://www.adobe.com/br/data-analytics-cloud/analytics/predictive-intelligence.html"  >Inteligência preditiva</a>) </p> </td> 
   <td colname="col2"> <p>Sim </p> </td> 
   <td colname="col3"> <p>Tokens ilimitados </p> </td> 
  </tr> 
 </tbody> 
</table>
