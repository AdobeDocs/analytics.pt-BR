---
description: A tabela a seguir mostra a diferença entre erros de código corretos e incorretos.
keywords: Implementação do Analytics
seo-description: A tabela a seguir mostra a diferença entre erros de código corretos e incorretos.
seo-title: Erros comuns de sintaxe
solution: Analytics
subtopic: Solução de problemas
title: Erros comuns de sintaxe
topic: Desenvolvedor e implementação
uuid: 9845 dcb 9-9 f 10-4 f 65-a 43 d -2 af 41 edaa 122
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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
