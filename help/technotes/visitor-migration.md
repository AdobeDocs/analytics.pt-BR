---
description: A migração do visitante é um processo no qual o cookie da ID de visitante é transferido de um domínio para outro.
keywords: Analytics Implementation
title: Migração de visitante
topic: Developer and implementation
uuid: af31928c-85d7-407f-a583-0c8f2852ceb3
translation-type: ht
source-git-commit: 0439440e10dddf8a5d64e4ea8f9868b521e5ca20

---


# Migração de visitante

A migração do visitante é um processo no qual o cookie da ID de visitante é transferido de um domínio para outro.

A migração do visitante permite que você preserve cookies de identificação do visitante ao alterar domínios de coleção de dados. Os domínios de coleta dos dados podem ser alterados pelos seguintes motivos:

* Transferência de `2o7.net` para `omtrdc.net` ([Coleta de dados regional](https://marketing.adobe.com/resources/help/pt_BR/whitepapers/rdc/)).

* Você está implementando o [Serviço de ID de visitante da Experience Cloud](https://marketing.adobe.com/resources/help/pt_BR/mcvid/) e migrando de um domínio de coleta de dados primários/CNAME para `2o7.net` ou `omtrdc.net` ([Coleta de dados regional](https://marketing.adobe.com/resources/help/pt_BR/whitepapers/rdc/))

* Transferência de `2o7.net` ou `omtrdc.net` para uma coleta da dados cname/primários ([Cookies primários)](https://docs.adobe.com/content/help/pt-BR/core-services/interface/ec-cookies/cookies-first-party.translate.html).

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
   <td colname="col1"> <p> <b>Para começar:</b> <a href="https://helpx.adobe.com/br/marketing-cloud/contact-support.html"  >entre em contato com o atendimento ao cliente</a> com os domínios que você deseja migrar e o período de migração que você deseja habilitar (30, 60 ou 90 dias). Certifique-se de incluir domínios protegidos e não protegidos. </p> </td> 
   <td colname="col3"> <p>Crie uma lista com a sintaxe <i>exata</i> para os domínios que você deseja migrar de ou para. </p> 
    <ul id="ul_067EC5C7619141A6BDFBC209C9FD47E2"> 
     <li id="li_0723D948465A49C1871B81207AEDC4DC">example.112.2o7.net &gt; metrics.example.com </li> 
     <li id="li_B0CA15A593BD4AB9802E33A3FF037C7A">example.102.112.2o7.net &gt; smetrics.example.com </li> 
    </ul> <p>Os nomes de host de migração são configurados no servidor de coleção de dados da Adobe. O Atendimento ao cliente informará quando a alteração ocorre para que você possa planejar a próxima etapa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Mais de 6 horas depois da alteração de configuração</b>: atualize as variáveis <code> s.trackingServer</code> e <code> s.trackingServerSecure</code> no código JavaScript do Analytics para usar os novos servidores de coleta de dados. </p> </td> 
   <td colname="col3"> <p>Depois de fazer essa alteração, use um [packet monitor](../implement/validate/packet-monitor.md) para verificar se a solicitação de imagem do Analytics vai para o servidor de coleta de dados atualizado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Depois de atualizar o código do Analytics</b>: teste o site para verificar se o redirecionamento do domínio de coleta dos dados anterior está ocorrendo. </p> </td> 
   <td colname="col3"> <p>Use um [packet monitor](../implement/validate/packet-monitor.md) para verificar se, quando você acessar o site pela primeira vez ou após apagar os cookies, é possível visualizar dois códigos de status HTTP 302 (redirecionar) antes do código do status HTTP 200 (OK). Em caso de falha de qualquer um dos redirecionamentos, entre em contato imediatamente com o Atendimento ao cliente para verificar se a migração está configurada corretamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Para o período de migração inteiro</b>: mantenha o registro de DNS do nome de host anterior ativado. </p> </td> 
   <td colname="col3"> <p>O nome de host anterior deve ser resolvido através de DNS ou a migração do cookie não ocorrerá. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variáveis visitorMigrationKey e visitorMigrationServer substituídas {#section_32FCEE2575944D039EA0FEBFB5814259}

A partir de março de 2013, as variáveis de coleta de dados `visitorMigrationKey`, `visitorMigrationServer` e `visitorMigrationServerSecure` foram substituídas e não são mais usadas. Os dados contidos anteriormente nessas variáveis agora são armazenados nos servidores da Adobe para aumentar a segurança.
