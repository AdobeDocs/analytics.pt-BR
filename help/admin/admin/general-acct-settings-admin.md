---
description: Descrições de campo das Configurações gerais de conta em Administração do conjunto de relatórios.
title: Configurações gerais da conta
topic: Admin tools
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
translation-type: tm+mt
source-git-commit: fde56828eafad8b7668a854170cd9ee3a8c7ed6b

---


# Configurações gerais da conta

Descrições de campo das Configurações gerais da conta em Administração de um conjunto de relatórios.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL General Account Settings]**

Essas configurações contêm opções de edição para a funcionalidade básica do conjunto de relatórios, como nome e fuso horário.

| Opção | Descrição |
|--- |--- |
| Título do Site | Identifica o site. Dá a cada conjunto de relatórios um título de site exclusivo. |
| URL básica | Especifica o site principal do conjunto de relatórios. O URL básico não afeta a filtragem de referenciador. Use [ filtros internos do URL](/help/admin/admin/internal-url-filter-admin.md) em vez disso. |
| Fuso Horário | Determina a data e a hora associadas aos dados do relatório.  Alterar o fuso horário de um conjunto de relatórios ao vivo cria um pico ou uma lacuna nos dados do relatório. Para minimizar o impacto, a Adobe recomenda alterar os fusos horários durante horários que não sejam de pico a fim de evitar o desvio dos dados.  Por exemplo, se você alterar o fuso horário do conjunto de relatórios de Hora central para Hora do Pacífico às 15:00 horas, a hora atual do conjunto de relatórios mudará para 13:00 horas. Como o relatório já coletou dados para a hora 13:00, os relatórios mostram um pico de tráfego entre 13:00 e 15:00 horas.  Como alternativa, se você alterar o fuso horário do conjunto de relatórios de Hora central para Hora do leste às 15:00 horas, a hora atual do conjunto de relatórios mudará para 16:00 horas. Os relatórios não exibem dados entre 15:00 e 16:00 horas no dia da mudança de hora. |
| Página Padrão | If your [!UICONTROL Most Popular Pages] report contains URLs rather than page names, this setting prevents multiple URLs from representing the same page. Por exemplo, os URLs `https://mysite.com` e `https://mysite.com/index.html` normalmente são a mesma página. Você pode remover nomes de arquivo padrão de modo que esses dois URLs sejam exibidos como `https://mysite.com`.  Se deixado em branco, os seguintes nomes de arquivo são removidos dos URLs: index.htm, index.html, index.cgi, index.asp, default.htm, default.html, default.cgi, default.asp, home.htm, home.html, home.cgi e home.asp.  Para desativar completamente a remoção dos nomes de arquivo, insira um valor que nunca está presente em seus URLs. |
| Substituir o último octeto de endereços IP por 0 | A remoção do último octeto é realizada antes da filtragem de IP. Assim, o último octeto será substituído por um 0, e as regras de exclusão de IP devem ser atualizadas para corresponder os endereços IP com um zero no final. A correspondência de * deve corresponder a 0. Marcar essa opção indica que o endereço IP foi alterado antes de ser processado. Por exemplo, o endereço de IP 134.123.567.780 é alterado para 134.123.567.0. Os dados de segmentação geográfica não serão tão exatos como seriam se o endereço inteiro de IP fosse usado. Especificamente, a precisão da cidade será mais afetada que a precisão do país ou da região. Tanto as regras de bot como as regras VISTA são afetadas, pois elas não podem acessar o endereço inteiro de IP. Além disso, qualquer regra de processamento que seja baseada em um IP (incluindo regrais de canais de marketing e regras de processamento de conjuntos de relatórios), será afetada por essa configuração.<br>**Observação **: essa configuração fica habilitada por padrão para qualquer conjunto de relatórios criado no Data Center de Londres depois de janeiro de 2019, mas somente se as configurações desse conjunto de relatórios tiverem sido copiadas de um modelo listado no Admin Console. Os conjuntos de relatórios cujas configurações estiverem duplicadas de outros conjuntos de relatórios herdarão todas as configurações do conjunto selecionado. |
| Ofuscação de IP | Transforma endereços IP em sequências de caracteres não reconhecidas, removendo-as dos armazenamentos de dados da Adobe. Quando o Obscurecimento de IP estiver ativado, os endereços IP originais são perdidos permanentemente.<br>**Observação **: os endereços IP são ofuscados em todo o Analytics, incluindo o Data Warehouse. Contudo, a configuração de IP no Target é controlada separadamente, de modo que a configuração não é afetada no Target.<br>Se a ofuscação de IP estiver ativada, a exclusão de IP ocorrerá antes de o endereço IP ser ofuscado, de modo que os clientes não precisam fazer qualquer alteração ao ativar a ofuscação de IP.<br>Marcar** Desativado **deixa o endereço IP nos dados.<br>Marcar** Ofuscar endereço IP **altera o IP para um valor com hash (por exemplo, 234abc6493872038).<br>Marcar** Remover endereço IP **substitui o endereço IP por x.x.x.x nos dados após a pesquisa geográfica.<br>**Observação**: essa configuração pode exigir alterações nas [regras de bot](/help/admin/admin/bot-removal/bot-rules.md) personalizadas ou[ exclusões de IP](/help/admin/admin/exclude-ip.md). |
| Armazenamento de ID de transação | Permite usar fontes de dados da [ID de transação](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md). |
| Ativar Ad Hoc Analysis | Indica se o conjunto de relatórios em questão é exibido como um conjunto de relatórios disponível na Ad Hoc Analysis. Use essa configuração para limitar quais conjuntos de relatórios serão exibidos como uma opção para a Ad Hoc Analysis. Por exemplo, é possível desativar a Ad Hoc Analysis para desenvolvimento e conjuntos de relatórios de QA. |
| Habilitar o Data Warehouse | Habilita a interface do usuário do Data Warehouse em Analytics > Ferramentas > Data Warehouse. |
