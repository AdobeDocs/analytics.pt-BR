---
description: Os feeds de dados são uma exportação dos dados de sequência de cliques recebidos pela Adobe que oferecem os feeds de dados padrão e personalizado.
keywords: ftp;sftp
title: Feeds de dados
uuid: 3c70eea3-ca59-4aa5-9b11-64e1bb677bfa
translation-type: tm+mt
source-git-commit: fc14751c810019c5257a23a8a598b16f42ed10ee

---


# Feeds de dados

Os feeds de dados são uma exportação dos dados de sequência de cliques recebidos pela Adobe que oferecem os [Feeds de dados](/help/export/analytics-data-feed/data-feed-overview.md) padrão e personalizado.

Se você adquiriu o Adobe Data Warehouse, os Feeds [!UICONTROL de dados] padrão podem configurar seus próprios feeds de dados do Analytics. Eles podem ser enviados para qualquer conta FTP (pode ser uma conta configurada pela Adobe ou uma conta FTP externa). Os serviços de engenharia da Adobe oferecem [!UICONTROL feeds de dados] personalizados que podem ser enviados utilizando praticamente qualquer meio.

[!UICONTROL As contas]FeedFTP de dados permitem 10 GB (por padrão). Todas as contas FTP possuem 50 MB por padrão. Quando os clientes estão usando a conta FTP para uso individual, usuários com grandes quantidades de tráfego podem encher essas contas rapidamente. Quando uma conta FTP está cheia, não é possível inserir mais nenhum arquivo. Desse modo, os arquivos enviados para uma conta FTP ([!UICONTROL feeds de dados], solicitações de data warehouse e etc) não são entregues. Este é um dos motivos pelos quais é importante gerenciar sua conta FTP da Adobe removendo arquivos que foram recebidos e baixados.

Quando uma conta FTP estiver cheia, você deverá baixar e remover os arquivos atuais para que a Adobe saiba que o espaço foi liberado. A Adobe poderá, então, reenviar os arquivos que não foram entregues. Algumas ferramentas, como o data warehouse, permitem que os usuários reenviem esses arquivos. O reenvio não requer o envolvimento da Adobe. Se a sua conta FTP fica cheia com frequência, entre em contato com o Atendimento ao cliente da Adobe, que poderá sugerir alternativas de envio que incluem o aumento do espaço de FTP e a cota do número do arquivo na conta.
