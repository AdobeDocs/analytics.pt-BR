---
description: A integração dos Conectores de dados para Silverpop usa as variáveis do Analytics para rastrear várias métricas Silverpop.
title: Variáveis de integração do Analytics
uuid: 3aef3caf-e24e-4fe7-b4d7-50ca0f6703b5
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Analytics Integration Variables{#analytics-integration-variables}

A integração dos Conectores de dados para Silverpop usa as variáveis do Analytics para rastrear várias métricas Silverpop.

Após identificar o evento e as eVars a serem usadas com a integração do Silverpop, use o Admin Console do Adobe Analytics para ativá-los (consulte Conjuntos [de](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html)relatórios).

A tabela a seguir descreve as variáveis do Analytics necessárias para a integração do Silverpop.

## Variáveis obrigatórias {#section-3ca8dc46bab0436cba0c9ef827c8356a}

| Tipo de variável | Nome | Método de preenchimento | Descrição |
|---|---|---|---|
| event (numérico) | Devoluções | Importado automaticamente do Silverpop. | O evento Rejeições permite que você veja o número de mensagens de email que não foram entregues aos destinatários devido a um problema de entrega. |
| event (numérico) | Cliques | Importado automaticamente do Silverpop. | O evento Clicado permite que você veja o número de visitantes que clicaram na mensagem de email. |
| event (numérico) | Abre | Importado automaticamente do Silverpop. | O evento Aberto permite que você veja o número de visitantes que abriram a mensagem de email. |
| event (numérico) | Envio | Importado automaticamente do Silverpop. | O evento Envia permite que você veja o número de mensagens de email enviadas. |
| event (numérico) | Cancelar inscrição | Importado automaticamente do Silverpop. | O evento Cancelado de inscrição permite que você veja o número de visitantes que abriram a mensagem de email, mas clicaram no link Cancelar inscrição para recusar futuras mensagens de email de sua organização. |
| eVar | ID do Silverpop/ID do visitante | Coletado de parâmetros de consulta em links de email pelo método de coleta automatizada ou por um plug-in JavaScript. | ID de visitante único |
| eVar ou s.campaign | ID de correspondência | Coletado de parâmetros de consulta em links de email pelo método de coleta automatizada ou por um plug-in JavaScript. | Geralmente, isso é armazenado na variável da campanha. |

## Variáveis opcionais {#section-5f0a32b0a2084c87a64b5f90c0d0fb53}

| Tipo de variável | Nome | Método de preenchimento | Descrição |
|---|---|---|---|
| event (contador) | Arquivo baixado | Coletada manualmente por meio de tags do Analytics. | Esse evento é usado para identificar usuários que baixaram um arquivo no site. |
| event (contador) | Formulário iniciado | Coletada manualmente por meio de tags do Analytics. | O formulário iniciado é usado para identificar usuários que iniciam um formulário, mas não o preenchem. |
| event (contador) | Formulário concluído | Coletada manualmente por meio de tags do Analytics. | Formulário concluído é usado para identificar visitantes que iniciam um formulário e não o preenchem. |
| eVar | Email Address | Coletada manualmente por meio de tags do Analytics. | O Endereço de email é para coletar manualmente o endereço de email ao assinar, fazer logon ou outras páginas nas quais o endereço de email é coletado. Essa variável é usada para recomercializar usuários que aceitaram receber e-mail, mas talvez ainda não tenham clicado em um e-mail no passado. |
| eVar | Arquivo baixado | Coletada manualmente por meio de tags do Analytics. | Arquivo baixado identifica qual arquivo o visitante baixou. |
| eVar | Nome do formulário | Coletada manualmente por meio de tags do Analytics. | Nome do formulário identifica que formulário um visitante abandonou. |

