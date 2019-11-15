---
description: É possível executar uma ou mais tarefas novamente a partir da lista de Tarefas.
keywords: Data Feed;job;rerun
solution: Analytics
title: Reexecutar uma tarefa
uuid: 5caf95da-dd88-4b1a-a081-684f4fd1f714
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Reexecutar uma tarefa

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

