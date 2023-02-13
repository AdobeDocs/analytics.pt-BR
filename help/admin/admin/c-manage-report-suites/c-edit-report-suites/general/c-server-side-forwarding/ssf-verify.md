---
description: Para verificar se o encaminhamento pelo lado do servidor está corretamente habilitado, será preciso inspecionar a resposta HTTP enviada pela solicitação de rastreamento do Analytics. Isso pode ser feito usando as ferramentas de desenvolvimento de um navegador ou usando uma ferramenta de proxy, como o Charles Web Debugger. As instruções a seguir ilustram quais indicadores devem estar presentes para garantir que o encaminhamento pelo lado do servidor seja habilitado corretamente.
solution: Analytics
title: Como verificar a implementação do encaminhamento pelo lado do servidor
feature: Server-Side Forwarding
exl-id: 21db4572-da3c-43aa-a774-86a089656695
source-git-commit: beef45403f3c3eb7ac423ca8e0b6db0143ff1b9b
workflow-type: ht
source-wordcount: '256'
ht-degree: 100%

---

# Como verificar a implementação do encaminhamento pelo lado do servidor

Para verificar se o encaminhamento pelo lado do servidor está corretamente habilitado, será preciso inspecionar a resposta HTTP enviada pela solicitação de rastreamento do Analytics. Isso pode ser feito usando as ferramentas de desenvolvimento de um navegador ou usando uma ferramenta de proxy, como o Charles Web Debugger. As instruções a seguir ilustram quais indicadores devem estar presentes para garantir que o encaminhamento pelo lado do servidor seja habilitado corretamente.

Para verificar o status do encaminhamento pelo lado do servidor:

1. Carregue uma página de teste que contenha o código AppMeasurement atualizado.
1. Nas ferramentas de depuração do seu navegador ou usando seu software proxy, inspecione a resposta HTTP da solicitação de rastreamento do Analytics (você pode facilmente filtrar isso, selecionando qualquer caminho contendo “b/ss”).
1. Inspecione a resposta HTTP. Se a resposta contiver dados do Audience Manager (conforme ilustrado abaixo), o encaminhamento pelo lado do servidor está funcionando.

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/ssf-succeed.png)

>[!CAUTION]
>
>Se a resposta contiver o par de valores `"status":"SUCCESS"` ou uma imagem 2 x 2, o encaminhamento pelo lado do servidor não será configurado corretamente. Verifique se o serviço de identidade foi implantado corretamente, se você implantou o módulo App Measurement, se o conjunto de relatórios aplicável foi mapeado para a ID da organização correto e se o encaminhamento do lado do servidor foi ativado nas ferramentas administrativas do Analytics.v

>[!MORELIKETHIS]
>
>* [Charles Web Debugger](https://www.charlesproxy.com/)

