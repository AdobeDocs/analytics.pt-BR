---
description: Use o Assistente de configuração do Data Connectors da Adobe para configurar a integração.
title: Ativar a integração
uuid: 0a5d2d45-5133-4259-96ce-c992a1e314ee
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
| ID da Conta | Especifique a ID de conta Aprimo. |
| ID de destinatário | Essa ID é uma representação codificada ou numérica de um endereço de email do sistema Aprimo. Essa &quot;ID do destinatário&quot; está associada ao comportamento de downstream do visitante no site ID do destinatário (abandonos de carrinho, compras etc.) que é extraída para o sistema Aprimo e pode ser aproveitada para fins de remarketing. |
| Clicados | (Obrigatório) Especifique o evento do Adobe Analytics que armazena os dados de email Clicados importados do sistema de email. O evento Clicados permite ver o número de visitantes que clicaram na mensagem de email. |
| ID de mensagem | (Obrigatório) Armazena a ID de correspondência exclusiva. |
| Abertos | (Obrigatório) Especifica o evento do Adobe Analytics que armazena os dados de emails abertos importados do sistema de email. O evento Abertos permite ver o número de visitantes que abriram a mensagem de email. |
| ID de destinatário | (Obrigatório) Armazena a ID de visitante único. |
| Enviados | (Obrigatório) Especifica o evento do Adobe Analytics que armazena os dados de emails enviados importados do sistema de email. O evento Enviado permite ver o número de mensagens de email enviadas. |
| Devoluções | (Obrigatório) Especifique o evento do Adobe Analytics que armazena os dados de email Total de rejeições importados do sistema de email. O evento Total-Bounces permite ver a quantidade de mensagens de email que não foram entregues aos destinatários devido a um problema de entrega. |
| Inscrições canceladas | (Obrigatório) Especifica o evento do Adobe Analytics que armazena os dados de cancelamento de inscrição importados do sistema de email. O evento Inscrições canceladas permite ver quantos visitantes abriram a mensagem de email, mas clicaram no link Cancelar inscrição para recusar futuras mensagens de email de sua organização. |
| Segmentos | Essa integração cria os segmentos definidos pelo parceiro exibidos na seção Segmentos do parceiro. Além disso, você pode selecionar segmentos existentes no nível do conjunto de relatórios para incluir na integração. |
| Solicitações de acesso | Ative os privilégios de acesso recomendados. |
| Coleta de dados | Selecione **Plug-in do JavaScript** se desejar usar o plug-in s_code.js como o modelo de coleção para essa integração. |
Selecione **Solução automatizada** se desejar usar um modelo de coleta automatizada para essa integração e, depois, especifique os identificadores exclusivos usados nessa integração. Se você selecionar essa opção, especifique os identificadores exclusivos usados nessa integração:
<ul><li>Parâmetro da string de consulta da ID da mensagem: esse valor representa a ID da mensagem anexada ao URL da página inicial pelo seu parceiro de email.</li>
<li>Parâmetro da string de consulta da ID do destinatário: esse valor representa a ID do destinatário anexada ao URL da página de aterrissagem pelo seu parceiro de email.</li></ul>|
|Geração de painel e marcador|Gerar automaticamente um painel e marcadores para a integração.|
