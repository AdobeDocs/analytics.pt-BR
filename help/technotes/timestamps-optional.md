---
description: Saiba mais sobre as vantagens e desvantagens de usar a configuração Carimbos opcionais de data e hora.
keywords: Analytics Implementation
title: Usar Carimbos opcionais de data e hora
topic: Developer and implementation
uuid: 956aaa16-6ffa-4b63-b022-a659f5143e00
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Usar Carimbos opcionais de data e hora

Saiba mais sobre as vantagens e desvantagens de usar a configuração Carimbos opcionais de data e hora.

Carimbos opcionais de data e hora é a configuração padrão para todos os novos conjuntos de relatórios.

* Combine dados com e sem carimbos de data e hora no mesmo conjunto de relatórios global.
* Envie dados com carimbo de data e hora de um aplicativo móvel para um conjunto de relatórios global.
* Atualize os aplicativos para usar carimbos de data e hora sem precisar criar um novo conjunto de relatórios.

>[!NOTE] Os carimbos opcionais de data e hora são a configuração padrão para todos os novos conjuntos de relatórios gerados a partir de um modelo. Os conjuntos de relatórios copiados de um conjunto existente herdarão as configurações do original.

Consulte [Carimbos opcionais](https://marketing.adobe.com/resources/help/pt_BR/reference/timestamp-optional.html) de data e hora para obter mais informações sobre a configuração.

## Carimbos opcionais de data e hora: integração de dados com e sem carimbos de data e hora {#section_BF17CB593044462B993FD0D28EA56518}

Usando o recurso Carimbos opcionais de data e hora, é possível combinar dados sem carimbos de data e hora com dados com carimbos de data e hora, sem perda de dados. Os dados offline com carimbos de data e hora gerados a partir de um dispositivo móvel podem ser combinados com dados online sem carimbos de data e hora de uma página da Web, ou integrados com dados de qualquer plataforma usando uma chamada de carimbo de data e hora do lado do cliente.

* **Dados** com carimbo de data e hora. O carimbo de data e hora do lado do cliente é capturado e enviado diretamente com os dados do dispositivo, usando as variáveis do carimbo de data e hora do lado do cliente: Javascript em uma página da Web ou usando uma chamada de SDK móvel ([!DNL offlineEnabled=true]) em um aplicativo móvel.
* **Dados** sem carimbo de data e hora. A Adobe define um carimbo de data e hora em dados sem carimbo de data e hora em um conjunto de relatórios quando os dados acessam os servidores de coleta.


Um conjunto de relatórios pode ter uma das seguintes configurações de carimbo de data e hora:

* Carimbos de data e hora não permitidos (a configuração da visitorID é suportada)
* Carimbos de data e hora são obrigatórios (a configuração da visitorID não é suportada)
* Carimbos de data e hora opcionais (a configuração da visitorID é suportada, mas não em hits marcados pelo carimbo de data e hora)

## Sobre os recursos dos carimbos de data e hora opcionais {#section_63B2FA9A2AB24B3993E84D2C2B4BF2CE}

Carimbos opcionais de data e hora permitem integrar e gerar relatórios em vários conjuntos de relatórios com ou sem carimbos de data e hora do lado do cliente. Com os carimbos opcionais de data e hora, você pode atualizar seu aplicativo para usar carimbos de data e hora enquanto ainda usa dados sem carimbos de data e hora do aplicativo anterior.

| Em versões anteriores... | Além disso... |
|--- |--- |
| Não foi possível enviar dados com carimbo de data e hora para um conjunto de relatórios global sem carimbo de data e hora. Consequentemente, os dados de ocorrência enviados de dispositivos offline eram descartados quando adicionados a um conjunto de relatórios sem carimbo de data e hora. <br/><br/>Consequentemente, os dados de ocorrência enviados de dados offline eram descartados quando adicionados a um conjunto de relatórios sem carimbo de data e hora. | Para atualizar um aplicativo com o objetivo de coletar e usar carimbos de data e hora, era necessário empregar um novo conjunto de relatórios. <br/>Não era possível salvar no conjunto de relatórios atual ou integrar dados existentes ao atualizar o aplicativo para usar carimbos de data e hora. |

**Com os carimbos opcionais de data e hora**, é possível integrar dados sem carimbos de data e hora de um site com dados offline de dispositivos móveis ou atualizar o aplicativo sem carimbos de data e hora para um aplicativo com esses carimbos.

## Combinação de dados em um conjunto de relatórios global {#section_5BE3BDF56007402BB1F5C3144D5FE1E0}

A combinação de dados em um conjunto de relatórios global pode ser feita de várias formas, incluindo a inserção de tags em vários conjuntos, regras do Vista e arquivos em lote de fontes offline.

>[!IMPORTANT] Planeje cuidadosamente o design de cada conjunto de dados do componente para que a combinação faça sentido no conjunto de relatórios global.

## Práticas recomendadas para uso de carimbos de data e hora {#section_9436394E5D7E4F8A8B369B6D11BB2B2B}

Veja a seguir algumas práticas recomendadas e alguns requisitos e restrições que devem ser observados ao integrar dados com e sem carimbos de data e hora.

* Em geral, os carimbos de data e hora para determinado visitante ou visita devem chegar à Adobe na ordem cronológica correta.

   Dados fora de ordem podem incluir dados que chegam tarde da coleta de dados offline e ocorrências que chegam tarde, ou relógios fora de sincronização em dispositivos móveis offline. Dados fora de ordem podem afetar negativamente os cálculos de tempo (como valores de tempo gasto), a atribuição (persistência de eVar), as contagens de número/visita e os relatórios de definição de caminho.

* Não é recomendado usar carimbos de data e hora ao configurar uma [s.visitorID](https://marketing.adobe.com/resources/help/pt_BR/sc/implement/visid_custom.html) . Isso pode levar a dados fora de ordem.

* Aplicativos híbridos compostos de um aplicativo (com carimbos de data e hora, dados offline) que abrem um navegador da Web (dados ativos e sem carimbos de data e hora) não devem usar carimbos de data e hora. Isso resulta em relatórios impreciso da sessão.

   Além disso, os aplicativos híbridos não devem definir uma ID de visitante.
