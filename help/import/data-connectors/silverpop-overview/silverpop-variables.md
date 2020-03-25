---
description: A integração dos Data Connectors para o Silverpop usa variáveis do Analytics para rastrear várias métricas do Silverpop.
title: Variáveis de integração do Analytics
uuid: 3aef3caf-e24e-4fe7-b4d7-50ca0f6703b5
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Variáveis de integração do Analytics {#analytics-integration-variables}

A integração dos Data Connectors para o Silverpop usa variáveis do Analytics para rastrear várias métricas do Silverpop.

Após identificar o evento e as eVars a serem usadas na integração do Silverpop, use o Admin Console do Adobe Analytics para ativá-los (consulte [Conjuntos de relatórios](https://docs.adobe.com/content/help/pt-BR/analytics/admin/manage-report-suites/report-suites-admin.html)).

A tabela a seguir descreve as variáveis do Analytics necessárias para a integração do Silverpop.

## Variáveis obrigatórias {#section-3ca8dc46bab0436cba0c9ef827c8356a}

| Tipo de variável | Nome | Método de preenchimento | Descrição |
|---|---|---|---|
| evento (numérico) | Devoluções | Importado automaticamente do Silverpop. | O evento Rejeições permite que você veja o número de mensagens de email que não foram entregues aos destinatários por causa de um problema de entrega. |
| evento (numérico) | Cliques | Importado automaticamente do Silverpop. | O evento Clicados permite ver o número de visitantes que clicaram na mensagem de email. |
| evento (numérico) | Aberturas | Importado automaticamente do Silverpop. | O evento Abertos permite ver o número de visitantes que abriram a mensagem de email. |
| evento (numérico) | Envios | Importado automaticamente do Silverpop. | O evento Envios permite que você veja o número de mensagens de email enviadas. |
| evento (numérico) | Cancelamentos de inscrição | Importado automaticamente do Silverpop. | O evento Inscrições canceladas permite ver quantos visitantes abriram a mensagem de email, mas clicaram no link Cancelar inscrição para recusar futuras mensagens de email de sua organização. |
| eVar | ID do Silverpop/ID do visitante | Coletado de parâmetros de consulta em links de email pelo método de coleta automatizada ou por um plug-in JavaScript. | ID única do visitante |
| eVar ou s.campaign | ID de mala direta | Coletado de parâmetros de consulta em links de email pelo método de coleta automatizada ou por um plug-in JavaScript. | É frequentemente armazenado na variável da campanha. |

## Variáveis opcionais {#section-5f0a32b0a2084c87a64b5f90c0d0fb53}

| Tipo de variável | Nome | Método de preenchimento | Descrição |
|---|---|---|---|
| evento (contador) | Arquivo baixado | Coletado manualmente por meio de tags do Analytics. | Esse evento é usado para identificar usuários que baixaram um arquivo no site. |
| evento (contador) | Formulário iniciado | Coletado manualmente por meio de tags do Analytics. | Formulário iniciado é usado para identificar usuários que iniciam um formulário, mas não o concluem. |
| evento (contador) | Formulário concluído | Coletado manualmente por meio de tags do Analytics. | Formulário concluído é usado para identificar usuários que iniciam um formulário, mas não o concluem. |
| eVar | Endereço de email | Coletado manualmente por meio de tags do Analytics. | A variável Endereço de email serve para coletar manualmente o endereço de email ao assinar, fazer logon ou em outras páginas nas quais o endereço de email é coletado. Essa variável é usada para o remarketing para usuários que aceitaram receber email, mas que talvez ainda não tenham clicado em um email no passado. |
| eVar | Arquivo baixado | Coletado manualmente por meio de tags do Analytics. | Arquivo baixado identifica qual arquivo o visitante baixou. |
| eVar | Nome do formulário | Coletado manualmente por meio de tags do Analytics. | Nome do formulário identifica que formulário um visitante abandonou. |

