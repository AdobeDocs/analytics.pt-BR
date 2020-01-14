---
description: Descreve o processo de implantação em três etapas.
title: Implantar a integração
uuid: a3c0ef21-ed9a-44d7-bdce-19b3bd5b8b80
translation-type: tm+mt
source-git-commit: a3aa8feb937e2a1f40c498aa4e143de21cf26b86

---


# Implantar a integração{#deploying-the-integration}

Descreve o processo de implantação em três etapas.

A implantação dessa integração é um processo simples que requer as seguintes ações:

## Concluindo o Assistente de integração{#completing-the-integration-wizard}

Etapas para usar o assistente de integração.

Para ativar a integração, você deve concluir o assistente de integração do Lyris na interface dos Conectores de dados.

1. Navegue até a área Conectores de dados (anteriormente Genesis) na Adobe Experience Cloud.

   ![](assets/data_connectors.png)

1. Em **[!UICONTROL Adicionar integração]**, em Lyris HQ, clique em**[!UICONTROL  Ativar]**.

   ![](assets/add_integration.png)

1. Em Configurações ****gerais, escolha o Conjunto de relatórios desejado e forneça um nome para a integração.
1. Preencha todas as informações relacionadas à conta do Lyris em Valores ****personalizados.

   ![](assets/general_settings.png)

1. Escolha as eVars e os eventos reservados apropriados nos menus suspensos.

   ![](assets/variable_mapping.png)

1. Você pode escolher seus próprios segmentos em **[!UICONTROL Seus segmentos]**- exceto os três segmentos de parceiro automatizados.
1. Essa integração pode exigir o download de alguns pontos de dados para sua conta do Lyris. Você pode optar por conceder acesso para isso em Solicitação **[!UICONTROL de]**acesso.
1. Em Coleta **[!UICONTROL de]**dados, você pode optar por ter uma solução automática ou manual (Plug-in JavaScript) para coletar parâmetros de sequência de consulta do URL da página inicial. Se você optar por ter uma solução automatizada, digite o parâmetro da sequência de consulta para ID da mensagem e ID do destinatário. Para obter um plug-in JavaScript, entre em contato com seu consultor da Adobe.

   ![](assets/data_collection.png)

1. Você pode optar por gerar automaticamente o painel Lyris e marcadores para você.

   ![](assets/dashboard_generation.png)

1. Revise o resumo da integração e clique em **[!UICONTROL Ativar]**.

## Configuração nos EmailLabs da Lyris{#configuration-within-the-lyris-emaillabs}

Etapas que descrevem o que configurar dentro do Lyris após a conclusão do assistente.

1. Após concluir o assistente de integração, você deve trabalhar com a equipe do Lyris Professional para concluir a integração com sua conta do Lyris HQ e facilitar os testes.
1. Adicionar parâmetros de sequência de consulta de URL: Verifique se a string de anexação do URL está inserida corretamente nas áreas de configurações da Organização da interface do usuário. Isso deve conter a ID do nível da campanha (hq_m) e a ID do nível do destinatário (hq_v).

   Um exemplo de uma ID de string é:

   ```
   hq_lid=149&hq_m=96843&hq_l=23&hq_v=7703a51905
   ```

   >[!NOTE]
   >
   >Se você estiver aplicando a ferramenta nativa de análise do Lyris, *clique em Rastreamento* marcará todas as variáveis necessárias que foram adicionadas.

## Verificar a integração{#verifying-the-integration}

Etapas para verificar se a integração do Lyris/Adobe Analytics foi bem-sucedida.

Depois que todas as etapas de implantação forem concluídas, você poderá validar se a integração está transferindo dados com êxito.

> [!NOTE] Leva alguns dias para a troca de dados começar. Entre em contato com Lyris depois de ativar a integração.

1. Navegue até sua Integração do Lyris nos Conectores de dados. Na guia **[!UICONTROL Suporte]**> Log**[!UICONTROL  de atividade de]**integração, você deve ver eventos como dados **[!UICONTROL de métrica importados com êxito]**e/ou dados de**[!UICONTROL  classificação importados com êxito]**:

   ![](assets/integration_info.png)

1. Agora, visualize seus relatórios de mensagem do Lyris com as métricas apropriadas. Na Adobe Experience Cloud, selecione **[!UICONTROL Relatórios e análises]**.
1. Selecione o conjunto de relatórios adequados.
1. Em Conversões ****personalizadas, selecione os Relatórios**[!UICONTROL  de ID da]** mensagem e escolha ID da **[!UICONTROL mensagem/Nome]**da mensagem.

## Código do plug-in do parâmetro da cadeia de consulta{#query-string-param-plug-in-code}

Mostra o código do plug-in do Lyris a ser usado com o Adobe Analytics.

> [!NOTE] Certifique-se de reservar as eVars necessárias na Ferramenta de administração do Adobe Analytics antes de trabalhar com o código abaixo. Depois de saber quais eVars você reservou, substitua eVarN pela eVar relevante. Por exemplo, eVar10.

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
