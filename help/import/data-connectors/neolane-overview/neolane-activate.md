---
description: Use o Assistente de configuração do Data Connectors da Adobe para configurar a integração.
title: Ativar a integração
uuid: 93c59f8e-3cf5-44c1-9a04-22460af93d5d
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
| Clicados | Número total de cliques em emails. |
| ID da campanha | Armazena a ID de mensagem exclusiva. É frequentemente armazenado na variável da campanha. |
| Abertos | O número total de aberturas de emails. |
| Cliques de pessoas | Número de pessoas que clicaram. |
| Processado | Número total de emails processados. |
| ID de broadlog | Essa ID é uma representação codificada ou numérica de um endereço de email do sistema Neolane. Essa &quot;Broadlog ID&quot; está associada ao comportamento downstream de visitantes no site (abandonos, compras, etc.) que é extraído para o sistema Neolane e pode ser aproveitado para fins de remarketing. |
| Programado | Número de mensagens de email programadas para entrega. |
| Enviado | Número de mensagens de email enviadas. |
| Total de rejeições | Número de mensagens de email que não foram entregues aos destinatários por causa de um problema de entrega. |
| Cliques únicos | Número de cliques distintos. |
| Aberturas únicas | Número de aberturas distintas. |
| Inscrições canceladas | Número de visitantes que abriram a mensagem de email, mas clicaram no link Cancelar inscrição para recusar futuras mensagens de email de sua organização. |
| Segmentos | Essa integração cria os segmentos definidos pelo parceiro exibidos na seção Segmentos do parceiro. Além disso, você pode selecionar segmentos existentes no nível do conjunto de relatórios para incluir na integração. |
| Solicitações de acesso | Ative os privilégios de acesso recomendados. |
| Coleta de dados | Selecione **Plug-in do JavaScript** se desejar usar o plug-in s_code.js como o modelo de coleção para essa integração. Selecione **Solução automatizada** se desejar usar um modelo de coleta automatizada para essa integração e, depois, especifique os identificadores exclusivos usados nessa integração. Se você selecionar essa opção, especifique os identificadores exclusivos usados nessa integração: <ul><li>Parâmetro da string de consulta da ID da mensagem: esse valor representa a ID da mensagem anexada ao URL da página inicial pelo seu parceiro de email.</li><li>Parâmetro da string de consulta da ID do destinatário: esse valor representa a ID do destinatário anexada ao URL da página de aterrissagem pelo seu parceiro de email.</li></ul> |
| Geração de painel e marcador | Gera automaticamente um painel e marcadores para a integração. |
