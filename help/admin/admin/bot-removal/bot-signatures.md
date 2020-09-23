---
title: Assinaturas comuns do robô
description: Reconhecer os identificadores comuns de bots.
translation-type: tm+mt
source-git-commit: 2f4c54ec57eeddc03f0b0d12a0a7f391e36ab0fc
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 0%

---


# Assinaturas comuns do robô

Embora a identificação de bots em um conjunto de dados seja diferente dependendo do ambiente, há algumas maneiras comuns de identificar bots.

## Número elevado de visualizações de página por visita

Você pode obter um relatório de Data Warehouse com endereço IP, visualizações de página e visitantes únicos. Em seguida, crie um &#x200B; de cálculo &#x200B; no Excel para visualizações de página por visita e classifique do mais alto para o mais baixo. Os bots geralmente têm um número muito alto de visualizações de página por visita (de várias centenas a milhares). Você verá um declínio acentuado à medida que você se move para o tráfego real.

## Sem quem indicou

Os bots normalmente não têm um URL de referência. Na segmentação, isso pode ser filtrado como `Referring Domain equals Typed/Bookmarked`.

## Agentes de usuário estranhos

Os bots geralmente usam agentes de usuário personalizados que não são classificados na dimensão Navegadores ou exibidos como uma `unknown` versão de um navegador padrão. Safari desconhecido e Opera desconhecida têm uma probabilidade extremamente alta de serem bots.

## Sistemas operacionais Linux ou &quot;Não especificado&quot;

Não queremos desacreditar o grande sistema operacional Linux open-source, mas aparentemente os robôs gostam de defini-lo como seu sistema operacional. No entanto, tenha cuidado ao excluir o tráfego legítimo dos usuários do Linux. Bots também gostam de não definir um sistema operacional, que pode ser segmentado como `Operating System &#x200B;equals Not Specified`.

## Visualizações de página = Visitas = Visitantes únicos

Isso se aplica especialmente ao relatório do agente do usuário. Como você pode ver na captura de tela abaixo, a &quot;versão desconhecida&quot; desses navegadores tem quase o mesmo número de visitantes que visitantes únicos (e quase o mesmo número de visualizações de página). Isso pode ser isolado na segmentação ao criar um container [!UICONTROL Incluir] para `Single Page Visits equals Enabled` ou `Hit Depth is less than 2`.

![](assets/bots-browsers-unknown.png)

## Visita número 1

Os bots normalmente recebem uma nova ID de visitante toda vez que são executados, incorrendo em apenas uma visita sempre e todo o tráfego consiste em uma número de visita 1.

## Resoluções mais baixas do monitor

Os usuários modernos têm monitores de resolução muito mais alta do que em anos anteriores. Ocorrências com as seguintes resoluções parecem ser muito populares para bots:

* 1024 x 768&#x200B;&#x200B;
* 1366 x 768
* 1600 x 864
* 800 x 600
* 1600 x 1200
* Não especificado
* 1024 x 667

## País + Fuso horário incompatível

Você notaria um desencontro entre o país de origem e o fuso horário. Por exemplo, o local pode ser os Estados Unidos, mas o fuso horário pode ser GMT.

![](assets/bots-country-time-zone.png)

## Não conectado

O usuário não faz logon em nenhum momento de sua visita e suas eVars de identificação de usuário não persistem das visitas anteriores. Enquanto alguns bots podem ser configurados para autenticação, a maioria não é tão inteligente.

## Nenhum KPIs em visita

Os bots normalmente não adicionam produtos a um carrinho de compras nem fazem check-out. Na maioria das vezes, eles não estão enviando formulários de cliente potencial ou outros eventos de sucesso, mas alguns bots enviam formulários HTML simples. &#x200B;

## Cadeia de query específica presente

Às vezes, os bots tentam interromper o cache ou interromper sites acessando URLs malformados ou URLs que não existem (como as páginas de administrador LAMP ou Wordpress típicas) ou anexando strings de query específicas.

## Endereços IP originados de plataformas de computação distribuída

Serviços de hospedagem na Web, como Amazon Web Services ou Google Cloud, podem ser usados como bot farms. Esses endereços IP estão em alto risco de serem bots:
&#x200B;
* [Google Cloud](https://cloud.google.com/compute/): START de endereço IP com `&#x200B;35.199` ou `35.194&#x200B;`
