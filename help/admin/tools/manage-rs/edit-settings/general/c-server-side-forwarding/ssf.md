---
description: O encaminhamento pelo lado do servidor foi projetado para clientes que desejam compartilhar dados do Analytics com outras soluções corporativas CX em tempo real. Quando ativado, o encaminhamento pelo lado do servidor também permite que o Analytics envie dados para outras soluções da CX Enterprise e que essas soluções enviem dados para o Analytics durante o processo de coleta de dados.
solution: Analytics
title: Visão geral do encaminhamento pelo lado do servidor
feature: Report Suite Settings
exl-id: e3cd72d2-9588-4770-a7c2-64b13a1e9519
role: Admin
TQID: https://experienceleague.adobe.com/O03-5Ovxy3Lq-LZjPOseTpOlCXaS1kwD8n2ZM1yJuxY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 887
ht-degree: 59%

---

# Visão geral do encaminhamento pelo lado do servidor

O encaminhamento pelo lado do servidor foi projetado para clientes que desejam compartilhar dados do Analytics com outras soluções corporativas CX em tempo real. Quando ativado, o encaminhamento pelo lado do servidor também permite que o Analytics envie dados para outras soluções da CX Enterprise e que essas soluções enviem dados para o Analytics durante o processo de coleta de dados.

O encaminhamento pelo lado do servidor aprimora a coleta de dados porque:

* Reduz as chamadas de da página. Com o encaminhamento pelo lado do servidor, os clientes do [!DNL Audience Manager] não precisam mais usar o DIL para a coleta de dados porque estão sendo encaminhados do Analytics. Remover o DIL significa eliminar uma chamada `"/event"`. Menos chamadas ajuda a melhorar o tempo de carregamento da página, o que resulta em uma melhor experiência do cliente no site.
* Permite que você aproveite o compartilhamento de dados entre as soluções CX Enterprise.
* Está em conformidade com as práticas recomendadas para a implementação e implantação do código do Audience Manager.

>[!TIP]
>
>Os clientes atuais do Audience Manager que utilizam o Analytics devem migrar para o encaminhamento pelo lado do servidor. Os novos clientes do Adobe Analytics e do Audience Manager devem implementar o encaminhamento pelo lado do servidor (em vez do DIL) como o método de transferência e coleta de dados padrão.

>[!IMPORTANT]
>Para atender à regulamentação de conformidade de cookies da UE, controladores de dados (clientes do Analytics) agora têm a opção de restringir dados de pré-consentimento no Adobe Analytics e evitar que sejam encaminhados pelo lado do servidor para o Adobe Audience Manager. Uma nova variável de contexto de implementação permite sinalizar ocorrências onde o consentimento não foi recebido. A variável, quando definida, evita que essas ocorrências sejam enviadas para o Adobe Audience Manager até que o consentimento seja recebido. Para obter mais informações, consulte [Conformidade com o GDPR_ePrivacy e o encaminhamento pelo lado do servidor](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-gdpr.md).

Para entender onde sua organização está em termos de implementação do encaminhamento pelo lado do servidor, passe por essas etapas de validação:

## ![step1_icon.png imagem](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/assets/step1_icon.png) Verificar implementação do serviço ECID

Verifique se o serviço da Experience Cloud ID (ECID) está implementado, ao inspecionar a [solicitação de rastreamento do Analytics](https://experienceleague.adobe.com/docs/id-service/using/implementation/test-verify.html?lang=pt-BR).

Na guia Solicitação, verifique se um valor de ECID está definido. Isso indica que o Serviço de identidade está implementado corretamente, o que é um pré-requisito para o encaminhamento pelo lado do servidor.

* Se você encontrar um valor ECID, avance para a etapa 2.
* Se você não vir um valor de ECID, [implemente o Serviço de identidade](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html?lang=pt-BR) antes de prosseguir para a etapa 2.

## ![step2_icon.png imagem](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/assets/step2_icon.png) Verificar a versão de implementação do encaminhamento pelo lado do servidor

Verifique se você já tem uma versão do encaminhamento pelo lado do servidor implementada, [inspecionando a solicitação de rastreamento do Analytics](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-verify.md).

Na guia &quot;Resposta&quot;, verifique se a resposta contém dados do Audience Manager. Se você encontrar:

* Uma **resposta JSON do Audience Manager que inclui itens como &quot;postbacks&quot; ou &quot;dcs_region&quot;**: você já possui alguma forma de encaminhamento pelo lado do servidor habilitada. Prossiga para a etapa 3.
* O **&quot;status&quot;:&quot;SUCCESS&quot;**: você tem o módulo de Gerenciamento de público-alvo implementado, mas o encaminhamento pelo lado do servidor não foi configurado corretamente. Prossiga para a etapa 3.
* Uma imagem **2 x 2**: você não tem encaminhamento pelo lado do servidor ou o Módulo de Gerenciamento de Público-Alvo implementado. Para corrigir isso:

   * **Clientes do Adobe Audience Manager com DIL**: coordene os 2 seguintes itens em conjunto:

      1. Remova o código DIL e instale o código de página do [Módulo de Gerenciamento de Público-Alvo](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html?lang=pt-BR).
      1. Ative o encaminhamento pelo lado do servidor na interface do administrador do Analytics, conforme descrito na etapa 3. Ativar essa configuração antes de remover o código DIL duplicará os dados e criará chamadas de servidor faturadas adicionais para o Audience Manager.

   * **Novos(as) clientes do Adobe Audience Manager**: instale o código de página do [Módulo de gerenciamento de público-alvo](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html?lang=pt-BR) e avance para a etapa 3. Os dados não serão enviados ao Audience Manager até que o encaminhamento pelo lado do servidor seja ativado na etapa 3.

## ![step3_icon.png imagem](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/assets/step3_icon.png) Verificar a implementação do encaminhamento pelo lado do servidor do conjunto de relatórios

Verifique se o encaminhamento pelo lado do servidor está implementado no nível do conjunto de relatórios, em vez da abordagem do servidor de rastreamento herdado.

O encaminhamento pelo lado do servidor no nível do conjunto de relatórios é recomendado em relação à abordagem do servidor de rastreamento herdada, pois você pode controlar em um nível mais fino quais dados são compartilhados do Analytics. Também é um pré-requisito para essa integração do Audience Analytics.

Acesse **Analytics** > **Administração** > **Conjuntos de relatórios** > (selecione o **conjunto de relatórios**) > **Editar configurações** > **Geral** > **Encaminhamento pelo lado do servidor**. Se a caixa de seleção estiver:

* **Inativo** (Você não pode fazer uma seleção ou o menu não existe): você não tem os conjuntos de relatórios selecionados mapeados para uma ID de organização. Entre em contato com o Atendimento ao cliente para verificar se o conjunto de relatórios está mapeado corretamente.
* **Desabilitado**: o novo encaminhamento pelo lado do servidor não está ativado. Leia o conteúdo na página e prossiga com a ativação do recurso.
* **Habilitado**: você está provisionado para o novo encaminhamento pelo lado do servidor. Você também pode configurar essa integração do Audience Analytics.

>[!NOTE]
>
>Os dados não serão exibidos em outras soluções CX Enterprise, como [Audience Manager](https://docs.adobe.com/content/help/pt-BR/experience-cloud/user-guides/home.html) ou [Públicos-alvo](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=pt-BR), até que todas as 3 etapas sejam concluídas. Uma vez habilitado, levará várias horas para que essas configurações entrem em vigor.
