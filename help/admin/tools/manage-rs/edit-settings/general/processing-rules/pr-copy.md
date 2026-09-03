---
title: Copiar regras de processamento
description: Saiba como copiar regras de processamento de um conjunto de relatórios para outro.
feature: Processing Rules
role: Admin
exl-id: bb34ecac-0512-4cff-9ef0-72db2dcabc03
TQID: 'https://experienceleague.adobe.com/x7mG1fjpNiPn0x6No0RtEz4aJLcN2t7wpUkJ-0LQxII'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: fbaf7f9a-8341-44f6-aa57-6c8d50741804
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b4dd41a7-ccf8-4e9d-918e-acaab534a307id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 253
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
