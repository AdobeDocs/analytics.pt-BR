---
description: A migração do visitante é um processo no qual o cookie da ID de visitante é transferido de um domínio para outro.
keywords: Implementação do Analytics
seo-description: A migração do visitante é um processo no qual o cookie da ID de visitante é transferido de um domínio para outro.
seo-title: Migração do visitante
solution: Analytics
title: Migração do visitante
topic: Desenvolvedor e implementação
uuid: af 31928 c -85 d 7-407 f-a 583-0 c 8 f 2852 ceb 3
translation-type: tm+mt
source-git-commit: 85dbc654643f63e30cb20df7e6e9e4cff8660c05

---


# Migração do visitante

A migração do visitante é um processo no qual o cookie da ID de visitante é transferido de um domínio para outro.

A migração do visitante permite que você preserve cookies de identificação do visitante ao alterar domínios de coleção de dados. Os domínios de coleta dos dados podem ser alterados pelos seguintes motivos:

* Moving from `2o7.net` to `omtrdc.net` ( [Regional Data Collection](https://marketing.adobe.com/resources/help/en_US/whitepapers/rdc/)).

* You are implementing the [Experience Cloud Visitor ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/) and are moving from a CNAME/first-party data collection domain to `2o7.net` or `omtrdc.net` ( [Regional Data Collection](https://marketing.adobe.com/resources/help/en_US/whitepapers/rdc/))

* Moving from `2o7.net` or `omtrdc.net` to a cname/first-party data collection ( [First-Party Cookies)](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/).

* Transferência de um CNAME para outro (alterando domínios).

Após a configuração da migração do visitante, quando um usuário visita o novo domínio sem um cookie de ID de visitante, o servidor redireciona para o nome de host de coleção de dados anterior, recupera qualquer cookie de ID de visitante disponível e, em seguida, redireciona para o novo domínio. Se uma ID do visitante não for encontrada no nome de host anterior, uma nova ID é gerada. Isso ocorre apenas uma vez por visitante.

## Processo de migração do visitante {#section_FF0C5C5CAEF343FFA1892B29311F7160}

A tabela a seguir lista as tarefas exigidas para a migração do visitante:

<table id="table_7B2535FC3E264216A299686415C6B21C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tarefa </th> 
   <th colname="col3" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Para começar:</b> <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html" format="http" scope="external">entre em contato com o atendimento ao cliente</a> com os domínios que você deseja migrar e o período de migração que você deseja habilitar (30, 60 ou 90 dias). Certifique-se de incluir domínios protegidos e não protegidos. </p> </td> 
   <td colname="col3"> <p>Crie uma lista com a sintaxe <i>exata</i> para os domínios que você deseja migrar de ou para. </p> 
    <ul id="ul_067EC5C7619141A6BDFBC209C9FD47E2"> 
     <li id="li_0723D948465A49C1871B81207AEDC4DC">example.112.2o7.net &gt; metrics.example.com </li> 
     <li id="li_B0CA15A593BD4AB9802E33A3FF037C7A">example.102.112.2o7.net &gt; smetrics.example.com </li> 
    </ul> <p>Os nomes de host de migração são configurados no servidor de coleção de dados da Adobe. O Atendimento ao cliente informará quando a alteração ocorre para que você possa planejar a próxima etapa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Mais de 6 horas depois da alteração de configuração</b>: atualize as variáveis <code>s.trackingServer</code> e <code>s.trackingServerSecure</code> no código JavaScript do Analytics para usar os novos servidores de coleta de dados. </p> </td> 
   <td colname="col3"> <p>After you make this change, use a <a href="../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258" format="dita" scope="local"> Packet Analyzer</a> to verify that the Analtyics image request is going to the updated data collection server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Depois de atualizar o código do Analytics</b>: teste o site para verificar se o redirecionamento do domínio de coleta dos dados anterior está ocorrendo. </p> </td> 
   <td colname="col3"> <p>Use um <a href="../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258" format="dita" scope="local"> Analisador de pacote</a> para verificar se ao acessar seu site pela primeira vez ou depois de apagar os cookies, você verá dois códigos de status HTTP 302 (redirecionamento) antes do código de status HTTP 200 (OK). Em caso de falha de qualquer um dos redirecionamentos, entre em contato imediatamente com o Atendimento ao cliente para verificar se a migração está configurada corretamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Para o período de migração inteiro</b>: mantenha o registro de DNS do nome de host anterior ativado. </p> </td> 
   <td colname="col3"> <p>O nome de host anterior deve ser resolvido através de DNS ou a migração do cookie não ocorrerá. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variáveis visitorMigrationKey e visitorMigrationServer substituídas {#section_32FCEE2575944D039EA0FEBFB5814259}

As of March 2013, the `visitorMigrationKey`, `visitorMigrationServer`, and `visitorMigrationServerSecure` data collection variables are deprecated and no longer used. Os dados contidos anteriormente nessas variáveis agora são armazenados nos servidores da Adobe para aumentar a segurança.
