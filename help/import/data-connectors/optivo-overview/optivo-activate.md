---
description: Use o assistente de Configuração dos Conectores de dados da Adobe para configurar a integração.
seo-description: Use o assistente de Configuração dos Conectores de dados da Adobe para configurar a integração.
seo-title: Ativar a integração
title: Ativar a integração
uuid: 3 b 2 acdb 8-9 a 1 f -4 f 17-92 f 2-6 a 3780 a 8 f 626
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Ativar a integração{#activate-the-integration}

Use o assistente de Configuração dos Conectores de dados da Adobe para configurar a integração.

1. Inicie [Conectores de dados](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) e clique **[!UICONTROL em + Adicionar novo]** para [adicionar uma nova integração](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html).
1. Na lista **[!UICONTROL Exibir]** , selecione **[!UICONTROL Por nome]** e arraste a integração [!DNL ~Parceiro~] para um slot de plug-in vazio.
1. Preencha o Assistente de integração usando as informações na tabela a seguir:

| Campo | Descrição |
|--- |--- |
| Conjunto de relatórios | O conjunto de relatórios que recebe os dados dessa integração. |
| Nome da integração | Especifique o nome da integração que os Conectores de dados exibem na Lista de integração ativa do conjunto de relatórios. |
| Endereço de email | Forneça um endereço de email para receber informações relacionadas à integração. |
| ID da Conta | Esse é o identificador exclusivo atribuído à sua organização pelo Provedor de serviço de email. Ele será usado ao solicitar dados de campanha por email (por exemplo, # Enviado, # Abertos, # Clicked etc.) de e enviar segmentos de visitantes para seu Provedor de serviço de email. |
| Recipient ID | Essa ID é uma representação codificada ou numérica de um endereço de email do sistema de email optivo® vs. Essa «ID do destinatário» é associada ao comportamento de visitante descendente no site (abandonos de carrinho, compras etc.) que são coletados no sistema de email optivo® e podem ser aproveitados para fins de recomercialização. |
| ID da mensagem | (Obrigatório) Armazena a ID de correspondência exclusiva. Essas dimensões de classificação são criadas pelo assistente dos Conectores de dados para a ID da mensagem: a)**Campanhas**: Campanhas associadas com a mensagem. b)**Canal**: O canal de transmissão, isso é constantemente "optivo broademail". c)**Código do país**: Esse campo contém o código do país do país de origem do remetente. É uma constante "DE". d) **Ferramenta de entrega**: Método de transmissão, sempre «Email». e) **Nome da mensagem**: O nome da correspondência, já que está configurado em um email optivo®. f) **Data inicial**: Carimbo de data e hora do início desta correspondência. |
| Tempo de clique da postagem | (Obrigatório) Isso é necessário para transmitir informações sobre uma ação do destinatário com o email optivo®, depois que o destinatário clicou em um link em uma correspondência. |
| Publicar clique em produto | (Obrigatório) Isso é necessário para transmitir informações sobre uma ação do destinatário com o email optivo®, depois que o destinatário clicou em um link em uma correspondência. |
| Ação de clique na postagem | (Obrigatório) Isso é necessário para transmitir informações sobre uma ação do destinatário com o email optivo®, depois que o destinatário clicou em um link em uma correspondência. |
| Rejeição sólida | (Obrigatório) Especifique o evento do Adobe Analytics que armazena os dados de rejeição importados do sistema de e-mail. Número de mensagens de email que não foram entregues aos destinatários e são consideradas permanentemente não entregues. |
| Rejeição suave | (Obrigatório) Especifique o evento do Adobe Analytics que armazena os dados de retorno de dados importados do sistema de email. Número de mensagens de email que não foram entregues aos destinatários devido a um problema de entrega. |
| Clicado | (Obrigatório) Especifique o evento do Adobe Analytics que armazena os dados clicados por e-mail importados do sistema de e-mail. O evento Clicado permite ver o número de visitantes que clicaram na mensagem de e-mail. |
| Abertos | (Obrigatório) Especifique o evento do Adobe Analytics que armazena os dados abertos por email importados do sistema de email. O evento Aberto permite que você veja o número de visitantes que abriram a mensagem de e-mail. |
| Enviado | (Obrigatório) Especifique o evento do Adobe Analytics que armazena os dados enviados por email importados do sistema de email. O evento Enviado permite que você veja o número de mensagens de email enviadas. |
| Cancelar inscrição | (Obrigatório) Especifique o evento do Adobe Analytics que armazena os dados de assinatura por e-mail importados do sistema de email. O evento Cancelar inscrição permite ver o número de visitantes que abriram a mensagem de email, mas clicaram no link Cancelar inscrição para recusar futuras mensagens de email de sua organização. |
| Segmentos | Ative os segmentos existentes para serem usados junto com essa integração (opcional). |
| Solicitações de acesso | Habilite os privilégios de acesso recomendados. |
| Coleção de dados | Selecione **o plug-in javascript** caso deseje usar o plug-in s_ code. js como modelo de coleção para essa integração. Selecione **Solução automatizada** se quiser usar um modelo de coleção automatizado para essa integração e especifique os identificadores exclusivos usados para essa integração. Se você selecionar essa opção, especifique os identificadores únicos usados para essa integração:<ul><li>Parâmetro da string de consulta da ID da mensagem: Esse valor representa a ID da mensagem anexada ao URL da página de aterrissagem pelo seu parceiro de e-mail.</li><li>Parâmetro da sequência de consulta da ID do destinatário: Esse valor representa o appendedto da ID do destinatário no URL da página de aterrissagem pelo seu parceiro de e-mail.</li></ul> |
| Geração de painel e marcador | Gerar automaticamente um painel e marcadores para a integração. |