---
description: A tabela a seguir mostra a diferença entre erros de código corretos e incorretos.
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Erros comuns de sintaxe
topic: Developer and implementation
uuid: 9845dcb9-9f10-4f65-a43d-2af41edaa122
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Erros comuns de sintaxe

A tabela a seguir mostra a diferença entre erros de código corretos e incorretos.

| Incorreto | Correto |
|---|---|
| prop1 | s.prop1 (usa "s.") |
| s.evar1 | s.eVar1 (uso coreto de letras maiúsculas e minúsculas) |
| s.pagetype='errorpage'; | s.pageType='errorPage'; (uso coreto de letras maiúsculas e minúsculas) |
| s.tl(this,o,pageA) | s.tl(this,'o','pageA'); (uso correto de aspas simples) |
| s.events='event1'; s.events='event2'; | s.events='event1,event2'; (formatação correta) |
| s.pageName="John" (aspas inteligentes ativadas) | s.pageName="John" (aspas inteligentes desativadas) |
| s.products="shoes,UX4879,1,19.99" | s.products="shoes;UX4879;1;19.99" (uso de ponto-e-vírgula, e não vírgula) |
| s.products=";MacBook Air;1;$1999.99" | s.products=";MacBook Air;1;1999.99" (não usa cifrão) |
| s.products=";Nikon SB-600 Speedlight Flash for Nikon Digital SLR Cameras;1;229.9489183" | s.products=";Nikon SB-600 Speedlight Flash for Nikon Digital SLR Cameras;1;229.95" (preços arredondados ou truncados) |
| var s_account="rsid1, rsid2" | var s_account="rsid1,rsid2" (sem espaços entre IDs do conjunto de relatórios quando houver marcação de vários conjuntos) |
| s.events="event1, event2" | s.events="event1,event2" (sem espaços entre IDs do evento quando houver marcação de vários eventos) |
| s.products="product name" | s.products=";product name" (ponto-e-vírgula usado quando nenhuma categoria de produto foi listada) |

## Observações adicionais {#section_E2B6A9C966AD40A09578DD0F784DCAB9}

Mantenha o comentário do HTML de fechamento no fim do código Adobe (mesmo se você estiver usando a parte NOSCRIPT do script).
