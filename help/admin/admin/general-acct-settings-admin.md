---
description: Descrições de campo das Configurações gerais da conta em Administração do conjunto de relatórios.
seo-description: Descrições de campo das Configurações gerais de conta em Administração do conjunto de relatórios.
seo-title: Configurações gerais da conta
solution: Analytics
title: Configurações gerais da conta
topic: Ferramentas administrativas
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
translation-type: tm+mt
source-git-commit: 3c5cc9275c9978caf57e4e29704e23405ac24b65

---


# Configurações gerais da conta

Descrições de campo das Configurações gerais da conta em Administração do conjunto de relatórios.

**[!UICONTROL Analytics &gt; Admin &gt; Report Suites &gt; Edit Settings &gt; General &gt; General Account Settings]**********************

Essas configurações contêm opções de edição para a funcionalidade básica do conjunto de relatórios, como nome e fuso horário.

<table id="table_5448A694DC0A48D2B20C7F1332509F6E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opção </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Título do Site</span> </td> 
   <td colname="col2"> <p>Identifica o site. Dá a cada conjunto de relatórios um título de site exclusivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> URL básica</span> </td> 
   <td colname="col2"> <p>Especifica o site principal do conjunto de relatórios. O URL básico não afeta a filtragem de referenciador. Use <a href="../../admin/admin/internal-url-filter-admin.md#concept_D6BB8358DB7643F0B13E5DC9B7607998" format="dita" scope="local"> filtros internos do URL</a> em vez disso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Fuso Horário</span> </td> 
   <td colname="col2"> <p>Determina a data e a hora associadas aos dados do relatório. </p> <p>Alterar o fuso horário de um conjunto de relatórios ao vivo cria um pico ou uma lacuna nos dados do relatório. Para minimizar o impacto, a Adobe recomenda alterar os fusos horários durante horários que não sejam de pico a fim de evitar o desvio dos dados. </p> <p>Por exemplo, se você alterar o fuso horário do conjunto de relatórios de Hora central para Hora do Pacífico às 15:00 horas, a hora atual do conjunto de relatórios mudará para 13:00 horas. Como o relatório já coletou dados para a hora 13:00, os relatórios mostram um pico de tráfego entre 13:00 e 15:00 horas. </p> <p>Como alternativa, se você alterar o fuso horário do conjunto de relatórios de Hora central para Hora do leste às 15:00 horas, a hora atual do conjunto de relatórios mudará para 16:00 horas. Os relatórios não exibem dados entre 15:00 e 16:00 horas no dia da mudança de hora. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Nível de conversão</span> </td> 
   <td colname="col2"> <p> Ativa ou desativa as variáveis de comércio eletrônico como eVars e campanhas. Use a opção <span class="uicontrol">Ativado, sem carrinho de compras</span> para ocultar todos os relatórios de carrinho de compras se não houver um carrinho de compras do site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Página Padrão</span> </td> 
   <td colname="col2"> <p> Se o seu <span class="wintitle">Relatório de páginas mais populares</span> contém URLs em vez de nomes de página, essa configuração impede que vários URLs representem a mesma página. For example, the URLs <span class="filepath"> https://mysite.com</span> and <span class="filepath"> https://mysite.com/index.html</span> are typically the same page. You can remove default filenames so that these two URLs would both show up as <span class="filepath"> https://mysite.com</span>. </p> <p>Se deixado em branco, os seguintes nomes de arquivo são removidos dos URLs: <span class="filepath">index.htm</span>, <span class="filepath">index.html</span>, <span class="filepath">index.cgi</span>, <span class="filepath">index.asp</span>, <span class="filepath">default.htm</span>, <span class="filepath">default.html</span>, <span class="filepath">default.cgi</span>, <span class="filepath">default.asp</span>, <span class="filepath">home.htm</span>, <span class="filepath">home.html</span>, <span class="filepath">home.cgi</span> e <span class="filepath">home.asp</span>. </p> <p>Para desativar completamente a remoção dos nomes de arquivo, insira um valor que nunca está presente em seus URLs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Substituir o último octeto de endereços IP por 0 </span> </td> 
   <td colname="col2"> <p>A remoção do último octeto é realizada antes da filtragem de IP. Assim, o último octeto será substituído por um 0, e as regras de exclusão de IP devem ser atualizadas para corresponder os endereços IP com um zero no final. A correspondência de * deve corresponder a 0. </p> <p>Marcar essa opção indica que o endereço IP foi alterado antes de ser processado. Por exemplo, o endereço de IP 134.123.567.780 é alterado para 134.123.567.0. Os dados de segmentação geográfica não serão tão exatos como seriam se o endereço inteiro de IP fosse usado. Specifically, city accuracy is going to be more affected than country or region accuracy. Tanto as regras de bot como as regras VISTA são afetadas, pois elas não podem acessar o endereço inteiro de IP. Além disso, qualquer regra de processamento que seja baseada em um IP (incluindo regrais de canais de marketing e regras de processamento de conjuntos de relatórios), será afetada por essa configuração. </p> <p>Observação: essa configuração fica habilitada por padrão para qualquer conjunto de relatórios criado no Data Center de Londres depois de janeiro de 2019, mas somente se as configurações desse conjunto de relatórios tiverem sido copiadas de um modelo listado no Admin Console. Os conjuntos de relatórios cujas configurações estiverem duplicadas de outros conjuntos de relatórios herdarão todas as configurações do conjunto selecionado. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Ofuscação de IP</span> </td> 
   <td colname="col2"> <p>Transforma endereços IP em sequências de caracteres não reconhecidas, removendo-as dos armazenamentos de dados da Adobe. Quando o Obscurecimento de IP estiver ativado, os endereços IP originais são perdidos permanentemente. </p> <p>Observação: os endereços IP são ofuscados em todo o Analytics, incluindo o Data Warehouse. Contudo, a configuração de IP no Target é controlada separadamente, de modo que a configuração não é afetada no Target. </p> <p>Se a ofuscação de IP estiver ativada, a exclusão de IP ocorrerá antes de o endereço IP ser ofuscado, de modo que os clientes não precisam fazer qualquer alteração ao ativar a ofuscação de IP. </p> <p>Marcar <span class="uicontrol">Desativado</span> deixa o endereço IP nos dados. </p> <p>Marcar <span class="uicontrol">Ofuscar endereço IP</span> altera o IP para um valor com hash (por exemplo, 234abc6493872038). </p> <p>Marcar <span class="uicontrol">Remover endereço IP</span> substitui o endereço IP por x.x.x.x nos dados após a pesquisa geográfica. </p> <p>Observação: Essa configuração pode exigir alterações nas regras <a href="../../admin/admin/bot-removal/bot-rules.md#concept_A306689C65EB4D0F9AE65E3FD48ED5F7" format="dita" scope="local"> do</a> robô personalizado ou<a href="../../admin/admin/exclude-ip.md#concept_265A95A803F740629CAAAA7EB8BE81A4" format="dita" scope="local"> exclusões</a>de IP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Armazenamento de ID de transação</span> </td> 
   <td colname="col2"> <p>Permite usar fontes de dados da <a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/c_Transaction_ID.html" format="https" scope="external">ID de transação</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Ativar Ad Hoc Analysis</span> </td> 
   <td colname="col2"> <p>Indica se o conjunto de relatórios em questão é exibido como um conjunto de relatórios disponível na Ad Hoc Analysis. Use essa configuração para limitar quais conjuntos de relatórios serão exibidos como uma opção para a Ad Hoc Analysis. Por exemplo, é possível desativar a Ad Hoc Analysis para desenvolvimento e conjuntos de relatórios de QA. </p> </td> 
  </tr> 
  <tr> 
   <td><span class="wintitle"> Habilitar o Data Warehouse</span> </td> 
   <td colname="col2"> <p>Habilita o Data Warehouse em <span class="uicontrol">Ferramentas</span> &gt; <span class="uicontrol">Data Warehouse</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

