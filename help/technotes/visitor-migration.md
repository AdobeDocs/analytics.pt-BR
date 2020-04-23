---
description: A migração do visitante é um processo no qual o cookie da ID de visitante é transferido de um domínio para outro.
keywords: Analytics Implementation
title: Migração de visitante
topic: Developer and implementation
uuid: af31928c-85d7-407f-a583-0c8f2852ceb3
translation-type: tm+mt
source-git-commit: 5e47974fcf95625def21a9011ad981197ae39c99

---


# Migração de visitante

A migração do visitante é um processo no qual o cookie da ID de visitante é transferido de um domínio para outro.

A migração de Visitantes permite preservar cookies de identificação de visitantes ao alterar domínios de coleta de dados. Os domínios de coleta de dados podem ser alterados pelos seguintes motivos:

* Transferência de `2o7.net` para `omtrdc.net` ([Coleta de dados regional](https://marketing.adobe.com/resources/help/pt_BR/whitepapers/rdc/)).

* Você está implementando o [Serviço de ID de visitante da Experience Cloud](https://marketing.adobe.com/resources/help/pt_BR/mcvid/) e migrando de um domínio de coleta de dados primários/CNAME para `2o7.net` ou `omtrdc.net` ([Coleta de dados regional](https://marketing.adobe.com/resources/help/pt_BR/whitepapers/rdc/))

* Transferência de `2o7.net` ou `omtrdc.net` para uma coleta da dados cname/primários ([Cookies primários)](https://docs.adobe.com/content/help/pt-BR/core-services/interface/ec-cookies/cookies-first-party.translate.html).

* Transferência de um CNAME para outro (alterando domínios).

Depois que a migração de visitante é configurada, quando um usuário visita o novo domínio sem um cookie de ID de visitante, o servidor redireciona para o nome do host de coleção de dados anterior, recupera todos os cookies de ID de visitante disponíveis e redireciona para o novo domínio. Se uma ID de Visitante não for encontrada no nome de host anterior, uma nova ID será gerada. Isso ocorre apenas uma vez por visitante.

## Processo de migração do visitante {#section_FF0C5C5CAEF343FFA1892B29311F7160}

A tabela a seguir lista as tarefas necessárias para a migração do visitante:

<table id="table_7B2535FC3E264216A299686415C6B21C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tarefa </th> 
   <th colname="col3" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Para começar:</b> <a href="https://helpx.adobe.com/br/marketing-cloud/contact-support.html"  >entre em contato com o atendimento ao cliente</a> com os domínios que você deseja migrar e o período de migração que você deseja habilitar (30, 60 ou 90 dias). Certifique-se de incluir os domínios protegidos e não protegidos. </p> </td> 
   <td colname="col3"> <p>Crie uma lista com a sintaxe <i>exata</i> dos domínios para os quais você deseja migrar e para os quais deseja migrar. </p> 
    <ul id="ul_067EC5C7619141A6BDFBC209C9FD47E2"> 
     <li id="li_0723D948465A49C1871B81207AEDC4DC">example.112.2o7.net &gt; metrics.example.com </li> 
     <li id="li_B0CA15A593BD4AB9802E33A3FF037C7A">example.102.112.2o7.net &gt; smetrics.example.com </li> 
    </ul> <p>Os nomes de host de migração são configurados no servidor de coleta de dados da Adobe. O Atendimento ao cliente informará quando a alteração for feita, para que você possa planejar a próxima etapa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Mais de 6 horas depois da alteração de configuração</b>: atualize as variáveis <code> s.trackingServer</code> e <code> s.trackingServerSecure</code> no código JavaScript do Analytics para usar os novos servidores de coleta de dados. </p> </td> 
   <td colname="col3"> <p>After you make this change, use a <a href="../implement/validate/packet-monitor.md"> packet monitor</a> to verify that the Analtyics image request is going to the updated data collection server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Imediatamente após a atualização do código</b>do Analytics: Teste seu site para verificar se o redirecionamento para o domínio de coleta de dados anterior está ocorrendo. </p> </td> 
   <td colname="col3"> <p>Use a <a href="../implement/validate/packet-monitor.md"> packet monitor</a> to verify that when you access your site for the first time, or after clearing cookies, you see two 302 (redirect) HTTP status codes before the 200 (OK) HTTP status code. Se algum desses redirecionamentos falhar, entre em contato imediatamente com o Atendimento ao cliente para garantir que a migração esteja configurada corretamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Para todo o período</b>de migração: Mantenha o registro DNS do nome de host anterior ativo. </p> </td> 
   <td colname="col3"> <p>O nome do host anterior deve ser resolvido por meio do DNS ou a migração do cookie não ocorrerá. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variáveis visitorMigrationKey e visitorMigrationServer substituídas {#section_32FCEE2575944D039EA0FEBFB5814259}

A partir de março de 2013, as variáveis de coleta de dados `visitorMigrationKey`, `visitorMigrationServer` e `visitorMigrationServerSecure` foram substituídas e não são mais usadas. Os dados contidos anteriormente nessas variáveis agora são armazenados nos servidores da Adobe para aumentar a segurança.
