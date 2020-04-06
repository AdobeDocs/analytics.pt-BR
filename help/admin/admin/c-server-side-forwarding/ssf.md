---
description: O encaminhamento pelo lado do servidor foi projetado para clientes que desejam compartilhar dados do Analytics em outras Soluções da Experience Cloud em tempo real. Quando habilitado, o encaminhamento pelo lado do servidor também permite que o Analytics envie dados para outras soluções da Experience Cloud e que essas soluções enviem dados para o Analytics durante o processo de coleta de dados.
solution: Audience Manager
title: Visão geral do encaminhamento pelo lado do servidor
uuid: 22ddbde5-6805-4eba-8f82-62772644dcaa
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Visão geral do encaminhamento pelo lado do servidor

O encaminhamento pelo lado do servidor foi projetado para clientes que desejam compartilhar dados do Analytics em outras Soluções da Experience Cloud em tempo real. Quando habilitado, o encaminhamento pelo lado do servidor também permite que o Analytics envie dados para outras soluções da Experience Cloud e que essas soluções enviem dados para o Analytics durante o processo de coleta de dados.

O encaminhamento pelo lado do servidor melhora na coleta de dados porque:

* Reduz as chamadas da página. Com o encaminhamento pelo lado do servidor, os clientes do [!DNL Audience Manager] não precisam mais usar o DIL para a coleta de dados porque estão sendo encaminhados do Analytics. Remover o DIL significa eliminar uma chamada `"/event"`. Menos chamadas ajudam a melhorar o tempo de carregamento da página, o que proporciona uma melhor experiência do cliente em seu site.
* Permite aproveitar o compartilhamento de dados entre as soluções da Experience Cloud.
* Está em conformidade com nossas práticas recomendadas para implementação e implantação do código do Gerenciador de Audiências.

>[!TIP]
>
>Os clientes atuais do Audience Manager que utilizam o Analytics devem migrar para o encaminhamento pelo lado do servidor. Os novos clientes do Adobe Analytics e do Audience Manager devem implementar o encaminhamento pelo lado do servidor (em vez do DIL) como o método de transferência e coleta de dados padrão.

>[!IMPORTANT]
>Por solicitação do Regulamento de conformidade de cookies da UE, controladores de dados (clientes do Analytics) agora têm a opção de restringir dados pré-consentimento do Adobe Analytics, e evitar que sejam encaminhados pelo lado do servidor para o Adobe Audience Manager (AAM). Uma nova variável de contexto de implementação permite sinalizar ocorrências em que o consentimento não foi recebido. A variável, quando definida, impede que essas ocorrências sejam enviadas para o AAM até que o consentimento seja recebido. For more information, see [GDPR_ePrivacy compliance and server-side forwarding](/help/admin/admin/c-server-side-forwarding/ssf-gdpr.md).

Para entender onde sua organização está em termos de implementação do encaminhamento pelo lado do servidor, passe por essas etapas de validação:

## ![step1_icon.png imagem](assets/step1_icon.png) Verificar implementação do serviço ECID

Verifique se o serviço da Experience Cloud ID (ECID) está implementado, ao inspecionar a [solicitação de rastreamento do Analytics](https://marketing.adobe.com/resources/help/pt_BR/mcvid/mcvid-test-verify.html).

Na guia Solicitação, verifique se um valor de ECID está definido. Isso indica que o Serviço de identidade está implementado corretamente, o que é um pré-requisito para o encaminhamento pelo lado do servidor.

* Se você encontrar um valor ECID, avance para a etapa 2.
* Se você não vir um valor de ECID, [implemente o Serviço de identidade](https://marketing.adobe.com/resources/help/pt_BR/mcvid/mcvid-implementation-guides.html) antes de prosseguir para a etapa 2.

## ![step2_icon.png imagem](assets/step2_icon.png) Verificar a versão de implementação do encaminhamento pelo lado do servidor

Verifique se você já tem uma versão do encaminhamento pelo lado do servidor implementada, [inspecionando a solicitação de rastreamento do Analytics](/help/admin/admin/c-server-side-forwarding/ssf-verify.md).

Na guia &quot;Resposta&quot;, verifique se a resposta contém dados do Audience Manager. Se você encontrar:

* Uma **resposta JSON do Audience Manager que inclui itens como &quot;postbacks&quot; ou &quot;dcs_region&quot;**: você já possui alguma forma de encaminhamento pelo lado do servidor habilitada. Prossiga para a etapa 3.
* O **&quot;status&quot;:&quot;SUCCESS&quot;**: você tem o módulo de Gerenciamento de público-alvo implementado, mas o encaminhamento pelo lado do servidor não foi configurado corretamente. Prossiga para a etapa 3.
* Uma imagem **de** 2 x 2: o encaminhamento pelo lado do servidor ou o Módulo de gerenciamento de Audiências não estão implementados. Para corrigir isso:

   * **Clientes do AAM com DIL**: coordene os dois itens a seguir em uma conjunção próxima:

      1. Remova o código DIL e instale o código de página do Módulo [de gerenciamento de](https://docs.adobe.com/content/help/pt-BR/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html) Audiências.
      1. Ative o encaminhamento pelo lado do servidor na interface do usuário do Analytics Admin, conforme descrito na etapa 3. Habilitar essa configuração antes de remover o código DIL irá duplicado de dados e criar chamadas de servidor faturadas adicionais para o Audiência Manager.
   * **Novos clientes** do AAM - instale o código de página do Módulo [de gerenciamento de](https://docs.adobe.com/content/help/pt-BR/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html) Audiências e continue com a etapa 3. Os dados não serão enviados para o Gerenciador de Audiências até que o encaminhamento pelo lado do servidor seja ativado na etapa 3.


## ![step3_icon.png imagem](assets/step3_icon.png) Verificar a implementação do encaminhamento pelo lado do servidor do conjunto de relatórios

Verifique se o encaminhamento pelo lado do servidor foi implementado no nível do conjunto de relatórios, em vez da abordagem do servidor de rastreamento herdado.

O encaminhamento pelo lado do servidor no nível do conjunto de relatórios é recomendado na abordagem do servidor de rastreamento herdado, pois você pode controlar em um nível mais fino quais dados são compartilhados do Analytics. Também é um pré-requisito para essa integração do Analytics de Audiência.

Acesse **Analytics** > **Administração** > **Conjuntos de relatórios** > (selecione o **conjunto de relatórios**) > **Editar configurações** > **Geral** > **Encaminhamento pelo lado do servidor**. Se a caixa de seleção estiver:

* **Inativa** (Você não pode fazer uma seleção ou o menu não existe): você não possui os conjuntos de relatórios selecionados mapeados para a sua Organização IMS. Certifique-se de que os seus conjuntos de relatórios aplicáveis sejam mapeados à Organização da Experience Cloud adequada usando a [Interface do usuário de mapeamento de conjuntos de relatórios](https://docs.adobe.com/content/help/pt-BR/core-services/interface/about-core-services/report-suite-mapping.html).
* **Desativado**: O novo encaminhamento pelo lado do servidor não está ativado. Leia o conteúdo na página e prossiga com a ativação do recurso.
* **Ativado**: Você está provisionado para o novo encaminhamento pelo lado do servidor. Você também pode configurar essa integração do Analytics de Audiência.

>[!NOTE] Os dados não serão exibidos em outras soluções da Experience Cloud, como [Audience Manager](https://docs.adobe.com/content/help/pt-BR/audience-manager/user-guide/aam-home.translate.html) ou [Públicos-alvo](https://marketing.adobe.com/resources/help/pt_BR/mcloud/audience_library.html), até que todas as 3 etapas sejam concluídas. Uma vez ativado, levará várias horas para que essas configurações entrem em vigor.

