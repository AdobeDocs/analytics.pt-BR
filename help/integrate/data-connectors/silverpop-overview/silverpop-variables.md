---
description: A integração dos Conectores de dados para Silverpop usa variáveis do Analytics para rastrear várias métricas do Silverpop.
seo-description: A integração dos Conectores de dados para Silverpop usa variáveis do Analytics para rastrear várias métricas do Silverpop.
seo-title: Variáveis de integração do Analytics
title: Variáveis de integração do Analytics
uuid: 3 aef 3 caf-e 24 e -4 fe 7-b 4 d 7-50 ca 0 f 6703 b 5
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Analytics Integration Variables{#analytics-integration-variables}

A integração dos Conectores de dados para Silverpop usa variáveis do Analytics para rastrear várias métricas do Silverpop.

After identifying the Event and eVars to use with the Silverpop integration, use the Adobe Analytics Admin Console to enable them (see [Report Suites](http://microsite.omniture.com/t2/help/en_US/reference/index.html?f=report_suites_admin)).

A tabela a seguir descreve as variáveis do Analytics necessárias para a integração do Silverpop.

## Required Variables {#section-3ca8dc46bab0436cba0c9ef827c8356a}

| Tipo de variável | Nome | Método de preenchimento | Descrição |
|---|---|---|---|
| event (numérico) | Devoluções | Importado automaticamente do Silverpop. | O evento Rejeições permite ver o número de mensagens de email que não foram entregues aos destinatários devido a um problema de entrega. |
| event (numérico) | Cliques | Importado automaticamente do Silverpop. | O evento Clicado permite ver o número de visitantes que clicaram na mensagem de e-mail. |
| event (numérico) | Aberturas | Importado automaticamente do Silverpop. | O evento Aberto permite que você veja o número de visitantes que abriram a mensagem de e-mail. |
| event (numérico) | Envia | Importado automaticamente do Silverpop. | O evento Envia permite visualizar o número de mensagens de email enviadas. |
| event (numérico) | Cancelamentos | Importado automaticamente do Silverpop. | O evento Cancelar inscrição permite ver o número de visitantes que abriram a mensagem de email, mas clicaram no link Cancelar inscrição para recusar futuras mensagens de email de sua organização. |
| eVar | ID do Silverpop ID/ID do visitante | Coletado de parâmetros de consulta em links de email por meio do método de coleta automatizada ou de um plug-in javascript. | ID de visitante único |
| Evar ou s. campaign | ID de correspondência | Coletado de parâmetros de consulta em links de email por meio do método de coleta automatizada ou de um plug-in javascript. | Isso é armazenado na variável campanha com frequência. |

## Variáveis opcionais {#section-5f0a32b0a2084c87a64b5f90c0d0fb53}

| Tipo de variável | Nome | Método de preenchimento | Descrição |
|---|---|---|---|
| event (contador) | Arquivo baixado | Coletadas manualmente por meio de tags do Analytics. | Esse evento é usado para identificar usuários que baixaram um arquivo no site. |
| event (contador) | Formulário iniciado | Coletadas manualmente por meio de tags do Analytics. | O Formulário iniciado é usado para identificar usuários que iniciam um formulário, mas não o concluíram. |
| event (contador) | Formulário concluído | Coletadas manualmente por meio de tags do Analytics. | O Formulário concluído é usado para identificar visitantes que iniciam um formulário e não o concluíram. |
| eVar | Email Address | Coletadas manualmente por meio de tags do Analytics. | Endereço de email é para coletar manualmente o endereço de email no registro, logon ou outras páginas nas quais o endereço de email é coletado. Essa variável é usada para recomercializar para usuários que aceitaram receber e-mail, mas podem não ter clicado em um email no passado. |
| eVar | Arquivo baixado | Coletadas manualmente por meio de tags do Analytics. | O arquivo baixado identifica qual arquivo um visitante fez download. |
| eVar | Nome do formulário | Coletadas manualmente por meio de tags do Analytics. | O Nome do formulário identifica qual formulário um visitante abandonou. |

