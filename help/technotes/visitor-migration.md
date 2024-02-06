---
description: A migração do visitante é um processo no qual o cookie da ID de visitante é transferido de um domínio para outro.
keywords: Implementação do Analytics
title: Migração de visitante
topic-fix: Developer and implementation
feature: Analytics Basics
exl-id: d44628c8-902f-4e60-b819-41d5537407d8
source-git-commit: d3d5b01fe17f88d07a748fac814d2161682837c2
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 62%

---

# Migração de visitante

>[!NOTE]
>
>Se você já implementou o Serviço de ID de visitante do Experience Cloud, o Período de carência não é aplicável e não deve ser ativado.

A migração do visitante é um processo no qual os cookies de ID do visitante (s_vi) são migrados de um domínio para outro.

A migração do visitante permite que você preserve cookies de identificação do visitante ao alterar domínios de coleção de dados. Os domínios de coleta dos dados podem ser alterados pelos seguintes motivos:

* Transferência de `2o7.net` para `adobedc.net`.

* Você está implementando o [Serviço de ID de visitante da Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR) e migrando de um domínio de coleção de dados primários/CNAME para `adobedc.net`, `2o7.net` ou `omtrdc.net`

* Migração para uma coleção de dados cname/primários ([Cookies primários)](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=pt-BR).

* Transferência de um CNAME para outro (alterando domínios).

Após a configuração da migração do visitante, quando um usuário visita o novo domínio sem um cookie de ID de visitante, o servidor redireciona para o nome de host de coleção de dados anterior, recupera qualquer cookie de ID de visitante disponível e, em seguida, redireciona para o novo domínio. Se uma ID do visitante não for encontrada no nome de host anterior, uma nova ID é gerada. Isso ocorre apenas uma vez por visitante.

## Processo de migração do visitante {#process}

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
   <td colname="col1"> <p> <b>Para começar:</b> <a href="https://helpx.adobe.com/br/marketing-cloud/contact-support.html"  >entre em contato com o atendimento ao cliente</a> com os domínios que você deseja migrar e o período de migração que você deseja habilitar (30, 60 ou 90 dias). Certifique-se de incluir os domínios não seguros e seguros. </p> </td> 
   <td colname="col3"> <p>Crie uma lista com a sintaxe <i>exata</i> para os domínios que você deseja migrar de ou para. </p> 
    <ul id="ul_067EC5C7619141A6BDFBC209C9FD47E2"> 
     <li id="li_0723D948465A49C1871B81207AEDC4DC">example.112.2o7.net &gt; metrics.example.com </li> 
     <li id="li_B0CA15A593BD4AB9802E33A3FF037C7A">example.102.112.2o7.net &gt; smetrics.example.com </li> 
    </ul> <p>Os nomes de host de migração são configurados no servidor de coleção de dados da Adobe. O Atendimento ao cliente informará quando a alteração ocorre para que você possa planejar a próxima etapa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Mais de 6 horas depois da alteração de configuração</b>: atualize as variáveis <code> s.trackingServer</code> e <code> s.trackingServerSecure</code> no código JavaScript do Analytics para usar os novos servidores de coleta de dados. </p> </td> 
   <td colname="col3"> <p>Depois de fazer essa alteração, use o <a href="https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=pt-BR"> Experience Cloud Debugger</a> para verificar se a solicitação de imagem do Analytics vai para o servidor de coleção de dados atualizado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Depois de atualizar o código do Analytics</b>: teste o site para verificar se o redirecionamento do domínio de coleta dos dados anterior está ocorrendo. </p> </td> 
   <td colname="col3"> <p>Use um <a href="../implement/validate/packet-monitor.md"> monitor de pacote</a> para verificar se, quando você acessar o site pela primeira vez ou após apagar os cookies, é possível visualizar dois códigos de status HTTP 302 (redirecionar) antes do código do status HTTP 200 (OK). Em caso de falha de qualquer um dos redirecionamentos, entre em contato imediatamente com o Atendimento ao cliente para verificar se a migração está configurada corretamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Para o período de migração inteiro</b>: mantenha o registro de DNS do nome de host anterior ativado. </p> </td> 
   <td colname="col3"> <p>O nome de host anterior deve ser resolvido através de DNS ou a migração do cookie não ocorrerá. </p> </td> 
  </tr> 
 </tbody> 
</table>

| Tarefa | Descrição |
|--- |--- |
| Para começar: entre em contato com o Atendimento ao cliente com os domínios que você deseja migrar e o período de migração que você deseja habilitar (30, 60 ou 90 dias). Certifique-se de incluir os domínios não seguros e seguros. | Crie uma lista com a sintaxe exata dos domínios para os quais você deseja migrar e dos quais deseja migrar.<ul><li>example.112.2o7.net > metrics.example.com</li><li>example.102.112.2o7.net > smetrics.example.com</li></ul>Os nomes de host de migração são configurados no servidor de coleção de dados da Adobe. O Atendimento ao cliente informará quando a alteração ocorre para que você possa planejar a próxima etapa. |
| Mais de 6 horas depois da alteração de configuração: atualize o `s.trackingServer` e `s.trackingServerSecure` em seu código JavaScript do Analytics para usar os novos servidores de coleta de dados. | Depois de fazer essa alteração, use o [Experience Cloud debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=pt-BR) para verificar se a solicitação de imagem do Analytics vai para o servidor de coleta de dados atualizado. |
| Imediatamente após atualizar seu código do Analytics: teste seu site para verificar se o redirecionamento para o domínio de coleta de dados anterior está ocorrendo. | Use um [monitor de pacote](../implement/validate/packet-monitor.md) para verificar se, quando você acessar o site pela primeira vez ou após apagar os cookies, é possível visualizar dois códigos de status HTTP 302 (redirecionar) antes do código do status HTTP 200 (OK). Em caso de falha de qualquer um dos redirecionamentos, entre em contato imediatamente com o Atendimento ao cliente para verificar se a migração está configurada corretamente. |
| Para todo o período de migração: mantenha o registro DNS do nome de host anterior ativo. | O nome de host anterior deve ser resolvido através de DNS ou a migração do cookie não ocorrerá. |