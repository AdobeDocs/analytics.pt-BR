---
description: Para verificar se o encaminhamento pelo lado do servidor está ativado corretamente, será necessário inspecionar a resposta HTTP da solicitação de rastreamento do Analytics. Essas instruções ilustram quais indicadores devem estar presentes para garantir que o encaminhamento pelo lado do servidor esteja habilitado corretamente.
solution: Analytics
title: Como verificar a implementação do encaminhamento pelo lado do servidor
feature: Report Suite Settings
exl-id: 21db4572-da3c-43aa-a774-86a089656695
role: Admin
TQID: https://experienceleague.adobe.com/FpB4dk9D87gc24t5KG6WRJ-r8GFOvOEUlRTTjc6XFYI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 246
ht-degree: 33%

---

# Como verificar a implementação do encaminhamento pelo lado do servidor

Para verificar se o encaminhamento pelo lado do servidor está ativado corretamente, será necessário inspecionar a resposta HTTP da solicitação de rastreamento do Analytics. Isso pode ser feito usando as ferramentas de desenvolvedor de um navegador ou usando uma ferramenta de proxy, como o Charles Web Debugger. As instruções a seguir ilustram quais indicadores devem estar presentes para garantir que o encaminhamento pelo lado do servidor esteja habilitado corretamente.

Para verificar o status do encaminhamento pelo lado do servidor:

1. Carregue uma página de teste que contenha o código AppMeasurement atualizado.
1. Nas ferramentas de depuração do seu navegador ou usando seu software proxy, inspecione a resposta HTTP da solicitação de rastreamento do Analytics (você pode filtrar facilmente selecionando qualquer caminho que contenha &quot;b/ss&quot;).
1. Inspecione a resposta HTTP. Se a resposta contiver dados do Audience Manager (como ilustrado abaixo), o encaminhamento pelo lado do servidor está funcionando.

![](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/assets/ssf-succeed.png)

>[!CAUTION]
>
>Se a resposta contiver o par de valores `"status":"SUCCESS"` ou uma imagem 2 x 2, o encaminhamento pelo lado do servidor não será configurado corretamente. Verifique se o serviço de identidade foi implantado corretamente, se você implantou o módulo App Measurement, se o conjunto de relatórios aplicável foi mapeado para a ID da organização correto e se o encaminhamento do lado do servidor foi habilitado nas ferramentas administrativas do Analytics.v

>[!MORELIKETHIS]
>
>* [Charles Web Debugger](https://www.charlesproxy.com/)
