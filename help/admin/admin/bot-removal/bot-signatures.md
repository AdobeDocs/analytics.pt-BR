---
title: Assinaturas comuns do bot
description: Reconheça os identificadores comuns de bots.
exl-id: 57622af6-c1d3-4ef1-b3e6-10c14f04a55c
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '521'
ht-degree: 100%

---

# Assinaturas comuns do bot

Embora a identificação de bots em um conjunto de dados seja diferente dependendo do ambiente, estas são algumas maneiras comuns de identificar bots.

## Alto número de exibições de página por visita

Você pode obter um relatório do Data Warehouse com endereço IP, exibições de página e visitantes únicos. Em seguida, crie um cálculo no Excel para exibições de página por visita e classifique do mais alto para o mais baixo. Os bots geralmente têm um número muito alto de exibições de página por visita (várias centenas a milhares). Você verá um declínio acentuado à medida que passar para o tráfego real.

## Sem referenciador

Os bots normalmente não têm um URL de referência. Na segmentação, pode ser filtrado como `Referring Domain equals Typed/Bookmarked`.

## Agentes de usuário estranhos

Os bots geralmente usam agentes de usuário personalizados que não são classificados na dimensão Navegadores ou exibidos como uma versão `unknown` de um navegador padrão. O Safari desconhecido e o Opera desconhecido têm uma probabilidade extremamente alta de serem bots.

## Sistemas operacionais Linux ou &quot;Não especificados&quot;

Não queremos desacreditar o grande sistema operacional Linux de código aberto, mas aparentemente os bots gostam de defini-lo como seu sistema operacional. No entanto, tenha cuidado com a exclusão de tráfego legítimo de usuários do Linux. Os bots também gostam de não definir um sistema operacional, que pode ser segmentado como `Operating System &#x200B;equals Not Specified`.

## Exibições de página = Visitas = Visitantes únicos

Isso se aplica especialmente ao relatório do agente do usuário. Como você pode ver na captura de tela abaixo, a &quot;versão desconhecida&quot; desses navegadores tem quase o mesmo número de visitantes que visitantes únicos (e quase o mesmo número de exibições de página). Isso pode ser isolado na segmentação por meio da criação de um container [!UICONTROL Incluir] para `Single Page Visits equals Enabled` ou `Hit Depth is less than 2`.

![](assets/bots-browsers-unknown.png)

## Número de visitas de 1

Os bots geralmente recebem uma nova ID de visitante sempre que são executados, incorrendo assim em apenas uma visita, e todo o tráfego consiste em uma visita.

## Resoluções mais baixas do monitor

Usuários modernos têm monitores de resolução muito mais altos do que em anos anteriores. As ocorrências com as seguintes resoluções parecem ser muito populares para bots:

* 1024 x 768&#x200B;&#x200B;
* 1366 x 768
* 1600 x 864
* 800 x 600
* 1600 x 1200
* Não especificado
* 1024 x 667

## Incompatibilidade de país + fuso horário

Você nota uma incompatibilidade entre o país de origem e o fuso horário. Por exemplo, o local pode ser os Estados Unidos, mas o fuso horário pode ser GMT.

![](assets/bots-country-time-zone.png)

## Sem logon

O usuário não faz logon em nenhum ponto de sua visita e suas eVars de identificação de usuário não são mantidas de visitas anteriores. Embora alguns bots possam ser configurados para autenticação, a maioria não é tão inteligente.

## Nenhum KPI na visita

Os bots normalmente não adicionam produtos a um carrinho de compras nem fazem check-out. Na maioria das vezes, eles não enviam formulários de cliente potencial ou outros eventos de sucesso; alguns bots enviam formulários HTML simples.

## Sequência de consulta específica presente

Às vezes, os bots tentam danificar o cache ou violar sites de outra forma, acessando URLs malformados ou que não existem (como as páginas de administrador típicas do LAMP ou do Wordpress) ou anexando strings de consulta específicas.

## Endereços IP originados de plataformas de computação distribuída

Os serviços de hospedagem na Web, como Amazon Web Services ou Google Cloud, podem ser usados como farms de bots. Estes endereços IP têm alto risco de serem bots:
&#x200B;
* [Google Cloud](https://cloud.google.com/compute/): o endereço IP começa com `&#x200B;35.199` ou `35.194&#x200B;`
