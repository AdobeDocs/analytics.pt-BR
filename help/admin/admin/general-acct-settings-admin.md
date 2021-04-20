---
description: Descrições de campo das Configurações gerais de conta em Administração do conjunto de relatórios.
title: Configurações gerais da conta
feature: Admin Tools
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
exl-id: f49babb2-8e26-4cc6-b264-b4d7be93f130
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 88%

---

# Configurações gerais da conta

Descrições de campo das Configurações gerais da conta em Administração de um conjunto de relatórios.

**[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]** > **[!UICONTROL Editar configurações]** > **[!UICONTROL Geral]** > **[!UICONTROL Configurações gerais da conta]**

Essas configurações contêm opções de edição para a funcionalidade básica do conjunto de relatórios, como nome e fuso horário.

| Opção | Descrição |
|--- |--- |
| Título do Site | Identifica o site. Dê a cada report suite um título de site único. |
| URL básica | Especifica o site principal do conjunto de relatórios. O URL básico não afeta a filtragem de referenciador. Use [filtros internos do URL](/help/admin/admin/internal-url-filter-admin.md) em vez disso. |
| Fuso Horário | Determina a data e a hora associadas aos dados do relatório.  Alterar o fuso horário de um conjunto de relatórios ao vivo cria um pico ou uma lacuna nos dados do relatório. Para minimizar o impacto, a Adobe recomenda alterar os fusos horários durante horários que não sejam de pico a fim de evitar o desvio dos dados.  Por exemplo, se você alterar o fuso horário do conjunto de relatórios de Hora central para Hora do Pacífico às 15:00 horas, a hora atual do conjunto de relatórios mudará para 13:00 horas. Como o relatório já coletou dados para a hora 13:00, os relatórios mostram um pico de tráfego entre 13:00 e 15:00 horas.  Como alternativa, se você alterar o fuso horário do conjunto de relatórios de Hora central para Hora do leste às 15:00 horas, a hora atual do conjunto de relatórios mudará para 16:00 horas. Os relatórios não exibem dados entre 15:00 e 16:00 horas no dia da mudança de hora. |
| Página Padrão | Se o seu [!UICONTROL Relatório de páginas mais populares] contém URLs em vez de nomes de página, essa configuração impede que vários URLs representem a mesma página. Por exemplo, os URLs `https://example.com` e `https://example.com/index.html` normalmente são a mesma página. Você pode remover nomes de arquivo padrão de modo que esses dois URLs sejam exibidos como `https://example.com`.  Se deixado em branco, os seguintes nomes de arquivo são removidos dos URLs: index.htm, index.html, index.cgi, index.asp, default.htm, default.html, default.cgi, default.asp, home.htm, home.html, home.cgi e home.asp.  Para desativar completamente a remoção dos nomes de arquivo, insira um valor que nunca está presente em seus URLs. |
| Substituir o último octeto de endereços IP por 0 | A remoção do último octeto é feita antes que qualquer processamento seja feito na ocorrência, incluindo antes da filtragem/exclusão de IP, antes de verificar as regras de bot, antes de pesquisas de segmentação geográfica etc. Assim, o último octeto será substituído por um 0, e as regras de exclusão de IP devem ser atualizadas para corresponder os endereços IP com um zero no final. A correspondência de * deve corresponder a 0. Por exemplo, o endereço de IP 11.22.33.44 é alterado para 11.22.33.0. Os dados de segmentação geográfica não serão tão exatos como seriam se o endereço inteiro de IP fosse usado. Especificamente, a precisão da cidade será mais afetada que a precisão do país ou da região. Tanto as regras de bot como as regras VISTA são afetadas, pois elas não podem acessar o endereço inteiro de IP. Além disso, qualquer regra de processamento que seja baseada em um IP (incluindo regrais de canais de marketing e regras de processamento de conjuntos de relatórios), será afetada por essa configuração. <br> **Observação**: essa configuração fica habilitada por padrão para qualquer conjunto de relatórios criado no Data Center de Londres depois de janeiro de 2019, mas somente se as configurações desse conjunto de relatórios tiverem sido copiadas de um modelo listado no Admin Console. Os conjuntos de relatórios cujas configurações estiverem duplicadas de outros conjuntos de relatórios herdarão todas as configurações do conjunto selecionado. |
| Ofuscação de IP | Transforma endereços IP em sequências de caracteres não reconhecidas, removendo-as dos armazenamentos de dados da Adobe. Quando o Obscurecimento de IP estiver ativado, os endereços IP originais são perdidos permanentemente.  <br> **Observação**: os endereços IP são ofuscados em todo o Analytics, incluindo o Data Warehouse. Contudo, a configuração de IP no Target é controlada separadamente, de modo que a configuração não é afetada no Target.<br> Se a ofuscação de IP estiver ativada, todo o processamento necessário, incluindo filtragem/exclusão de IP, regras de bot e pesquisas de geosegmentação, será feito antes que o endereço IP seja ofuscado. Não é necessário alterar nada ao ativar a ofuscação de IP.<ul><li>Marcar **Desativado** deixa o endereço IP nos dados.</li><li>Marcar **Ofuscar endereço IP** altera o IP para dois pontos, seguido de um valor com hash (por exemplo, `::1932023538`).</li><li>Marcar **Remover endereço IP**`::X.X.X.X` substitui o endereço IP por nos dados após a pesquisa geográfica.</li></ul>**Observação**: essa configuração pode exigir alterações nas [regras de bot](/help/admin/admin/bot-removal/bot-rules.md) personalizadas ou [exclusões de IP](/help/admin/admin/exclude-ip.md). |
| Armazenamento de ID de transação | Permite usar fontes de dados da [ID de transação](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md). |
| Habilitar o Data Warehouse | Habilita a interface do usuário do Data Warehouse em Analytics > Ferramentas > Data Warehouse. |
