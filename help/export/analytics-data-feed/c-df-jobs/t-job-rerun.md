---
description: É possível executar uma ou mais tarefas novamente a partir da lista de Tarefas.
keywords: Feed de dados; tarefa; rerun
seo-description: É possível executar uma ou mais tarefas novamente a partir da lista de Tarefas.
seo-title: Executar novamente uma tarefa
solution: Analytics
title: Executar novamente uma tarefa
uuid: 5 caf 95 da-dd 88-4 b 1 a-a 081-684 f 4 fd 1 f 714
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Executar novamente uma tarefa

É possível executar uma ou mais tarefas novamente a partir da lista de Tarefas.

1. Selecione um ou mais tarefas que você deseja executar novamente.
1. Click **[!UICONTROL Rerun Job]**.

   O processo de repetição depende do status atual da tarefa.

   | Status | Filename em cache no servidor | Processo |
   |---|---|---|
   | Concluído | Sim | O arquivo é reenviado. |
   | Concluído | Não | A tarefa é reprocessada e reenviada. |
   | Falha | Não | A tarefa é reprocessada e reenviada. |
   | Outro status | N/A | Não suportado. |

