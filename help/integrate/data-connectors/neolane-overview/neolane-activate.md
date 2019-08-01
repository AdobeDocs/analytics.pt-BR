---
description: Use o assistente de Configuração dos Conectores de dados da Adobe para configurar a integração.
seo-description: Use o assistente de Configuração dos Conectores de dados da Adobe para configurar a integração.
seo-title: Ativar a integração
title: Ativar a integração
uuid: 93 c 59 f 8 e -3 cf 5-44 c 1-9 a 04-22460 af 93 d 5 d
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a3310ec57ce4c68539f07e0d294c8175742c49dc

---


# Activate the Integration{#activate-the-integration}

Use o assistente de Configuração dos Conectores de dados da Adobe para configurar a integração.

1. Start [Data Connectors](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) and click **[!UICONTROL + Add New]** to [add a new integration](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html).
1. In the **[!UICONTROL Show]** list, select **[!UICONTROL By Name]** and drag the [!DNL ~Partner~] integration to an empty plug-in slot.
1. Preencha o Assistente de integração usando as informações na tabela a seguir:

| Campo | Descrição |
|--- |--- |
| Conjunto de relatórios | O conjunto de relatórios que recebe os dados dessa integração. |
| Nome da integração | Especifique o nome da integração que os Conectores de dados exibem na Lista de integração ativa do conjunto de relatórios. |
| Clicado | O número total de cliques de email. |
| ID da campanha | Armazena a ID de mensagem exclusiva. Isso é armazenado na variável campanha com frequência. |
| Abertos | O número total de aberturas de email. |
| Cliques de pessoa | Número de pessoas que clicaram. |
| Processado | O número total de emails processados. |
| Broadlog ID | Essa ID é uma representação codificada ou numérica de um endereço de email do sistema Neolane. Essa "ID de log de Broadlog" está associada ao comportamento de visitante descendente no site (abandonos da ID do log do carrinho do carrinho, compras etc.) que são coletados no sistema Neolane e podem ser aproveitados para fins de recomercialização. |
| Programado | Número de mensagens de email programadas para entrega. |
| Enviado | Número de mensagens de email enviadas. |
| Total de rejeições | Número de mensagens de email que não foram entregues aos destinatários devido a um problema de entrega. |
| Cliques únicos | Número de cliques distintos. |
| Aberturas únicas | Número de aberturas distintas. |
| Cancelar inscrição | Número de visitantes que abriram a mensagem de email, mas clicavam no link Cancelar inscrição para recusar futuras mensagens de email de sua organização. |
| Segmentos | Essa integração cria os segmentos definidos pelo parceiro exibidos na seção Segmentos do parceiro. Além disso, você pode selecionar segmentos existentes no Nível do conjunto de relatórios para incluir na integração. |
| Solicitações de acesso | Habilite os privilégios de acesso recomendados. |
| Coleção de dados | Select **JavaScript Plug-in** if you want to use the s_code.js plug-in as the collection model for this integration. Select **Automated Solution** if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. Se você selecionar essa opção, especifique os identificadores únicos usados para essa integração: <ul><li>Parâmetro da string de consulta da ID da mensagem: Esse valor representa a ID da mensagem anexada ao URL da página de aterrissagem pelo seu parceiro de e-mail.</li><li>Parâmetro da sequência de consulta da ID do destinatário: Esse valor representa o appendedto da ID do destinatário no URL da página de aterrissagem pelo seu parceiro de e-mail.</li></ul> |
| Geração de painel e marcador | Gerar automaticamente um painel e marcadores para a integração. |