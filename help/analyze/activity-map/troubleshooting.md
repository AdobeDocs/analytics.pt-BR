---
title: Solução de problemas de coleta de dados do Activity Map
description: Determine por que não é possível ver os dados do Activity Map em solicitações de imagem
feature: Activity Map
role: User, Admin
exl-id: 7f9e06ba-4040-483b-b18b-cdfe85bca486
TQID: 'https://experienceleague.adobe.com/gv0QMe3b8xe17THNCvDN0g7bPy73XdakcSsZYio8K5s'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: d40ce8ba-a8b5-4daa-9c46-16a4e57a022b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c1579802-ddd4-4214-8a91-97b2066abe11id: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 429
ht-degree: 16%

---

# Solução de problemas de coleta de dados do Activity Map

Se você não vir dados para dimensões do Activity Map, use esta página para ajudar a determinar por quê.

## Confirmar a coleta de dados usando o depurador

Primeiro, verifique se o AppMeasurement coleta corretamente os dados do Activity Map.

1. Baixe e instale a [Extensão do Chrome do Adobe CX Enterprise Debugger](https://experienceleague.adobe.com/en/docs/experience-platform/debugger/home).
2. Navegue até a página da Web e clique em um link.
3. Quando a página subsequente for carregada, abra o depurador. Confirme se você vê as variáveis de dados de contexto do Activity Map agrupadas entre `activitymap.` e `.activitymap`:

## Possíveis motivos pelos quais os dados do Activity Map não estão presentes

Verifique cada um dos seguintes itens para garantir que os componentes do Activity Map estejam presentes:

* **Versão do AppMeasurement**: o Activity Map tem suporte na v1.6 e posterior. Muitos problemas de caso de borda são resolvidos ao atualizar para a versão estável mais recente do AppMeasurement.
* **Módulo do Activity Map**: verifique se o módulo `AppMeasurement_Module_Activity_Map` está presente no arquivo `AppMeasurement.js`. Se sua implementação usar o Adobe Experience Platform para coletar dados, verifique se **[!UICONTROL Habilitar ClickMap]** está marcado ao configurar a extensão do Analytics em **[!UICONTROL Rastreamento de link]**.
* **O `s_sq` cookie**: o Activity Map depende do cookie `s_sq` para a coleta de dados.
   * Verifique se a variável `cookieDomainPeriods` está definida corretamente, especialmente para domínios regionais como `*.co.uk` ou `*.co.jp`.
   * Verifique se a variável `linkInternalFilters` está definida com os valores desejados. Se um link clicado não corresponder aos filtros internos, a Activity Map o considerará um link de saída e não coletará dados.
* **Sobreposição do Activity Map em execução**: o AppMeasurement não rastreia dados de cliques da sua página da Web quando a sobreposição do Activity Map está habilitada.

Exibe os parâmetros do navegador que não são compatíveis com a utilização do Activity Map. A Adobe recomenda desabilitar essas configurações.

## Chrome

![](assets/Chrome1.png)

![](assets/Chrome2.png)

![](assets/Chrome3.png)

## Firefox

![](assets/Firefox.png)

## Safari

![](assets/Safari1.png)

![](assets/Safari2.png)

## Internet Explorer

![](assets/IE1.png)


**Validação**

Interaja com chamadas usando a guia Rede do Developer Console:

1. Carregue o script Development Launch no site.
1. Ao clicar em Elementos, procure por “/ee” na guia Rede

Adobe Experience Platform Debugger:

1. Baixe e instale o [Adobe Experience Platform Debugger](https://chromewebstore.google.com/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob).
1. Acesse [!UICONTROL Logs] > [!UICONTROL Edge] > [!UICONTROL Conectar ao Edge].

* **A chamada interativa não está sendo acionada na guia Rede**: A coleta de dados de cliques em uma chamada de coleta, filtre com `"/ee"` ou `"collect?"`.
* **Não há Exibição de Carga para a chamada de coleta**: a chamada de coleta foi projetada de forma que o rastreamento não afete a navegação para outros sites, portanto, o recurso de descarregamento do documento é aplicável para as chamadas de coleta. Esse recurso não afetará sua coleção de dados, mas se você precisar validar na página, adicione `target="_blank"` ao respectivo elemento. O link é aberto em uma nova guia.
