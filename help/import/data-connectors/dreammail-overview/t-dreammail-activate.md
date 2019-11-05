---
description: Use o Assistente de configuração dos conectores de dados da Adobe para configurar a integração.
seo-description: Use o Assistente de configuração dos conectores de dados da Adobe para configurar a integração.
seo-title: Ativar a integração
title: Ativar a integração
uuid: 9084b691-291d-49f7-9fa4-abda507e060d
translation-type: tm+mt
source-git-commit: bc46011a48aa18e33ba6f1912223857f5a664f35

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
| UUID de integração | Especifique seu UUID de integração do DreamMail. |
| Nome do cliente | Especifique o nome do cliente do DreamMail. |
| Nome do site | Especifique o nome do site do DreamMail. |
| Rejeitar Voltas | Número de mensagens de email que não foram entregues aos destinatários devido a um problema de entrega. |
| Entregue | Número de entregas de mensagem bem-sucedidas. |
| Erros de entrega | Entregas de mensagem malsucedidas. |
| Abertura de HTML | Número de visitantes que abriram a mensagem de email. |
| Inválidos | Número de endereços de email inválidos. |
| Campanha | ID da campanha de marketing. |
| Enviar várias | O evento Clicado permite que você veja o número de visitantes que clicaram na mensagem de email. |
| Email eVar | Um endereço de email do sistema DreamMail. Esta "eVar de email" está associada ao comportamento de visitantes downstream no site (abandonos de carrinho, compras etc.) que é extraída para o sistema DreamMail e pode ser aproveitada para fins de remarketing. |
| Evento Spotlight | Evento que pode ser exportado em segmentos de recomercialização. |
| Compras em destaque | Evento que pode ser exportado em segmentos de recomercialização. |
| Valor do destaque | Evento de receita que pode ser exportado em segmentos de recomercialização. |
| Total de cliques | O evento Clicado permite que você veja o número de visitantes que clicaram na mensagem de email. |
| Segmentos | Essa integração cria os segmentos definidos pelo parceiro exibidos na seção Segmentos do parceiro. Além disso, você pode selecionar segmentos existentes no nível do conjunto de relatórios para incluir na integração. |
|  Solicitações de acesso | Ative os privilégios de acesso recomendados. |
| Coleta de dados | Selecione Plug-in **de** JavaScript se desejar usar o plug-in s_code.js como o modelo de coleção para essa integração (consulte ). Selecione Solução **** automatizada se desejar usar um modelo de coleta automatizada para essa integração e especifique os identificadores exclusivos usados para essa integração. Se você selecionar essa opção, especifique os identificadores exclusivos usados para essa integração:<ul><li>Parâmetro da string de consulta da ID da mensagem: Esse valor representa a ID da mensagem anexada ao URL da página inicial pelo seu parceiro de email.</li><li>Parâmetro da string de consulta da ID do destinatário: Esse valor representa a ID do destinatário anexada ao URL da página inicial pelo seu parceiro de email.</li></ul> |
| Geração de painel e marcador | Gerar automaticamente um painel e marcadores para a integração. |
