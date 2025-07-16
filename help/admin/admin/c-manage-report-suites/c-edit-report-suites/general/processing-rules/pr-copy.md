---
title: Copiar regras de processamento
description: Saiba como copiar regras de processamento de um conjunto de relatórios para outro.
feature: Processing Rules
role: Admin
source-git-commit: 0bed2622f54bf2f46aa57dbfad7bd55a61d6c7d0
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# Cópia das regras de processamento entre conjuntos de relatórios

Copiar regras de processamento evita que você recrie manualmente a mesma lógica em vários conjuntos de relatórios. Você pode usar o recurso de cópia para compartilhar facilmente a funcionalidade de regras de processamento em vários conjuntos de relatórios, ou para copiar a funcionalidade testada de um conjunto de relatórios de desenvolvimento para um conjunto de relatórios de produção.

**[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de Relatórios]** > Selecionar conjunto de relatórios > **[!UICONTROL Editar Configurações]** > **[!UICONTROL Geral]** > **[!UICONTROL Regras de processamento]** > **[!UICONTROL Copiar regras de processamento]**

Essa interface permite duas opções:

* **Substituir todas as regras de processamento**: essa opção exclui todas as regras de processamento do conjunto de relatórios de destino e adiciona todas as regras de processamento ao conjunto de relatórios de destino na mesma ordem. Não é possível selecionar um número limitado de regras de processamento para substituir.
* **Anexar regras de processamento específicas**: esta opção permite que você selecione uma ou mais regras de processamento. As regras anexadas são adicionadas ao final da lista de regras de processamento em cada conjunto de relatórios de destino. Considere a ordem das regras de processamento e as regras que já existem ao anexar regras a cada conjunto de relatórios de destino.

Ao selecionar regras de processamento para anexar ou conjuntos de relatórios para copiar, você pode usar `Ctrl`/`Cmd` + `Click` para selecionar várias regras de processamento ou conjuntos de relatórios. Depois de selecionar os conjuntos de relatórios desejados para cópia, selecione **[!UICONTROL Copiar]** e confirme a janela modal exibida.

>[!WARNING]
>
>As regras de processamento afetam diretamente a coleta de dados e podem causar perda de dados se usadas incorretamente. Sempre teste as regras de processamento em um conjunto de relatórios de desenvolvimento antes de copiá-las em um conjunto de relatórios de produção para atenuar problemas de qualidade de dados.
