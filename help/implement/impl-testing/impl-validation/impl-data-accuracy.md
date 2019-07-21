---
description: A validação da precisão de dados é um processo de comparação dos dados do relatório com pontos de dados conhecidos e verificáveis.
keywords: Implementação do Analytics
seo-description: A validação da precisão de dados é um processo de comparação dos dados do relatório com pontos de dados conhecidos e verificáveis.
seo-title: Validação da precisão de dados
solution: Analytics
title: Validação da precisão de dados
topic: Desenvolvedor e implementação
uuid: 267 f 6 c 61-705 a -41 cf -9 e 09-4 e 2 ce 2331 f 32
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Validação da precisão de dados

A validação da precisão de dados é um processo de comparação dos dados do relatório com pontos de dados conhecidos e verificáveis.

O processo de validação deve ser concluído pela equipe da Adobe, de preferência pelo Consultor Adobe (a pessoa que mais conhece os detalhes técnicos da implementação).

Os pontos de dados preferidos para essa validação, em ordem de preferência, são listados a seguir:

* (Sites de Econversion) Comparação de ordens de econversion para um único dia.
* A comparação de eventos bem-sucedidos conhecidos, especialmente dados registrados onde os endereços IP e outras informações de navegador geralmente armazenadas nos logs de servidor da Web podem ser comparados com os dados coletados.
* Comparação de exibições da página.

>[!NOTE]
>
>Default pages, such as [!DNL index.html], often receive automated or monitoring traffic. Essas páginas representam uma diferença maior à coleta de dados baseada em navegador que outras páginas visitadas.

Os três tipos de validação exigem um log de depuração ou feed de dados para o período em questão. Esse tempo geralmente é de um dia ou menos.

Espera-se que os pedidos ou eventos bem-sucedidos possam ser medidos dentro de 2-3% dos valores reais (às vezes levando a níveis mais altos de precisão), com o uso de implementações baseadas em JavaScript. Isso presume uma página SSL, já que páginas SSL são armazenadas em cache com menos frequência e, por definição, não devem ser armazenadas em cache. Uma implementação com solicitações de imagem totalmente do lado do servidor em uma página SSL deve estar dentro de cerca de 0-1% dos valores reais. As páginas não seguras podem notar diferenças maiores, mas ainda dentro dos 5% dos valore reais.

Na comparação de exibições de página em um período, espera-se que as exibições de página possam responder por até 5% dos valores reais, não incluindo monitoramento (como Keynote ou WhatsUpGold) ou tráfego automático (spiders, bots e scripts).

As comparações de precisão de dados devem considerar os seguintes itens:

* Perguntas e respostas ou outros tipos de teste interno que podem ser filtrados por endereços IP ou regras VISTA.
* Tags inteligentes que geram apenas tags para determinados tipos de pedidos ou tráfego.
* As consultas de comparação devem levar em conta o que está sendo medido pelo site (não incluindo retornos, pedidos feitos pela equipe de atendimento ao cliente ou outras condições especiais).
* Assegure-se de que as diferenças de fuso horário entre a consulta e o conjunto de relatórios sejam correspondentes.
* Keynote personalizado ou semelhante (transação de Keynote etc) que meça o processo de pedidos e pode ser refletido nas tags, mas removido dos sistemas de pedido.
* Registros dos processos antifraude do cliente.
* Recarrega a página de pedido (A duplicação de pedidos é eliminada com base em *`purchaseID`*).

