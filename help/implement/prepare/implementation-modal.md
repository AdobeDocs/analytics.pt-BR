---
title: Modal de implementação
description: Saiba mais sobre a experiência dos novos clientes ao executarem a implementação do Adobe Analytics.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Modal de implementação

<!-- https://activation.adobedtm.com/index.php?redirected=1 -->

A janela modal &quot;Bem-vindo ao Adobe Analytics&quot; oferece um fluxo de trabalho simplificado para criar um conjunto de relatórios. A Adobe recomenda usar esse fluxo de trabalho sempre que mais conjuntos de relatórios forem necessários na organização.

![Captura de tela modal](assets/implementation-modal.png)

## Pré-requisitos

Sua Adobe ID deve ter acesso ao Adobe Analytics e ao Adobe Experience Platform Launch. Se não tiver acesso ao Launch, poderá entrar em um loop de autenticação no qual ele solicita que suas credenciais sejam verificadas indefinidamente. Fale com um administrador de sistema em sua organização para obter acesso ao Launch.

## Acessar o modal

Acesse o modal para criar um conjunto de relatórios usando as etapas a seguir.

1. Faça logon em [experiencecloud.adobe.com](https://experiencecloud.adobe.com) usando as credenciais da Adobe ID.
2. Clique no ícone de 9-grid na parte superior e em [!UICONTROL Adobe Analytics].
3. Se ainda não tiver criado um conjunto de relatórios, o modal será exibido automaticamente. If a report suite exists for this login company, click the Help icon in the top right, then click [!UICONTROL Welcome to Adobe Analytics].

>[!NOTE] A [!UICONTROL Welcome to Adobe Analytics] opção só será exibida se você fizer logon por meio da Adobe Experience Cloud. Se fizer logon por meio de domínios herdados, o modal não estará disponível.

## Criar um novo conjunto de relatórios

Click the [!UICONTROL Start Setup] button to begin the report suite creation workflow.

![Assistente RS](assets/analytics-implementation-rs-wizard.png)

### Tipo de propriedade

O tipo de propriedade ajuda a Adobe a determinar algumas configurações de backend com base em onde você pretende implementar o Analytics.

* **Site**: se você pretende implementar o Adobe Analytics apenas para um site.
* **Aplicativo móvel nativo**: se você pretende implementar o Adobe Analytics apenas para um aplicativo móvel.
* **Ambos**: se este conjunto de relatórios contiver dados de um site e um aplicativo móvel.

### Setores

Especifique seu modelo de negócios principal. Essa configuração ajuda a Adobe a pré-configurar alguns nomes e configurações de variável com base no modelo de negócios principal.

### Camada de dados

Uma [camada de dados](data-layer.md) é um objeto JavaScript que organiza todas as variáveis usadas na implementação em um único local útil. Consulte [Camadas de dados](data-layer.md) para obter mais informações.

### Repositório de dados

Dê um nome amigável ao conjunto de relatórios. A ID do conjunto de relatórios (RSID) é gerada automaticamente com base no nome amigável e na empresa de logon.

### Fuso horário

Verifique se a Adobe detectou o fuso horário correto para o conjunto de relatórios.

### Exibições de página estimadas por dia

Estime quanto tráfego o site ou aplicativo recebe por dia. Essas informações permitem que a Adobe aloque a quantidade correta de recursos de processamento no conjunto de relatórios.

### Moeda de base

Determine em qual moeda o conjunto de relatórios armazena valores monetários.

>[!IMPORTANT] Certifique-se de indicar a moeda correta, especialmente se você tiver requisitos de relatório sobre a receita. É difícil alterar a moeda padrão após o início da coleta de dados.

## Recursos de implementação

Após criar o conjunto de relatórios, escolha uma das duas opções para continuar com a implementação:

* **Acessar o Adobe Experience Platform Launch**: vincula você ao [launch.adobe.com](https://launch.adobe.com) para configurar a implementação e baixar o código de implantação. Consulte [Implementação com o Launch](../launch/overview.md). A Adobe recomenda usar o Launch na maioria dos casos.
* **Download do código de implementação**: fornece um link direto para baixar arquivos JavaScript para uma implementação manual do JavaScript. Consulte [AppMeasurement para JavaScript](../js/overview.md).
