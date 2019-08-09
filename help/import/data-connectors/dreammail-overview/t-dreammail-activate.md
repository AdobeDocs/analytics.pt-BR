---
description: Use o assistente de Configuração dos Conectores de dados da Adobe para configurar a integração.
seo-description: Use o assistente de Configuração dos Conectores de dados da Adobe para configurar a integração.
seo-title: Ativar a integração
title: Ativar a integração
uuid: 9084 b 691-291 d -49 f 7-9 fa 4-abda 507 e 060 d
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
| UUID de integração | Especifique o UUID de integração do dreammail. |
| Nome do cliente | Especifique o Nome do cliente dreammail. |
| Nome do site | Especifique o Nome do site do dreammail. |
| Devoluções de rejeição | Número de mensagens de email que não foram entregues aos destinatários devido a um problema de entrega. |
| Entregue | Número de entregas de mensagem bem-sucedidas. |
| Erros de entrega | Falha de entregas de mensagens. |
| Aberturas HTML | Número de visitantes que abriram a mensagem de email. |
| Inválidos | Número de endereços de email inválidos. |
| Campanha | ID da campanha de marketing. |
| Passar de | O evento Clicado permite ver o número de visitantes que clicaram na mensagem de e-mail. |
| Email eVar | Um endereço de email do sistema dreammail. Essa "evar de email" está associada ao comportamento de visitante descendente no site (abandonos de carrinho, compras etc.) que são coletados no sistema dreammail e podem ser aproveitados para fins de recomercialização. |
| Evento de destaque | Evento que pode ser exportado em segmentos de recomercialização. |
| Compras de destaque | Evento que pode ser exportado em segmentos de recomercialização. |
| Valor de destaque | Evento de receita que pode ser exportado em segmentos de recomercialização. |
| Totalclicks | O evento Clicado permite ver o número de visitantes que clicaram na mensagem de e-mail. |
| Segmentos | Essa integração cria os segmentos definidos pelo parceiro exibidos na seção Segmentos do parceiro. Além disso, você pode selecionar segmentos existentes no Nível do conjunto de relatórios para incluir na integração. |
| Solicitações de acesso | Habilite os privilégios de acesso recomendados. |
| Coleção de dados | Selecione **o plug-in javascript** caso deseje usar o plug-in s_ code. js como o modelo de coleta dessa integração (consulte). Selecione **Solução automatizada** se quiser usar um modelo de coleção automatizado para essa integração e especifique os identificadores exclusivos usados para essa integração. Se você selecionar essa opção, especifique os identificadores únicos usados para essa integração:<ul><li>Parâmetro da string de consulta da ID da mensagem: Esse valor representa a ID da mensagem anexada ao URL da página de aterrissagem pelo seu parceiro de e-mail.</li><li>Parâmetro da sequência de consulta da ID do destinatário: Esse valor representa o appendedto da ID do destinatário no URL da página de aterrissagem pelo seu parceiro de e-mail.</li></ul> |
| Geração de painel e marcador | Gerar automaticamente um painel e marcadores para a integração. |