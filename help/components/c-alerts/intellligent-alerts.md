---
description: O sistema de Alertas inteligentes permite um controle mais detalhado dos alertas e integra a detecção de anomalias ao sistema de alertas.
title: Alertas inteligentes
feature: Alerts
exl-id: 1b23211e-7632-4b33-a27d-c58b3bbbbab1
source-git-commit: a979fc8787fa96f8fa8317996ac66341a6f54354
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 93%

---

# Alertas inteligentes

O sistema de Alertas inteligentes permite um controle mais detalhado dos alertas e integra a detecção de anomalias ao sistema de alertas.

Veja um vídeo com uma visão geral:

>[!VIDEO](https://video.tv.adobe.com/v/25446/?quality=12)

## Visão geral {#section_6AC8CA81DEA94E99B0F192B60D0FDF03}

>[!IMPORTANT]
>
>Os Alertas inteligentes estão disponíveis somente para clientes do Adobe [!DNL Analytics] Prime e do Adobe [!DNL Analytics] Ultimate.

Os Alertas inteligentes permitem

* Criar alertas com base em anomalias (limites de 90%, 95%, 99%, 99,75% e 99,9%; % de alteração; acima/abaixo).
* Visualizar a frequência de disparo de um alerta.
* Enviar alertas por email ou SMS com links para projetos do Analysis Workspace gerados automaticamente.
* Criar alertas “empilhados”, capazes de capturar várias métricas de um só alerta.

Os componentes do sistema de alertas incluem: o Criador de alertas, o Gerenciador de alertas, a Pré-visualização de alertas e acesso melhorado com contexto para criar alertas. A interface de usuário do sistema de alerta anterior não estará mais disponível, mas os alertas serão migrados. Alguns recursos legados de alerta [não estão mais disponíveis](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/alerts.html?lang=pt-BR).

Há três maneiras de acessar o Criador de alertas:

* Usando o seguinte atalho no Analysis Workspace:

  `ctrl (or cmd) + shift + a`
* Acessando diretamente o Criador de alertas: **[!UICONTROL Espaço de trabalho]** > **[!UICONTROL Componentes]** > **[!UICONTROL Novo alerta]** .
* Selecionando um ou mais itens de linha da tabela de forma livre, clicando com o botão direito do mouse e selecionando **[!UICONTROL Criar alerta a partir da seleção]**. Isso abrirá o Criador de alertas e pré-preencherá o criador com as métricas e filtros apropriados aplicados a partir da tabela. Você pode editar o alerta, se necessário.

  ![](assets/create-alert-from-selection.png)


## Perguntas frequentes: Como os alertas são calculados e acionados {#trigger}

Os limites % são desvios padrão. Por exemplo, 95% = 2 desvios padrão e 99% = 3 desvios padrão. Dependendo da granularidade de tempo escolhida, [modelos diferentes](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md) são usados para calcular a distância (a quantidade de desvios padrão) de cada ponto de dados em relação à norma. Se você definir um limite mais baixo (como 90%), receberá mais anomalias se definir um limite mais alto (99%), Os limites 99,75% e 99,99% foram criados especificamente para a granularidade horária, de forma que não tantas anomalias não sejam acionadas.

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
   <td colname="col2"> <p>O período de treinamento varia com base na granularidade selecionada. Consulte Técnicas estatísticas usadas na <a href="/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md">Detecção de anomalias</a> para obter mais detalhes. Aqui está um resumo: </p> 
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
   <td colname="col2"> <p>Não na Espaço de trabalho, mas é possível no Report Builder (assista a este vídeo sobre a <a href="https://experienceleague.adobe.com/docs/analytics-learn/tutorials/exporting/report-builder/anomaly-detection-in-report-builder.html?lang=pt-BR"  >Detecção de anomalias no Report Builder </a>). </p> <p>Lembre-se de que o Report Builder usa métodos de detecção de anomalias menos sofisticados. Ele usa um período fixo de treinamento de 30 dias, com intervalo fixo de 95%. </p> </td> 
  </tr> 
 </tbody> 
</table>
