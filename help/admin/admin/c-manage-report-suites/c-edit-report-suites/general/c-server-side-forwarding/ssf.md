---
description: O encaminhamento pelo lado do servidor foi projetado para clientes que desejam compartilhar dados do Analytics com outras soluções da Experience Cloud em tempo real. Quando habilitado, o encaminhamento pelo lado do servidor também permite que o Analytics envie dados para outras soluções da Experience Cloud e que essas soluções enviem dados para o Analytics durante o processo de coleta de dados.
solution: Analytics
title: Visão geral do encaminhamento pelo lado do servidor
feature: Report Suite Settings
exl-id: e3cd72d2-9588-4770-a7c2-64b13a1e9519
role: Admin
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 100%

---

# Visão geral do encaminhamento pelo lado do servidor

O encaminhamento pelo lado do servidor foi projetado para clientes que desejam compartilhar dados do Analytics com outras soluções da Experience Cloud em tempo real. Quando habilitado, o encaminhamento pelo lado do servidor também permite que o Analytics envie dados para outras soluções da Experience Cloud e que essas soluções enviem dados para o Analytics durante o processo de coleta de dados.

O encaminhamento pelo lado do servidor é aprimorado no momento da coleta de dados porque:

* Reduz as chamadas da página. Com o encaminhamento pelo lado do servidor, os clientes do [!DNL Audience Manager] não precisam mais usar o DIL para a coleta de dados porque estão sendo encaminhados do Analytics. Remover o DIL significa eliminar uma chamada `"/event"`. Menos chamadas ajudam a melhorar os tempos de carregamento de página, o que cria uma melhor experiência do cliente em seu site.
* Permite aproveitar o compartilhamento de dados entre as soluções da Experience Cloud.
* Está em conformidade com nossas práticas recomendadas do Audience Manager para a implementação e implantação de códigos.

>[!TIP]
>
>Os clientes atuais do Audience Manager que utilizam o Analytics devem migrar para o encaminhamento pelo lado do servidor. Os novos clientes do Adobe Analytics e do Audience Manager devem implementar o encaminhamento pelo lado do servidor (em vez do DIL) como o método de transferência e coleta de dados padrão.

>[!IMPORTANT]
>Para atender à regulamentação de conformidade de cookies da UE, controladores de dados (clientes do Analytics) agora têm a opção de restringir dados de pré-consentimento no Adobe Analytics e evitar que sejam encaminhados pelo lado do servidor para o Adobe Audience Manager. Uma nova variável de contexto de implementação permite sinalizar ocorrências onde o consentimento não foi recebido. A variável, quando definida, evita que essas ocorrências sejam enviadas para o Adobe Audience Manager até que o consentimento seja recebido. Para obter mais informações, consulte [Conformidade do GDPR_ePrivacy com o encaminhamento pelo lado do servidor](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-gdpr.md).

Para entender onde sua organização está em termos de implementação do encaminhamento pelo lado do servidor, passe por essas etapas de validação:

## ![step1_icon.png imagem](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step1_icon.png) Verificar implementação do serviço ECID

Verifique se o serviço da Experience Cloud ID (ECID) está implementado, ao inspecionar a [solicitação de rastreamento do Analytics](https://experienceleague.adobe.com/docs/id-service/using/implementation/test-verify.html?lang=pt-BR).

Na guia Solicitação, verifique se um valor de ECID está definido. Isso indica que o Serviço de identidade está implementado corretamente, o que é um pré-requisito para o encaminhamento pelo lado do servidor.

* Se você encontrar um valor ECID, avance para a etapa 2.
* Se você não vir um valor de ECID, [implemente o Serviço de identidade](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html?lang=pt-BR) antes de prosseguir para a etapa 2.

## ![step2_icon.png imagem](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step2_icon.png) Verificar a versão de implementação do encaminhamento pelo lado do servidor

Verifique se você já tem uma versão do encaminhamento pelo lado do servidor implementada, [inspecionando a solicitação de rastreamento do Analytics](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-verify.md).

Na guia &quot;Resposta&quot;, verifique se a resposta contém dados do Audience Manager. Se você encontrar:

* Uma **resposta JSON do Audience Manager que inclui itens como &quot;postbacks&quot; ou &quot;dcs_region&quot;**: você já possui alguma forma de encaminhamento pelo lado do servidor habilitada. Prossiga para a etapa 3.
* O **&quot;status&quot;:&quot;SUCCESS&quot;**: você tem o módulo de Gerenciamento de público-alvo implementado, mas o encaminhamento pelo lado do servidor não foi configurado corretamente. Prossiga para a etapa 3.
* Uma **imagem 2 x 2**: você não possui o encaminhamento pelo lado do servidor ou o módulo de Gerenciamento de público-alvo implementado. Para corrigir isso:

   * **Clientes do Adobe Audience Manager com DIL**: coordene os 2 seguintes itens em conjunto:

      1. Remova o código DIL e instale o código de página do [módulo de Gerenciamento de público-alvo](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html?lang=pt-BR).
      1. Ative o encaminhamento pelo lado do servidor na interface do usuário do Analytics, conforme descrito na etapa 3. Habilitar esta configuração antes de remover o código DIL duplicará os dados e criará chamadas de servidor cobradas adicionais no Audience Manager.

   * **Novos(as) clientes do Adobe Audience Manager**: instale o código de página do [Módulo de gerenciamento de público-alvo](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html?lang=pt-BR) e avance para a etapa 3. Os dados não serão enviados ao Audience Manager até que o encaminhamento pelo lado do servidor seja ativado na etapa 3.

## ![step3_icon.png imagem](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step3_icon.png) Verificar a implementação do encaminhamento pelo lado do servidor do conjunto de relatórios

Verifique se o encaminhamento pelo lado do servidor foi implementado em nível de conjunto de relatórios, em vez da abordagem do servidor de rastreamento herdado.

O encaminhamento pelo lado do servidor no nível do conjunto de relatórios é recomendado por meio da abordagem do servidor de rastreamento herdado porque assim você pode controlar em maior detalhe quais dados são compartilhados com o Analytics. Também é um pré-requisito para esta integração do Audience Analytics.

Acesse **Analytics** > **Administração** > **Conjuntos de relatórios** > (selecione o **conjunto de relatórios**) > **Editar configurações** > **Geral** > **Encaminhamento pelo lado do servidor**. Se a caixa de seleção estiver:

* **Inativo** (Você não pode fazer uma seleção ou o menu não existe): você não tem os conjuntos de relatórios selecionados mapeados para uma ID de organização. Entre em contato com o Atendimento ao cliente para verificar se o conjunto de relatórios está mapeado corretamente.
* **Desabilitada**: você não possui o novo encaminhamento pelo lado do servidor ativado. Leia o conteúdo na página e prossiga com a ativação do recurso.
* **Habilitada:** você está provisionado para o novo encaminhamento pelo lado do servidor. Você também pode configurar esta integração do Audience Analytics.

>[!NOTE]
>
>Os dados não serão exibidos em outras soluções da Experience Cloud, como [Audience Manager](https://docs.adobe.com/content/help/pt-BR/experience-cloud/user-guides/home.html) ou [Públicos-alvo](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=pt-BR), até que todas as 3 etapas sejam concluídas. Uma vez ativado, levará várias horas para que essas configurações entrem em vigor.
