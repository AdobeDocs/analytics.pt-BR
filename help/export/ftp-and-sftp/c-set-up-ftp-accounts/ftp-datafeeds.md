---
description: Os feeds de dados são uma exportação dos dados de sequência de cliques recebidos pela Adobe que oferecem os feeds de dados padrão e personalizado.
keywords: ftp;sftp
title: Feeds de dados
feature: FTP Export
exl-id: 286050fa-e197-4b70-b167-da6921615c1b
TQID: https://experienceleague.adobe.com/SWXC-g3KTGuKiT0CBFfptUSBigs8pgkPVdRLzWhl6z4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 331
ht-degree: 25%

---

# Feeds de dados

>[!NOTE]
>
>As informações a seguir estão relacionadas aos tipos de destino FTP e SFTP. FTP e SFTP são tipos de destino herdados. Ao configurar um feed de dados, você deve usar um tipo de destino de nuvem, que é mais seguro. Para obter mais informações sobre como configurar os tipos de destino da nuvem para um Feed de dados, consulte [Criar um Feed de dados](/help/export/analytics-data-feed/create-feed.md).

Os feeds de dados são uma exportação dos dados de sequência de cliques recebidos pela Adobe que oferecem os [Feeds de dados](/help/export/analytics-data-feed/data-feed-overview.md) padrão e personalizado.

Se você adquiriu o Adobe Data Warehouse, os [!UICONTROL Feeds de dados padrão] podem configurar seus próprios feeds de dados do Analytics. Eles podem ser enviados para qualquer conta FTP (configurada pela Adobe ou um FTP externo). Os Serviços de Engenharia da Adobe oferecem [!UICONTROL Feeds de Dados] personalizados que podem ser enviados por praticamente qualquer meio.

[!UICONTROL Feed de dados] contas FTP permitem 10 GB (por padrão). Todas as outras contas FTP padrão têm 50 MB por padrão. Nos casos em que os clientes estão usando a conta FTP para o uso pretendido adequado, alguns usuários com quantidades altas de tráfego podem preencher rapidamente essas contas. Quando uma conta FTP está cheia, nenhum arquivo adicional pode ser enviado para ela. Desse modo, os arquivos enviados para uma conta FTP ([!UICONTROL feeds de dados], solicitações de data warehouse e etc) não são entregues. É por isso que é importante gerenciar a conta FTP da Adobe removendo os arquivos recebidos e baixados.

Quando uma conta FTP estiver cheia, você deverá baixar e remover os arquivos atuais e informar à Adobe que o espaço foi limpo. O Adobe pode reenviar arquivos que não foram entregues. Algumas ferramentas, como o Data Warehouse, permitem que os usuários reenviem esses arquivos. O reenvio pode não exigir envolvimento da Adobe. Se a sua conta FTP parece estar enchendo com frequência, entre em contato com o Atendimento ao cliente da Adobe, que pode sugerir alternativas de entrega que podem incluir o aumento da cota de espaço e número de arquivo FTP na conta.
