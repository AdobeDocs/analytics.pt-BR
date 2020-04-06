---
description: Descreve o processo de implantação em três etapas.
title: Implantar a integração
uuid: a3c0ef21-ed9a-44d7-bdce-19b3bd5b8b80
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Implantar a integração {#deploying-the-integration}

Descreve o processo de implantação em três etapas.

A implantação dessa integração é um processo simples que requer as seguintes ações:

## Concluir o Assistente de integração {#completing-the-integration-wizard}

Etapas para usar o assistente de integração.

Para ativar a integração, você deve concluir o assistente de integração do Lyris na interface dos Data Connectors.

1. Navegue até a área Data Connectors (anteriormente Genesis) na Adobe Experience Cloud.

   ![](assets/data_connectors.png)

1. Em **[!UICONTROL Add Integration]**, em Lyris HQ, clique em **[!UICONTROL Activate]**.

   ![](assets/add_integration.png)

1. Under **[!UICONTROL General Settings]**, choose the desired Report Suite and provide a name for the integration.
1. Fill in all your Lyris account-related information under **[!UICONTROL Custom Values]**.

   ![](assets/general_settings.png)

1. Escolha as eVars e os eventos reservados apropriados nos menus suspensos.

   ![](assets/variable_mapping.png)

1. You may choose your own segments under **[!UICONTROL Your Segments]** - apart from the 3 automated Partner segments.
1. Essa integração pode exigir o download de alguns pontos de dados para sua conta do Lyris. You may choose to give access for this under **[!UICONTROL Access Request]**.
1. Under **[!UICONTROL Data Collection]**, you can choose to have an automated or a manual solution (JavaScript Plug-in) to collect query string parameters from the landing page URL. Se você optar por ter uma solução automatizada, digite os parâmetros ID da mensagem e ID do destinatário da string de consulta. Para obter um plug-in do JavaScript, entre em contato com seu consultor da Adobe.

   ![](assets/data_collection.png)

1. Você pode optar por gerar automaticamente o painel e marcadores do Lyris.

   ![](assets/dashboard_generation.png)

1. Review the integration summary and click **[!UICONTROL Activate]**.

## Configuração no EmailLabs do Lyris {#configuration-within-the-lyris-emaillabs}

Etapas que descrevem o que configurar no Lyris após a conclusão do assistente.

1. Após concluir o assistente de integração, você deve trabalhar com a equipe profissional do Lyris para concluir a integração com sua conta do Lyris HQ e facilitar os testes.
1. Adicionar parâmetros de string de consulta de URL: verifique se a string de anexação do URL está inserida corretamente nas áreas de configuração da seção Organização da interface do usuário. Ela deve conter a ID do nível da campanha (hq_m) e a ID do nível do destinatário (hq_v).

   Um exemplo de ID em string é:

   ```
   hq_lid=149&hq_m=96843&hq_l=23&hq_v=7703a51905
   ```

   >[!NOTE]
   >
   >Se você estiver aplicando a ferramenta nativa de análise do Lyris, o *Rastreamento de cliques* marcará todas as variáveis necessárias que foram adicionadas.

## Verificar a integração {#verifying-the-integration}

Etapas para verificar se a integração Lyris/Adobe Analytics foi bem-sucedida.

Depois que todas as etapas de implantação forem concluídas, você poderá validar se a integração está transferindo dados com êxito.

>[!NOTE] Leva alguns dias para a troca de dados começar. Entre em contato com a Lyris depois de ativar a integração.

1. Navegue até sua integração do Lyris nos Data Connectors. Na **[!UICONTROL Support]** guia > **[!UICONTROL Integration Activity Log]**, você deve ver eventos como **[!UICONTROL Metric data imported successfully]** e/ou **[!UICONTROL Classification data imported successfully]**:

   ![](assets/integration_info.png)

1. Agora, visualize seus relatórios de mensagem do Lyris com as métricas apropriadas. In the Adobe Experience Cloud, select **[!UICONTROL Reports & Analytics]**.
1. Selecione o conjunto de relatórios adequados.
1. Em **[!UICONTROL Custom Conversions]**, selecione o **[!UICONTROL Message ID Reports]** e escolha **[!UICONTROL Message ID/Message Name]**.

## Código do plug-in do parâmetro da string de consulta {#query-string-param-plug-in-code}

Mostra o código do plug-in do Lyris a ser usado com o Adobe Analytics.

>[!NOTE] Certifique-se de ter reservado as eVars necessárias na Ferramenta de administração do Adobe Analytics antes de trabalhar com o código abaixo. Depois de saber quais eVars você reservou, substitua eVarN pela eVar relevante. Por exemplo, pela eVar10.

```
/* 
  * Plugin: getQueryParam 2.3 
  */ 
s.getQueryParam=new Function("p","d","u","" 
+"var s=this,v='',i,t;d=d?d:'';u=u?u:(s.pageURL?s.pageURL:s.wd.locati" 
+"on);if(u=='f')u=s.gtfs().location;while(p){i=p.indexOf(',');i=i<0?p" 
+".length:i;t=s.p_gpv(p.substring(0,i),u+'');if(t){t=t.indexOf('#')>-" 
+"1?t.substring(0,t.indexOf('#')):t;}if(t)v+=v?d+t:t;p=p.substring(i=" 
+"=p.length?i:i+1)}return v"); 
s.p_gpv=new Function("k","u","" 
+"var s=this,v='',i=u.indexOf('?'),q;if(k&&i>-1){q=u.substring(i+1);v" 
+"=s.pt(q,'&','p_gvf',k)}return v"); 
s.p_gvf=new Function("t","k","" 
+"if(t){var s=this,i=t.indexOf('='),p=i<0?t:t.substring(0,i),v=i<0?'T" 
+"rue':t.substring(i+1);if(p.toLowerCase()==k.toLowerCase())return s." 
+"epa(v)}return ''"); 
 
/*in the s_doPlugins function - Replace N with actual eVar number*/ 
s.eVarN=s.getQueryParam("<insert Lyris QS Param>");  
//places query param value from Message ID in eVarN variable s.eVarN=s.getQueryParam("<insert Lyris QS Param>");  
//places query param value from Recepient ID in eVarN variable 
```
