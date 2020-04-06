---
description: Você pode criar um novo conjunto de relatórios selecionando um modelo predefinido ou usando um de seus conjunto de relatórios existentes para servir como modelo geral.
title: Configurações do novo conjunto de relatórios
topic: Admin tools
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Configurações do novo conjunto de relatórios

Você pode criar um novo conjunto de relatórios selecionando um modelo predefinido ou usando um de seus conjunto de relatórios existentes para servir como modelo geral.

Descrições dos elementos usados ao [Criar um conjunto de relatórios](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md).

>[!NOTE] A [documentação do Conjunto de relatórios virtuais](/help/components/vrs/c-workflow-vrs/vrs-create.md) mostra como criar conjuntos de relatórios virtuais.

<table id="table_F739FBD8DB8D409E916F12F61C5953D0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> ID do conjunto de relatórios </span> </td> 
   <td colname="col2"> <p>Especifica uma ID exclusiva que pode conter somente caracteres alfanuméricos. Essa ID não pode ser alterada após sua criação. A Adobe define o prefixo de ID necessário e também não pode ser alterado. </p> <p>Ao criar vários conjunto de relatórios, certifique-se de que a convenção de nome que usar garanta IDs de conjunto de relatórios únicos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Título do Site</span> </td> 
   <td colname="col2">Identifica o conjunto de relatórios em <span class="wintitle">Ferramentas administrativas</span>. Esse título também é usado na lista suspensa do <span class="wintitle">Conjunto de relatórios</span> no cabeçalho do suite. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Fuso Horário</span> </td> 
   <td colname="col2"> Programa eventos e dados de carimbo de data e hora. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> URL básica</span> </td> 
   <td colname="col2"> (Opcional) Define o domínio base do conjunto de relatórios. Esse URL funciona como um filtro de URL interno se você não definir explicitamente filtros de URL internos para o conjunto de relatórios. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Página Padrão</span> </td> 
   <td colname="col2"> <p>(Opcional) elimina dos URLs encontrados as ocorrências do valor <span class="wintitle">Página padrão</span>. Se seu relatório <span class="wintitle">Páginas mais populares</span> contiver URLs em vez de nomes de páginas, esta configuração impedirá que haja vários URLs para a mesma página da Web. </p> <p>Por exemplo, os URLs <span class="filepath">https://mysite.com</span> e <span class="filepath">https://mysite.com/index.html</span> normalmente são a mesma página. Você pode remover nomes de arquivo irrelevantes, de modo que esses dois URLs sejam exibidos como <span class="filepath">https://meusite.com</span> em seus relatórios. </p> <p>Se você não definir esse valor, o Analytics remove automaticamente os seguintes nomes de arquivos dos URLs: <span class="filepath">index.htm</span>, <span class="filepath">index.html</span>, <span class="filepath">index.cgi</span>, <span class="filepath">index.asp</span>, <span class="filepath">default.htm</span>, <span class="filepath">default.html</span>, <span class="filepath">default.cgi</span>, <span class="filepath">default.asp</span>, <span class="filepath">home.htm</span>, <span class="filepath">home.html</span>, <span class="filepath">home.cgi</span> e <span class="filepath">home.asp</span>. </p> <p>Para desativar a remoção de nomes de arquivo, especifique um valor de Página padrão que nunca ocorra em seus URLs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Data de ativação </p> </td> 
   <td colname="col2">Informa a Adobe da data em que você espera que este conjunto de relatórios fique ativo. Se sua programação de implantação for alterada, forneça uma estimativa de tráfego atualizada usando a ferramenta <span class="wintitle">Tráfego esperado permanente</span> em <a href="/help/admin/c-traffic-management/traffic-management.md">Gerenciamento do tráfego</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Exibições de página estimadas por dia</span> </td> 
   <td colname="col2"> Identifica o número estimado de visualizações de página que você espera que este conjunto de relatórios suporte em um dia. Grandes volumes de tráfego exigem um processo de aprovação mais longo. Para evitar atrasos no processamento, seja o mais preciso possível com essa estimativa. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Moeda de base</span> </td> 
   <td colname="col2"> <p>Especifica a moeda padrão usada para armazenar todos os dados monetários. O relatórios do Analytics converte as transações em outras moedas para a moeda de base, usando a taxa de conversão atual no momento em que recebe os dados. </p> <p> O relatório de Analytics utiliza o Variável<span class="varname"> currencyCode</span> do JavaScript para identificar a moeda de uma transação específica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Desativar suporte de caractere multibyte </span> </td> 
   <td colname="col2"> <p>Desativa o suporte a caracteres multibyte para o conjunto de relatórios. Se você desativar o suporte a caracteres com vários bytes, o sistema partirá do princípio de que os dados estão no formato ISO-8859-1. As páginas da Web precisam especificar seu conjunto de caracteres na Variável<span class="varname"> charSet</span> do JavaScript. </p> <p>O suporte a caracteres com vários bytes armazena caracteres no conjunto de relatórios usando UTF-8. Após o recebimento, o sistema converte os dados do conjunto de caracteres de sua página da Web para o conjunto de caracteres UTF-8, para que você possa usar qualquer idioma em seus relatórios de marketing. </p> <p>Entre em contato com seu Gerente de conta ou com o Atendimento ao cliente para alterar o suporte a caracteres com vários bytes de um conjunto de relatórios existente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Ativar a Ad Hoc Analysis para esse suite</span> </td> 
   <td colname="col2"> Permite a visualização desse conjunto de relatórios quando você executa a Ad Hoc Analysis. </td> 
  </tr> 
 </tbody> 
</table>

