---
description: Use o Assistente de configuração do Data Connectors da Adobe para configurar a integração.
title: Ativar a integração
uuid: 9084b691-291d-49f7-9fa4-abda507e060d
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
| UUID de integração | Especifique sua UUID de integração do DreamMail. |
| Nome do cliente | Especifique o nome do cliente do DreamMail. |
| Nome do site | Especifique o nome do site do DreamMail. |
| Rejeições | Número de mensagens de email que não foram entregues aos destinatários por causa de um problema de entrega. |
| Entregues | Número de entregas de mensagem bem-sucedidas. |
| Erros de entrega | Entregas de mensagem malsucedidas. |
| Aberturas de HTML | Número de visitantes que abriram a mensagem de email. |
| Inválidos | Número de endereços de email inválidos. |
| Campanha | ID da campanha de marketing. |
| Encaminhamentos | O evento Clicados permite ver o número de visitantes que clicaram na mensagem de email. |
| eVar de email | Um endereço de email do sistema DreamMail. Essa &quot;eVar de email&quot; está associada ao comportamento downstream de visitantes no site (abandonos de carrinho, compras etc.) que é extraído para o sistema DreamMail e pode ser aproveitado para fins de remarketing. |
| Evento Em destaque | Evento que pode ser exportado em segmentos de remarketing. |
| Compras em destaque | Evento que pode ser exportado em segmentos de remarketing. |
| Valor dos destaques | Evento de receita que pode ser exportado em segmentos de remarketing. |
| Total de cliques | O evento Clicados permite ver o número de visitantes que clicaram na mensagem de email. |
| Segmentos | Essa integração cria os segmentos definidos pelo parceiro exibidos na seção Segmentos do parceiro. Além disso, você pode selecionar segmentos existentes no nível do conjunto de relatórios para incluir na integração. |
| Solicitações de acesso | Ative os privilégios de acesso recomendados. |
| Coleta de dados | Selecione **Plug-in do JavaScript** se desejar usar o plug-in s_code.js como o modelo de coleção para essa integração (consulte ). Selecione **Solução automatizada** se desejar usar um modelo de coleta automatizada para essa integração e, depois, especifique os identificadores exclusivos usados nessa integração. Se você selecionar essa opção, especifique os identificadores exclusivos usados nessa integração:<ul><li>Parâmetro da string de consulta da ID da mensagem: esse valor representa a ID da mensagem anexada ao URL da página inicial pelo seu parceiro de email.</li><li>Parâmetro da string de consulta da ID do destinatário: esse valor representa a ID do destinatário anexada ao URL da página de aterrissagem pelo seu parceiro de email.</li></ul> |
| Geração de painel e marcador | Gera automaticamente um painel e marcadores para a integração. |
