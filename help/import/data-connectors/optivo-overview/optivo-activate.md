---
description: Use o Assistente de configuração dos conectores de dados da Adobe para configurar a integração.
seo-description: Use o Assistente de configuração dos conectores de dados da Adobe para configurar a integração.
seo-title: Ativar a integração
title: Ativar a integração
uuid: 3b2acdb8-9a1f-4f17-92f2-6a3780a8f626
translation-type: tm+mt
source-git-commit: 34b18e7769e0850283fd3840c2557818d5d742f0

---


# Ativar a integração{#activate-the-integration}

Use o Assistente de configuração dos conectores de dados da Adobe para configurar a integração.

1. Inicie os Conectores [de](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) dados e clique em **[!UICONTROL + Adicionar novo]** para [adicionar uma nova integração](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html).
1. Na lista **[!UICONTROL Exibir]** , selecione **[!UICONTROL Por nome]** e arraste a integração do [!DNL ~parceiro~] para um slot de plug-in vazio.
1. Complete o Assistente de integração usando as informações na tabela a seguir:

| Campo | Descrição |
|--- |--- |
| Conjunto de relatórios | O conjunto de relatórios que recebe os dados dessa integração. |
| Nome da integração | Especifique o nome da integração que os Conectores de dados exibem na lista Integração ativa do conjunto de relatórios. |
| Endereço de email | Forneça um endereço de email para receber informações relacionadas à integração. |
| ID da Conta | Esse é o identificador exclusivo atribuído à sua organização pelo Provedor de serviços de e-mail. Ele será usado ao solicitar dados de campanha por email (por exemplo, # Enviado, # Aberto, # Clicado, etc.) de e enviando segmentos de visitantes para seu Provedor de serviços de e-mail. |
| Recipient ID | Esta ID é uma representação codificada ou numérica de um endereço de email do sistema de email optivo®. Essa "ID do destinatário" está associada ao comportamento do visitante downstream no site (abandonos de carrinho, compras etc.) que é puxada para dentro do sistema de banda larga optivo® e pode ser aproveitada para fins de remarketing. |
| ID da mensagem | (Obrigatório) Armazena a ID de endereçamento exclusiva. Essas dimensões de classificação são criadas pelo assistente de Conectores de dados para a ID da mensagem: <br>a)**Campanhas**: Campanhas associadas à mensagem. <br>b)**Canal**: O canal de transmissão é constantemente "optivo Broadmail". <br>c)Código **** do país: Este campo contém o código de país do país do remetente de origem. É uma constante "DE". <br>d) Ferramenta **de entrega**: Método de transmissão, sempre "Email".<br> e) Nome **da** mensagem: O nome do correio, conforme configurado no optivo® Broadmail. <br>f) Data **de** início: Carimbo de data e hora do início desta correspondência. |
| Hora de clique da postagem | (Obrigatório) Isso é necessário para transmitir informações sobre uma ação do destinatário ao optivo® Broadmail depois que o destinatário clicou em um link em um email. |
| Produto de cliques pós-publicação | (Obrigatório) Isso é necessário para transmitir informações sobre uma ação do destinatário ao optivo® Broadmail depois que o destinatário clicou em um link em um email. |
| Ação de clicar na postagem | (Obrigatório) Isso é necessário para transmitir informações sobre uma ação do destinatário ao optivo® Broadmail depois que o destinatário clicou em um link em um email. |
| Rejeição forçada | (Obrigatório) Especifique o evento do Adobe Analytics que armazena os dados de rejeição em disco importados do sistema de email. Número de mensagens de e-mail que não foram entregues aos destinatários e são consideradas como não entregues permanentemente. |
| Rejeição suave | (Obrigatório) Especifique o evento do Adobe Analytics que armazena os dados de rejeição em mídia eletrônica importados do sistema de email. Número de mensagens de email que não foram entregues aos destinatários devido a um problema de entrega. |
| Clicado | (Obrigatório) Especifique o evento do Adobe Analytics que armazena os dados clicados por email importados do sistema de email. O evento Clicado permite que você veja o número de visitantes que clicaram na mensagem de email. |
| Aberto | (Obrigatório) Especifique o evento do Adobe Analytics que armazena os dados abertos por email importados do sistema de email. O evento Aberto permite que você veja o número de visitantes que abriram a mensagem de email. |
| Enviados | (Obrigatório) Especifique o evento do Adobe Analytics que armazena os dados enviados por email importados do sistema de email. O evento Enviado permite que você veja o número de mensagens de email enviadas. |
| Inscrito | (Obrigatório) Especifique o evento do Adobe Analytics que armazena os dados de cancelamento de assinatura por email importados do sistema de email. O evento Cancelado de inscrição permite que você veja o número de visitantes que abriram a mensagem de email, mas clicaram no link Cancelar inscrição para recusar futuras mensagens de email de sua organização. |
| Segmentos | Habilitar segmentos existentes para serem usados junto com essa integração (opcional). |
|  Solicitações de acesso | Ative os privilégios de acesso recomendados. |
| Coleta de dados | Selecione Plug-in **de** JavaScript se desejar usar o plug-in s_code.js como o modelo de coleção para essa integração. Selecione Solução **** automatizada se desejar usar um modelo de coleta automatizada para essa integração e especifique os identificadores exclusivos usados para essa integração. Se você selecionar essa opção, especifique os identificadores exclusivos usados para essa integração:<ul><li>Parâmetro da string de consulta da ID da mensagem: Esse valor representa a ID da mensagem anexada ao URL da página inicial pelo seu parceiro de email.</li><li>Parâmetro da string de consulta da ID do destinatário: Esse valor representa a ID do destinatário anexada ao URL da página inicial pelo seu parceiro de email.</li></ul> |
| Geração de painel e marcador | Gerar automaticamente um painel e marcadores para a integração. |