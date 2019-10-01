---
description: Use o Assistente de configuração dos conectores de dados da Adobe para configurar a integração.
seo-description: Use o Assistente de configuração dos conectores de dados da Adobe para configurar a integração.
seo-title: Ativar a integração
title: Ativar a integração
uuid: 0a5d2d45-5133-4259-96ce-c992a1e314ee
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Ativar a integração {#activate-the-integration}

Use o Assistente de configuração dos conectores de dados da Adobe para configurar a integração.

1. Inicie os Conectores [de](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) dados e clique em **[!UICONTROL + Adicionar novo]** para [adicionar uma nova integração](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html).
1. Na lista **[!UICONTROL Exibir]** , selecione **[!UICONTROL Por nome]** e arraste a integração do [!DNL ~parceiro~] para um slot de plug-in vazio.
1. Complete o Assistente de integração usando as informações na tabela a seguir:

| Campo | Descrição |
|--- |--- |
| Conjunto de relatórios | O conjunto de relatórios que recebe os dados dessa integração. |
| Nome da integração | Especifique o nome da integração que os Conectores de dados exibem na lista Integração ativa do conjunto de relatórios. |
| ID da Conta | Especifique sua ID de conta Aprimo. |
| Recipient ID | Esta ID é uma representação codificada ou numérica de um endereço de email do sistema Aprimo. Essa "ID do destinatário" está associada ao comportamento do visitante downstream na ID do destinatário do site (abandonos de carrinho, compras etc.) que é puxada para o sistema Aprimo e pode ser aproveitada para fins de recomercialização. |
| Clicado | (Obrigatório) Especifique o evento do Adobe Analytics que armazena os dados de e-mail clicados importados do sistema de e-mail. O evento Clicado permite que você veja o número de visitantes que clicaram na mensagem de email. |
| ID da mensagem | (Obrigatório) Armazena a ID de endereçamento exclusiva. |
| Aberto | (Obrigatório) Especifique o evento do Adobe Analytics que armazena os dados Abertos por email importados do sistema de email. O evento Aberto permite que você veja o número de visitantes que abriram a mensagem de email. |
| Recipient ID | (Obrigatório) Armazena a ID de visitante único. |
| Enviados | (Obrigatório) Especifique o evento do Adobe Analytics que armazena os dados de email enviados importados do sistema de email. O evento Enviado permite que você veja o número de mensagens de email enviadas. |
| Devoluções | (Obrigatório) Especifique o evento do Adobe Analytics que armazena os dados de Rejeições totais de email importados do sistema de email. O evento Total-Rejeições permite que você veja o número de mensagens de email que não foram entregues aos destinatários devido a um problema de entrega. |
| Inscrito | (Obrigatório) Especifique o evento do Adobe Analytics que armazena os dados de e-mail Cancelar assinatura importados do sistema de e-mail. O evento Cancelado de inscrição permite que você veja o número de visitantes que abriram a mensagem de email, mas clicaram no link Cancelar inscrição para recusar futuras mensagens de email de sua organização. |
| Segmentos | Essa integração cria os segmentos definidos pelo parceiro exibidos na seção Segmentos do parceiro. Além disso, você pode selecionar segmentos existentes no nível do conjunto de relatórios para incluir na integração. |
|  Solicitações de acesso | Ative os privilégios de acesso recomendados. |
| Coleta de dados | Selecione Plug-in **de** JavaScript se desejar usar o plug-in s_code.js como o modelo de coleção para essa integração. |
Selecione Solução **** automatizada se desejar usar um modelo de coleta automatizada para essa integração e especifique os identificadores exclusivos usados para essa integração. Se você selecionar essa opção, especifique os identificadores exclusivos usados para essa integração:
<ul><li>Parâmetro da string de consulta da ID da mensagem: Esse valor representa a ID da mensagem anexada ao URL da página inicial pelo seu parceiro de email.</li>
<li>Parâmetro da string de consulta da ID do destinatário: Esse valor representa a ID do destinatário anexada ao URL da página inicial pelo seu parceiro de email.</li></ul>||Geração de painel e marcador|Gerar automaticamente um painel e marcadores para a integração.|
