---
description: Para verificar se o encaminhamento pelo lado do servidor está corretamente habilitado, será preciso inspecionar a resposta HTTP enviada pela solicitação de rastreamento do Analytics. Isso pode ser feito usando as ferramentas de desenvolvimento de um navegador ou usando uma ferramenta de proxy, como o Charles Web Debugger. As instruções a seguir ilustram quais indicadores devem estar presentes para garantir que o encaminhamento pelo lado do servidor seja habilitado corretamente.
solution: Audience Manager
title: Como verificar a implementação do encaminhamento pelo lado do servidor
uuid: e37296cc-0120-486a-a4ca-78d648cf6a11
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Como verificar a implementação do encaminhamento pelo lado do servidor

Para verificar se o encaminhamento pelo lado do servidor está corretamente habilitado, será preciso inspecionar a resposta HTTP enviada pela solicitação de rastreamento do Analytics. Isso pode ser feito usando as ferramentas de desenvolvimento de um navegador ou usando uma ferramenta de proxy, como o Charles Web Debugger. As instruções a seguir ilustram quais indicadores devem estar presentes para garantir que o encaminhamento pelo lado do servidor seja habilitado corretamente.

Para verificar o status do encaminhamento pelo lado do servidor:

1. Carregue uma página de teste que contenha o código AppMeasurement atualizado.
1. Nas ferramentas de depuração do seu navegador ou usando seu software proxy, inspecione a resposta HTTP da solicitação de rastreamento do Analytics (você pode facilmente filtrar isso, selecionando qualquer caminho contendo “b/ss”).
1. Inspecione a resposta HTTP. Se a resposta contiver dados do Audience Manager (conforme ilustrado abaixo), o encaminhamento pelo lado do servidor está funcionando.

![](assets/ssf-succeed.png)

>[!CAUTION]
>
>Se a resposta contiver o par de valores `"status":"SUCCESS"` ou uma imagem 2 x 2, o encaminhamento pelo lado do servidor não será configurado corretamente. Certifique-se de que o Serviço de identidade foi devidamente implantado, que você implantou o módulo AppMeasurement, que o conjunto de relatórios aplicável foi mapeado para a Organização IMS correta e que o encaminhamento pelo lado do servidor foi habilitado no Admin Console do Analytics.

>[!MORELIKETHIS]
>
>* [Charles Web Debugger](https://www.charlesproxy.com/)

