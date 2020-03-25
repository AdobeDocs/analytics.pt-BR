---
description: Use o Assistente de configuração do Data Connectors da Adobe para configurar a integração.
title: Ativar a integração
uuid: 3b2acdb8-9a1f-4f17-92f2-6a3780a8f626
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Ativar a integração {#activate-the-integration}

Use o Assistente de configuração do Data Connectors da Adobe para configurar a integração.

1. Inicie o [Data Connectors](https://marketing.adobe.com/resources/help/pt_BR/genesis/c_overview.html) e clique em **[!UICONTROL + Adicionar nova]** para [adicionar uma nova integração](https://marketing.adobe.com/resources/help/pt_BR/genesis/t_add_integration.html).
1. Na lista **[!UICONTROL Exibir]**, selecione **[!UICONTROL Por nome]** e arraste a integração do [!DNL ~Parceiro~] para um slot de plug-in vazio.
1. Complete o Assistente de integração usando as informações na tabela a seguir:

| Campo | Descrição |
|--- |--- |
| Conjunto de relatórios | O conjunto de relatórios que recebe os dados dessa integração. |
| Nome da integração | Especifique o nome da integração que o Data Connectors exibe na lista Integração ativa do conjunto de relatórios. |
| Endereço de email | Forneça o endereço de email para receber informações sobre integração. |
| ID da Conta | Esse é o identificador exclusivo atribuído à sua organização pelo provedor de serviços de email. Ele será usado na solicitação de dados de campanha de email (por exemplo, Nº Enviado, Nº Abertos, Nº Clicados etc.) e ao enviar segmentos de visitantes para seu provedor de serviços de email. |
| ID de destinatário | Essa ID é uma representação codificada ou numérica de um endereço de email do sistema optivo® broadmail. Essa &quot;ID de destinatário&quot; está associada ao comportamento downstream de visitantes no site (abandonos de carrinho, compras etc.) que é extraído para o sistema optivo® broadmail e pode ser aproveitado para fins de remarketing. |
| ID de mensagem | (Obrigatório) Armazena a ID de correspondência exclusiva. Essas dimensões de classificação são criadas pelo assistente de Data Connectors para a ID de mensagem: <br>a)**Campanhas**: campanhas associadas à mensagem. <br>b)**Canal**: o canal de transmissão é “optivo broadmail” constantemente. <br>c) **Código do país**: este campo contém o código do país de origem do remetente. É uma contante com valor &quot;DE&quot;. <br>d) **Ferramenta de entrega**: método de transmissão, sempre &quot;Email&quot;.<br> e) **Nome da mensagem**: o nome da mala direta, conforme configurado no optivo® broadmail. <br>f) **Data de início**: carimbo de data e hora do início dessa correspondência. |
| Tempo pós-clique | (Obrigatório) É necessário para transmitir informações sobre uma ação do destinatário ao optivo® broadmail depois que o destinatário clicou em um link em uma mala direta. |
| Pós-clique no produto | (Obrigatório) É necessário para transmitir informações sobre uma ação do destinatário ao optivo® broadmail depois que o destinatário clicou em um link em uma mala direta. |
| Ação pós-clique | (Obrigatório) É necessário para transmitir informações sobre uma ação do destinatário ao optivo® broadmail depois que o destinatário clicou em um link em uma mala direta. |
| Rejeição permanente | (Obrigatório) Especifica o evento do Adobe Analytics que armazena os dados de rejeição permanente importados do sistema de email. Número de mensagens de email que não foram entregues aos destinatários e são consideradas como não entregues permanentemente. |
| Rejeição temporária | (Obrigatório) Especifica o evento do Adobe Analytics que armazena os dados de rejeição temporária importados do sistema de email. Número de mensagens de email que não foram entregues aos destinatários por causa de um problema de entrega. |
| Clicados | (Obrigatório) Especifica o evento do Adobe Analytics que armazena os dados de emails clicados importados do sistema de email. O evento Clicados permite ver o número de visitantes que clicaram na mensagem de email. |
| Abertos | (Obrigatório) Especifica o evento do Adobe Analytics que armazena os dados de emails abertos importados do sistema de email. O evento Abertos permite ver o número de visitantes que abriram a mensagem de email. |
| Enviado | (Obrigatório) Especifica o evento do Adobe Analytics que armazena os dados de emails enviados importados do sistema de email. O evento Enviado permite ver o número de mensagens de email enviadas. |
| Inscrições canceladas | (Obrigatório) Especifica o evento do Adobe Analytics que armazena os dados de cancelamento de inscrição importados do sistema de email. O evento Inscrições canceladas permite ver quantos visitantes abriram a mensagem de email, mas clicaram no link Cancelar inscrição para recusar futuras mensagens de email de sua organização. |
| Segmentos | Habilitar segmentos existentes para serem usados junto com essa integração (opcional). |
| Solicitações de acesso | Ative os privilégios de acesso recomendados. |
| Coleta de dados | Selecione **Plug-in do JavaScript** se desejar usar o plug-in s_code.js como o modelo de coleção para essa integração. Selecione **Solução automatizada** se desejar usar um modelo de coleta automatizada para essa integração e, depois, especifique os identificadores exclusivos usados nessa integração. Se você selecionar essa opção, especifique os identificadores exclusivos usados nessa integração:<ul><li>Parâmetro da string de consulta da ID de mensagem: esse valor representa a ID da mensagem anexada ao URL da página inicial pelo seu parceiro de email.</li><li>Parâmetro da string de consulta da ID do destinatário: esse valor representa a ID do destinatário anexada ao URL da página de aterrissagem pelo seu parceiro de email.</li></ul> |
| Geração de painel e marcador | Gera automaticamente um painel e marcadores para a integração. |
