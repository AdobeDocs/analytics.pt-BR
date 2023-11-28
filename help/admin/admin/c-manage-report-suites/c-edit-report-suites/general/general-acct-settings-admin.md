---
description: Descrições de campo das Configurações gerais de conta em Administração do conjunto de relatórios.
title: Configurações gerais da conta
feature: Admin Tools
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
exl-id: f49babb2-8e26-4cc6-b264-b4d7be93f130
source-git-commit: 1e139992b44396caa6220da8dd2f5540cfe88198
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 89%

---

# Configurações gerais da conta

Descrições de campo das Configurações gerais da conta em Administração de um conjunto de relatórios.

**[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]** > **[!UICONTROL Editar configurações]** > **[!UICONTROL Geral]** > **[!UICONTROL Configurações gerais da conta]**

Essas configurações contêm opções de edição para a funcionalidade básica do conjunto de relatórios, como nome e fuso horário.

É um vídeo sobre como configurar as Configurações gerais da conta:

>[!VIDEO](https://video.tv.adobe.com/v/332330/?quality=12)

| Opção | Descrição |
|--- |--- |
| Título do Site | Identifica o site. Dê a cada report suite um título de site único. |
| URL básica | Especifica o site principal do conjunto de relatórios. O URL básico não afeta a filtragem de referenciador. Use [filtros internos do URL](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md) em vez disso. |
| Fuso Horário | Determina a data e a hora associadas aos dados do relatório.  Alterar o fuso horário de um conjunto de relatórios ao vivo cria um pico ou uma lacuna nos dados do relatório. Para minimizar o impacto, a Adobe recomenda alterar os fusos horários durante horários que não sejam de pico a fim de evitar o desvio dos dados.  Por exemplo, se você alterar o fuso horário do conjunto de relatórios de Hora central para Hora do Pacífico às 15:00 horas, a hora atual do conjunto de relatórios mudará para 13:00 horas. Como o relatório já coletou dados para a hora 13:00, os relatórios mostram um pico de tráfego entre 13:00 e 15:00 horas.  Como alternativa, se você alterar o fuso horário do conjunto de relatórios de Hora central para Hora do leste às 15:00 horas, a hora atual do conjunto de relatórios mudará para 16:00 horas. Os relatórios não exibem dados entre 15:00 e 16:00 horas no dia da mudança de hora. |
| Página Padrão | Se o seu [!UICONTROL Relatório de páginas mais populares] contém URLs em vez de nomes de página, essa configuração impede que vários URLs representem a mesma página. Por exemplo, os URLs `https://example.com` e `https://example.com/index.html` normalmente são a mesma página. Você pode remover nomes de arquivo padrão de modo que esses dois URLs sejam exibidos como `https://example.com`.  Se deixado em branco, os seguintes nomes de arquivo são removidos dos URLs: index.htm, index.html, index.cgi, index.asp, default.htm, default.html, default.cgi, default.asp, home.htm, home.html, home.cgi e home.asp.  Para desativar completamente a remoção dos nomes de arquivo, insira um valor que nunca está presente em seus URLs. |
| Substituir o último octeto de endereços IP por 0 | Uma vez habilitado, substitui o último octeto de endereços IP por um zero. Isso ocorre antes do preenchimento de relatórios geográficos e, por isso, pode afetar a precisão deles. |
| Ofuscação de IP | Transforma endereços IP em sequências de caracteres não reconhecidas, removendo-as dos armazenamentos de dados da Adobe. Quando o Obscurecimento de IP estiver ativado, os endereços IP originais são perdidos permanentemente.  <br> **Observação**: os endereços IP são ofuscados em todo o Analytics, incluindo o Data Warehouse. Contudo, a configuração de IP no Target é controlada separadamente, de modo que a configuração não é afetada no Target.<br> Se a ofuscação de IP estiver ativada, todo o processamento necessário, incluindo filtragem/exclusão de IP, regras de bot e pesquisas de geossegmentação, será feito antes que o endereço IP seja ofuscado. Não é necessário alterar nada ao ativar a ofuscação de IP.<ul><li>Marcar **Desativado** deixa o endereço IP nos dados.</li><li>Marcar a opção **Ofuscar endereço IP** altera o IP para dois pontos, seguido de um valor com hash (por exemplo, `::1932023538`).</li><li>Marcar **Remover endereço IP** substitui o endereço IP por `::X.X.X.X` nos dados após a pesquisa geográfica.</li></ul>**Observação**: essa configuração pode exigir alterações nas [regras de bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md) personalizadas ou [exclusões de IP](/help/admin/admin/exclude-ip.md).<br> **Nota**: dados coletados pelo Experience Edge podem ter ofuscação de IP aplicada no Experience Edge via [configuração do fluxo de dados](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=en#@advanced-options). Se a ofuscação de IP for aplicada na borda, ela já será ofuscada, pois atinge o Analytics, afetando as regras de bot e as pesquisas geográficas. |
| Armazenamento de ID de transação | Permite usar fontes de dados da [ID de transação](/help/import/data-sources/transactionid.md). |
| Habilitar o Data Warehouse | Habilita a interface do usuário do Data Warehouse em Analytics > Ferramentas > Data Warehouse. |
| Opção de CEP | Permite especificar o CEP em vez de usar o que a pesquisa de IP geográfico produz. |
| Suporte a caracteres com vários bytes | O suporte a caracteres multibyte armazena caracteres no conjunto de relatórios usando UTF-8. No recebimento, o sistema converte os dados do conjunto de caracteres de sua página da Web para o conjunto de caracteres UTF-8, de modo a permitir o uso de qualquer idioma em seus relatórios de marketing. Entre em contato com a Equipe de conta do Adobe ou com o Atendimento ao cliente para alterar o suporte a caracteres multibyte de um conjunto de relatórios existente. |
| Ativado | Especifica se este conjunto de relatórios está ativado ou não. |
| Moeda de base | Permite especificar a [moeda](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/currencycode.html?lang=pt-BR) base para este conjunto de relatórios. |
| ID da organização | A ID associada à empresa provisionada pela Experience Cloud. A ID é uma sequência de 24 caracteres alfanuméricos seguidos por (e deve incluir) @AdobeOrg. |
