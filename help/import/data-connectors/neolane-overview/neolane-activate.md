---
description: Use o Assistente de configuração dos conectores de dados da Adobe para configurar a integração.
seo-description: Use o Assistente de configuração dos conectores de dados da Adobe para configurar a integração.
seo-title: Ativar a integração
title: Ativar a integração
uuid: 93c59f8e-3cf5-44c1-9a04-22460af93d5d
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

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
| Clicado | Número total de cliques em email. |
| ID da campanha | Armazena a ID de mensagem exclusiva. Geralmente, isso é armazenado na variável da campanha. |
| Aberto | O número total de e-mails abertos. |
| Cliques de pessoa | Número de pessoas que clicaram. |
| Processado | Número total de emails processados. |
| Broadlog ID | Essa ID é uma representação codificada ou numérica de um endereço de email do sistema Neolane. Essa "ID da Broadlog" está associada ao comportamento de visitantes downstream no site (abandonos, compras, etc.) que é absorvida pelo sistema Neolane e pode ser potenciada para fins de recomercialização. |
| Programado | Número de mensagens de email programadas para entrega. |
| Enviados | Número de mensagens de email enviadas. |
| Total de rejeições | Número de mensagens de email que não foram entregues aos destinatários devido a um problema de entrega. |
| Cliques únicos | Número de cliques distintos. |
| Aberturas únicas | Número de aberturas distintas. |
| Inscrito | Número de visitantes que abriram a mensagem de email, mas clicaram no link Cancelar inscrição para recusar futuras mensagens de email de sua organização. |
| Segmentos | Essa integração cria os segmentos definidos pelo parceiro exibidos na seção Segmentos do parceiro. Além disso, você pode selecionar segmentos existentes no nível do conjunto de relatórios para incluir na integração. |
|  Solicitações de acesso | Ative os privilégios de acesso recomendados. |
| Coleta de dados | Selecione Plug-in **de** JavaScript se desejar usar o plug-in s_code.js como o modelo de coleção para essa integração. Selecione Solução **** automatizada se desejar usar um modelo de coleta automatizada para essa integração e especifique os identificadores exclusivos usados para essa integração. Se você selecionar essa opção, especifique os identificadores exclusivos usados para essa integração: <ul><li>Parâmetro da string de consulta da ID da mensagem: Esse valor representa a ID da mensagem anexada ao URL da página inicial pelo seu parceiro de email.</li><li>Parâmetro da string de consulta da ID do destinatário: Esse valor representa a ID do destinatário anexada ao URL da página inicial pelo seu parceiro de email.</li></ul> |
| Geração de painel e marcador | Gerar automaticamente um painel e marcadores para a integração. |
