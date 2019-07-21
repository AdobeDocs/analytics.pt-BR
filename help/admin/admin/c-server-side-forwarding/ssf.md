---
description: O encaminhamento pelo lado do servidor foi projetado para clientes que desejam compartilhar dados do Analytics com outras soluções da Experience Cloud em tempo real. Quando habilitado, o encaminhamento pelo lado do servidor também permite que o Analytics envie dados a outras soluções da Experience Cloud e, consequentemente, que essas soluções enviem dados para o Analytics durante o processo de coleta de dados.
seo-description: O encaminhamento pelo lado do servidor foi projetado para clientes que desejam compartilhar dados do Analytics com outras soluções da Experience Cloud em tempo real. Quando habilitado, o encaminhamento pelo lado do servidor também permite que o Analytics envie dados a outras soluções da Experience Cloud e, consequentemente, que essas soluções enviem dados para o Analytics durante o processo de coleta de dados.
seo-title: Visão geral do encaminhamento pelo lado do servidor
solution: Audience Manager
title: Visão geral do encaminhamento pelo lado do servidor
uuid: 22 ddbde 5-6805-4 eba -8 f 82-62772644 dcaa
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Visão geral do encaminhamento pelo lado do servidor

O encaminhamento pelo lado do servidor foi projetado para clientes que desejam compartilhar dados do Analytics com outras soluções da Experience Cloud em tempo real. Quando habilitado, o encaminhamento pelo lado do servidor também permite que o Analytics envie dados a outras soluções da Experience Cloud e, consequentemente, que essas soluções enviem dados para o Analytics durante o processo de coleta de dados.

O encaminhamento pelo lado do servidor é aprimorado no momento da coleta de dados porque:

* Reduz as chamadas da página. With server-side forwarding, [!DNL Audience Manager] customers no longer need to use DIL for data collection because it is being forwarded from Analytics. Removing DIL means eliminating an `"/event"` call. Menos chamadas ajudam a melhorar os tempos de carregamento de página, o que cria uma melhor experiência do cliente em seu site.
* Permite aproveitar o compartilhamento de dados entre as soluções da Experience Cloud.
* Está em conformidade com nossas práticas recomendadas do Audience Manager para a implementação e implantação de códigos.

>[!TIP]
>
>Os clientes atuais do Audience Manager que usam o Analytics devem migrar para o encaminhamento pelo lado do servidor. Os novos clientes do Adobe Analytics e do Audience Manager devem implementar o encaminhamento pelo lado do servidor (em vez do DIL) como o método de transferência e coleta de dados padrão.

>[!IMPORTANT]
>Por solicitação do Regulamento de conformidade de cookies da UE, controladores de dados (clientes do Analytics) agora têm a opção de restringir dados pré-consentimento do Adobe Analytics, e evitar que sejam encaminhados pelo lado do servidor para o Adobe Audience Manager (AAM). Uma nova variável de contexto de implementação permite sinalizar ocorrências onde o consentimento não foi recebido. A variável, quando definida, evita que tais ocorrências sejam enviadas para o AAM até que o consentimento seja recebido. Para obter mais informações, consulte Conformidade do GDPR_ePrivacy com o encaminhamento pelo lado do servidor.

Para entender onde sua organização está em termos de implementação do encaminhamento pelo lado do servidor, passe por essas etapas de validação:

## ![etapa 1_ ícone imagem. png](assets/step1_icon.png) Verificação da implementação do serviço MID

Verifique se o serviço da Experience Cloud ID (MID) está implementado, ao inspecionar a [solicitação de rastreamento do Analytics](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-test-verify.html).

Na guia Solicitação, verifique se um valor de MID está definido. Isso indica que o Serviço de identidade é implementado corretamente, o que é um pré-requisito para o encaminhamento pelo lado do servidor.

* Se você encontrar um valor MID, avance para a etapa 2.
* If you do not see a MID value, [implement Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-implementation-guides.html) before proceeding to step 2.

## ![Etapa 2_ ícone imagem. png](assets/step2_icon.png) Verificação da versão de implementação do encaminhamento pelo lado do servidor

Verify whether you already have a version of server-side forwarding implemented, by [inspecting the Analytics tracking request](../../../admin/admin/c-server-side-forwarding/ssf-verify.md).

Na guia “Resposta”, verifique se a resposta contém dados do Audience Manager. Se você encontrar:

* Uma resposta **JSON do Audience Manager que inclui itens como "postbacks" ou "dcs_region"**: você já possui alguma forma de encaminhamento pelo lado do servidor habilitado. Prossiga para a etapa 3.
* O **"status":"SUCCESS"**: você possui o módulo de Gerenciamento de público-alvo implementado, mas o encaminhamento pelo lado do servidor não foi configurado corretamente. Prossiga para a etapa 3.
* Uma **imagem 2 x 2**: você não possui o encaminhamento pelo lado do servidor ou o módulo de Gerenciamento de público-alvo implementado. Para corrigir isso:

   * **Clientes AAM com DIL**: coordene os seguintes 2 itens em uma conjunção próxima:

      1. Remova o código DIL e instale o código de página do [módulo de Gerenciamento de público-alvo](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html).
      1. Ative o encaminhamento pelo lado do servidor na interface do usuário do Analytics, conforme descrito na etapa 3. Habilitar esta configuração antes de remover o código DIL duplicará os dados e criará chamadas de servidor cobradas adicionais no Audience Manager.
   * **Novos clientes do AAM** - instale o código de página do [Módulo de gerenciamento de público-alvo](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html) e prossiga para a etapa 3. Os dados não serão enviados ao Audience Manager até que o encaminhamento pelo lado do servidor seja ativado na etapa 3.


## ![etapa 3_ ícone. imagem png](assets/step3_icon.png) Verificação da implementação do encaminhamento pelo lado do servidor do conjunto de relatórios

Verifique se o encaminhamento pelo lado do servidor foi implementado em nível de conjunto de relatórios, em vez da abordagem do servidor de rastreamento herdado.

O encaminhamento pelo lado do servidor no nível do conjunto de relatórios é recomendado por meio da abordagem do servidor de rastreamento herdado porque assim você pode controlar em maior detalhe quais dados são compartilhados com o Analytics. Também é um pré-requisito para esta integração do Audience Analytics.

Go to **Analytics** &gt; **Admin** &gt; **Report Suites** &gt; (select **report suites**) &gt; **Edit Settings** &gt; **General** &gt; **Server Side Forwarding**. Se a caixa de seleção estiver:

* **Inativa** (Você não pode fazer uma seleção ou o menu não existe): você não possui os conjuntos de relatórios selecionados mapeados para a sua Organização IMS. Certifique-se de que os seus conjuntos de relatórios aplicáveis sejam mapeados à Org do IMS adequada usando a [Interface do usuário de mapeamento de conjuntos de relatórios](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html).
* **Desabilitada**: você não possui o novo encaminhamento pelo lado do servidor ativado. Leia o conteúdo na página e prossiga com a ativação do recurso.
* **Habilitada:** você está provisionado para o novo encaminhamento pelo lado do servidor. Você também pode configurar esta integração do Audience Analytics.

<!-- Meike, check Report Suite Mapping UI link above -->

>[!NOTE]
>
>Data will not appear in other Experience Cloud solutions, such as [Audience Manager](https://marketing.adobe.com/resources/help/en_US/aam/c_aam_home.html) or [Audiences](https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html) until all 3 steps are complete. Uma vez ativado, levará várias horas para que essas configurações entrem em vigor.

