---
title: Implementação modal
description: Saiba mais sobre a experiência dos novos clientes ao executarem a implementação do Adobe Analytics.
translation-type: tm+mt
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# Implementação modal

<!-- https://activation.adobedtm.com/index.php?redirected=1 -->

A janela modal &quot;Bem-vindo ao Adobe Analytics&quot; fornece um fluxo de trabalho simplificado para criar um conjunto de relatórios. A Adobe recomenda usar esse fluxo de trabalho sempre que mais conjuntos de relatórios forem necessários em sua organização.

![Captura de tela modal](assets/implementation-modal.png)

## Pré-requisitos

Sua Adobe ID deve ter acesso ao Adobe Analytics e ao Adobe Experience Platform Launch. Se você não tiver acesso ao Launch, poderá ser colocado em um loop de autenticação no qual ele solicita que suas credenciais sejam verificadas indefinidamente. Fale com um administrador de sistema em sua organização para obter acesso ao Launch.

## Acesse o modal

Acesse o modal para criar um conjunto de relatórios usando as etapas a seguir.

1. Faça logon em [experiencecloud.adobe.com](https://experiencecloud.adobe.com) usando as credenciais da Adobe ID.
2. Click the 9-grid icon at the top, then click [!UICONTROL Adobe Analytics].
3. Se você ainda não tiver criado um conjunto de relatórios, o modal será exibido automaticamente. Se existir um conjunto de relatórios para essa empresa de logon, clique no ícone Ajuda na parte superior direita e clique em [!UICONTROL Bem-vindo ao Adobe Analytics].

> [!NOTE] A opção [!UICONTROL Bem-vindo ao Adobe Analytics] só é exibida se você fizer logon por meio da Adobe Experience Cloud. Se você fizer logon por domínios herdados, o modal não estará disponível.

## Criar um novo conjunto de relatórios

Clique no botão [!UICONTROL Iniciar configuração] para iniciar o fluxo de trabalho de criação do conjunto de relatórios.

![Assistente RS](assets/analytics-implementation-rs-wizard.png)

### Tipo de propriedade

O tipo de propriedade ajuda a Adobe a determinar algumas configurações de backend com base em onde você pretende implementar o Analytics.

* **Site**: Se você pretende implementar o Adobe Analytics apenas para um site.
* **Aplicativo** móvel nativo: Se você pretende implementar o Adobe Analytics apenas para um aplicativo móvel.
* **Ambos**: Se este conjunto de relatórios contiver dados para um site e um aplicativo móvel.

### Setores

Especifique seu modelo de negócios principal. Essa configuração ajuda a Adobe a pré-configurar alguns nomes e configurações variáveis com base no seu modelo de negócios principal.

### Camada de dados

Uma camada [de](data-layer.md) dados é um objeto JavaScript que organiza todas as variáveis usadas na implementação em um único local útil. See [Data layers](data-layer.md) for more information.

### Repositório de dados

Dê um nome amigável ao seu conjunto de relatórios. A ID do conjunto de relatórios (RSID) é gerada automaticamente com base no nome amigável e na empresa de logon.

### Fuso horário

Verifique se a Adobe detectou o fuso horário correto para o conjunto de relatórios.

### Visualizações de página estimadas por dia

Estime quanto tráfego seu site ou aplicativo recebe por dia. Essas informações permitem que a Adobe aloque a quantidade correta de recursos de processamento no seu conjunto de relatórios.

### Moeda de base

Determine em qual moeda o conjunto de relatórios armazena valores monetários.

> [!IMPORTANT] Certifique-se de indicar a moeda correta, especialmente se você tiver requisitos de relatório sobre a receita. É difícil alterar a moeda de base após o início da coleta de dados.

## Recursos de implementação

Após a criação do conjunto de relatórios, você tem uma das duas opções para continuar com a implementação:

* **Vá para o Adobe Experience Platform Launch**: Vincula você ao [launch.adobe.com](https://launch.adobe.com) para configurar sua implementação e baixar o código de implantação. Consulte [Implementação com o Launch](../launch/overview.md). A Adobe recomenda usar o Launch na maioria dos casos.
* **Download do código** de implementação: Fornece um link direto para baixar arquivos JavaScript para uma implementação manual do JavaScript. Consulte [AppMeasurement para JavaScript](../js/overview.md).
