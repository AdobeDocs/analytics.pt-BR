---
description: Use o assistente de Configuração dos Conectores de dados da Adobe para configurar a integração.
seo-description: Use o assistente de Configuração dos Conectores de dados da Adobe para configurar a integração.
seo-title: Ativar a integração
title: Ativar a integração
uuid: 0 a 5 d 2 d 45-5133-4259-96 ce-c 992 a 1 e 314 ee
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a3310ec57ce4c68539f07e0d294c8175742c49dc

---


# Activate the Integration {#activate-the-integration}

Use o assistente de Configuração dos Conectores de dados da Adobe para configurar a integração.

1. Start [Data Connectors](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) and click **[!UICONTROL + Add New]** to [add a new integration](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html).
1. In the **[!UICONTROL Show]** list, select **[!UICONTROL By Name]** and drag the [!DNL ~Partner~] integration to an empty plug-in slot.
1. Preencha o Assistente de integração usando as informações na tabela a seguir:

| Campo | Descrição |
|--- |--- |
| Conjunto de relatórios | O conjunto de relatórios que recebe os dados dessa integração. |
| Nome da integração | Especifique o nome da integração que os Conectores de dados exibem na Lista de integração ativa do conjunto de relatórios. |
| ID da Conta | Especifique a ID da conta Aprimo. |
| Recipient ID | Essa ID é uma representação codificada ou numérica de um endereço de email do sistema Aprimo. Essa «ID do destinatário» é associada ao comportamento de visitante descendente na ID do destinatário do site (abandonos de carrinho, compras etc.) que são coletados no sistema Aprimo e podem ser aproveitados para fins de recomercialização. |
| Clicado | (Obrigatório) Especifique o evento do Adobe Analytics que armazena os dados clicados por email importados do sistema de email. O evento Clicado permite ver o número de visitantes que clicaram na mensagem de e-mail. |
| ID da mensagem | (Obrigatório) Armazena a ID de correspondência exclusiva. |
| Abertos | (Obrigatório) Especifique o evento do Adobe Analytics que armazena os dados abertos por email importados do sistema de email. O evento Aberto permite que você veja o número de visitantes que abriram a mensagem de e-mail. |
| Recipient ID | (Obrigatório) Armazena a ID de visitante exclusiva. |
| Enviado | (Obrigatório) Especifique o evento do Adobe Analytics que armazena os dados enviados por email importados do sistema de email. O evento Enviado permite que você veja o número de mensagens de email enviadas. |
| Devoluções | (Obrigatório) Especifique o evento do Adobe Analytics que armazena o e-mail Total de dados importados do sistema de email. O evento Total de rejeições permite ver o número de mensagens de email que não foram entregues aos destinatários devido a um problema de entrega. |
| Cancelar inscrição | (Obrigatório) Especifique o evento do Adobe Analytics que armazena o email Cancelar assinatura de dados importados do sistema de email. O evento Cancelar inscrição permite ver o número de visitantes que abriram a mensagem de email, mas clicaram no link Cancelar inscrição para recusar futuras mensagens de email de sua organização. |
| Segmentos | Essa integração cria os segmentos definidos pelo parceiro exibidos na seção Segmentos do parceiro. Além disso, você pode selecionar segmentos existentes no Nível do conjunto de relatórios para incluir na integração. |
| Solicitações de acesso | Habilite os privilégios de acesso recomendados. |
| Coleção de dados | Select **JavaScript Plug-in** if you want to use the s_code.js plug-in as the collection model for this integration. |
Select **Automated Solution** if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. Se você selecionar essa opção, especifique os identificadores únicos usados para essa integração:
<ul><li>Parâmetro da string de consulta da ID da mensagem: Esse valor representa a ID da mensagem anexada ao URL da página de aterrissagem pelo seu parceiro de e-mail.</li>
<li>Parâmetro da sequência de consulta da ID do destinatário: Esse valor representa o appendedto da ID do destinatário no URL da página de aterrissagem pelo seu parceiro de e-mail.</li></ul>|
| Painel e Geração de marcador | Gerar automaticamente um painel e marcadores para a integração.|
