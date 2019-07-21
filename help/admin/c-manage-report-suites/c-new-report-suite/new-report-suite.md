---
description: Você pode criar um novo conjunto de relatórios selecionando um modelo predefinido ou usando um de seus conjunto de relatórios existentes para servir como modelo geral.
seo-description: Você pode criar um novo conjunto de relatórios selecionando um modelo predefinido ou usando um de seus conjunto de relatórios existentes para servir como modelo geral.
seo-title: Novo conjunto de relatórios - configurações
solution: Analytics
title: Novo conjunto de relatórios - configurações
topic: Ferramentas administrativas
uuid: 3508 f 684-11 a 3-4 c 8 f-a 233-bea 6 bafd 57 c 0
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Novo conjunto de relatórios - configurações

Você pode criar um novo conjunto de relatórios selecionando um modelo predefinido ou usando um de seus conjunto de relatórios existentes para servir como modelo geral.

Descrições dos elementos usados ao [Criar um conjunto de relatórios](../../../admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md#task_67033B9710CB49F9B71A4DE374A538A0).

>[!NOTE]
>
>The [Virtual Report Suite documentation](/help/components/vrs/c-workflow-vrs/vrs-create.md) shows you how to create virtual report suites.

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
   <td colname="col2"> <p>Especifica uma ID única que pode conter somente caracteres alfanuméricos. Essa ID não pode ser alterada depois de criada. A Adobe define o prefixo da ID necessário e ele não pode ser alterado. </p> <p>Ao criar vários conjunto de relatórios, certifique-se de que a convenção de nome que usar garanta IDs de conjunto de relatórios únicos. </p> </td> 
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
   <td colname="col2"> (Opcional) Define o domínio básico do conjunto de relatórios. Este URL funciona como um filtro interno do URL se você não definir explicitamente os filtros internos do URL do conjunto de relatórios. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Página Padrão</span> </td> 
   <td colname="col2"> <p>(Opcional) elimina dos URLs encontrados as ocorrências do valor <span class="wintitle">Página padrão</span>. Se seu relatório <span class="wintitle">Páginas mais populares</span> contiver URLs em vez de nomes de páginas, esta configuração impedirá que haja vários URLs para a mesma página da Web. </p> <p>For example, the URLs<span class="filepath"> https://mysite.com</span> and <span class="filepath"> https://mysite.com/index.html</span> are typically the same page. You can remove extraneous filenames so that both these URLs show up as <span class="filepath"> https://mysite.com</span> in your reports. </p> <p>Se você não definir esse valor, o Analytics remove automaticamente os seguintes nomes de arquivos dos URLs: <span class="filepath">index.htm</span>, <span class="filepath">index.html</span>, <span class="filepath">index.cgi</span>, <span class="filepath">index.asp</span>, <span class="filepath">default.htm</span>, <span class="filepath">default.html</span>, <span class="filepath">default.cgi</span>, <span class="filepath">default.asp</span>, <span class="filepath">home.htm</span>, <span class="filepath">home.html</span>, <span class="filepath">home.cgi</span> e <span class="filepath">home.asp</span>. </p> <p>Para desativar a eliminação dos nomes de arquivo, especifique um valor para Página padrão que nunca ocorra em seus URLs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Data de ativação </p> </td> 
   <td colname="col2">Informa a Adobe quanto à data em que você espera que este conjunto de relatórios fique ativo. If your deployment schedule changes, provide an updated traffic estimate using the <span class="wintitle"> Permanent Expected Traffic</span> tool in <a href="../../../admin/c-traffic-management/traffic-management.md#concept_8BD651EE8B84434CB4D6308BC6C01B79" format="dita" scope="local"> Traffic Management</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Exibições de página estimadas por dia</span> </td> 
   <td colname="col2"> Identifica o número estimado de Exibições de página a que você espera que este conjunto de relatórios preste suporte em um dia. Grandes volumes de tráfego requerem um processo de aprovação mais longo. Para evitar atrasos no processamento, seja tão preciso quanto possível com relação a esta estimativa. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Moeda de base</span> </td> 
   <td colname="col2"> <p>Especifica a moeda padrão usada para armazenar todos os dados monetários. O Analytics converte as transações em outras moedas para a moeda de base usando a taxa de conversão atual no momento em que recebe os dados. </p> <p> O relatório de Analytics utiliza o <span class="varname"> variável currencycode</span> javascript para identificar a moeda de uma determinada transação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Desativar suporte de caractere multibyte </span> </td> 
   <td colname="col2"> <p>Desativa o suporte de caractere multibyte para o conjunto de relatórios. Se você desativar o suporte a caracteres com vários bytes, o sistema partirá do princípio de que os dados estão no formato ISO-8859-1. As páginas da Web precisam especificar seu conjunto de caracteres na <span class="varname"> Variável charset</span> javascript. </p> <p>O suporte a caracteres com vários bytes armazena caracteres no conjunto de relatórios usando UTF-8. No recebimento, o sistema converte os dados do conjunto de caracteres de sua página da Web para o conjunto de caracteres UTF-8, de modo a permitir o uso de qualquer idioma em seus relatórios de marketing. </p> <p>Entre em contato com seu Gerente de Conta ou com o atendimento ao cliente para alterar o suporte a caracteres com vários bytes de um conjunto de relatórios existente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Ativar a Ad Hoc Analysis para esse suite</span> </td> 
   <td colname="col2"> Permite a visualização desse conjunto de relatórios quando você executa a Ad Hoc Analysis. </td> 
  </tr> 
 </tbody> 
</table>

