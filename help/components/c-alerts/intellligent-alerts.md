---
description: O novo sistema de Alertas inteligentes permite um controle mais detalhado dos alertas e integra a detecção de anomalias ao sistema de alertas.
title: Alertas inteligentes
uuid: ac8c9710-d245-46e9-b906-32d3bb0013c0
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Alertas inteligentes

O novo sistema de Alertas inteligentes permite um controle mais detalhado dos alertas e integra a detecção de anomalias ao sistema de alertas.

## Visão geral {#section_6AC8CA81DEA94E99B0F192B60D0FDF03}

>[!IMPORTANT]
>
>Os alertas inteligentes estão disponíveis somente para clientes do Adobe [!DNL Analytics] Prime e do Adobe [!DNL Analytics] Ultimate.

O novo Criador de alertas e o Gerenciador de alertas substituem a funcionalidade de alertas existente na Adobe [!DNL Analytics]. Os Alertas inteligentes permitem

* Criar alertas com base em anomalias (limites de 90%, 95%, 99%, 99,75% e 99,9%; % de alteração; acima/abaixo).
* Visualizar a frequência de disparo de um alerta.
* Enviar alertas por email ou SMS com links para projetos do Analysis Workspace gerados automaticamente.
* Criar alertas “empilhados”, capazes de capturar várias métricas de uma só alerta.

Os componentes do novo sistema de alertas incluem: o Criador de alertas, o Gerenciador de alertas, a Visualização de alertas e um melhor acesso ao contexto para criar alertas. A interface do usuário do sistema de alerta anterior não estará mais disponível, mas os alertas serão migrados. Alguns recursos de alerta de legado [não estarão mais disponíveis](https://marketing.adobe.com/resources/help/pt_BR/sc/user/deprecated_alerts.html).

Há quatro maneiras de acessar o Criador de alertas:

* Usando o seguinte atalho no Analysis Workspace:

   `ctrl (or cmd) + shift + a`
* Acessando diretamente o Criador de alertas: **[!UICONTROL Workspace]** &gt; **[!UICONTROL Componentes]** &gt; **[!UICONTROL Novo alerta]**.
* Selecionando um ou mais itens de linha da tabela de forma livre, clicando com o botão direito do mouse e selecionando **[!UICONTROL Criar alerta a partir da seleção]**. Isso abrirá o Criador de alertas e pré-preencherá o criador com as métricas e filtros apropriados aplicados a partir da tabela. Você pode editar o alerta, se necessário.

   ![](assets/create-alert-from-selection.png)

* A partir de um relatório do [!UICONTROL Reports &amp; Analytics], acessando **[!UICONTROL Mais]** &gt; **[!UICONTROL Adicionar alerta]**. Isso abrirá o novo Criador de alertas e pré-preencherá o criador com as métricas e filtros apropriados aplicados a partir do relatório. Você pode editar o alerta, se necessário.

   ![](assets/add-alert.png)

## Perguntas frequentes: Como os alertas são calculados e acionados  {#section_1F3B1DAF21784306953B49AAD4C3DCAB}

Os limites % são desvios padrão. Por exemplo, 95% = 2 desvios padrão e 99% = 3 desvios padrão. Dependendo da granularidade de tempo escolhida,  [modelos diferentes](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md) são usados para calcular o quão distante (quantos desvios padrão) cada ponto de dados está da norma. Se você definir um limite mais baixo (como 90%), receberá mais anomalias se definir um limite mais alto (99%), Os limites 99,75% e 99,99% foram criados especificamente para a granularidade horária, de forma que não tantas anomalias não sejam acionadas.

<table id="table_B3AA85E1DE3543DCA34966A52E3CE4AB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pergunta </th> 
   <th colname="col2" class="entry"> Resposta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>P: Até que ponto a detecção de anomalias dos alertas vai para determinar anomalias de dados?</b> </p> </td> 
   <td colname="col2"> <p>O período de treinamento varia com base na granularidade selecionada. Consulte Técnicas estatísticas usadas na <a href="/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md">Detecção de anomalias</a> para obter mais detalhes. Aqui está um resumo: </p> 
    <ul id="ul_4F8C2A41F06C498DBF5E7AE5DE803773"> 
     <li id="li_E246091A3F1E484C8444AF4052FCA784">Mensalmente = 15 meses + mesmo intervalo do ano passado </li> 
     <li id="li_CC014FB38AE1492B9647E990C29BFB3C">Semanalmente = 15 semanas + mesmo intervalo do ano passado </li> 
     <li id="li_2517EE2097534324BE9C1B54CD181A62">Diariamente = 35 dias + mesmo intervalo do ano passado </li> 
     <li id="li_710BC8B009354542AA4962A59A646099">De hora em hora = 336 horas </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: Se eu desejar ser alertado sobre apenas uma baixa no comportamento ou apenas um aumento, posso usar o recurso de anomalia ou preciso usar o valor absoluto?</b> </p> </td> 
   <td colname="col2"> <p>Usar o valor absoluto ainda acionaria alertas de baixas e de aumentos. Não é possível isolar alertas apenas para baixas ou aumentos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: Posso configurar os alertas para serem acionados apenas durante determinadas horas do dia (como horário comercial ou não comercial)? </b> </p> </td> 
   <td colname="col2"> <p>Atualmente, não. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>P: Posso obter uma tabela dos "valores esperados" que contém a linha pontilhada, ou algum tipo de saída do que são esses valores? </b> </p> </td> 
   <td colname="col2"> <p>Não na Workspace, mas é possível no Report Builder (assista a este vídeo sobre a <a href="https://www.youtube.com/watch?v=-a-8W6GQZnU"  >Detecção de anomalias no Report Builder </a>). </p> <p>Lembre-se de que o Report Builder usa métodos de detecção de anomalias menos sofisticados. Ele usa um período fixo de treinamento de 30 dias, intervalo fixo de 95% e é semelhante à <a href="https://marketing.adobe.com/resources/help/pt_BR/reference/anomaly.html"  ><span class="uicontrol"></span>Detecção de anomalias do Reports &amp; Analytics </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

