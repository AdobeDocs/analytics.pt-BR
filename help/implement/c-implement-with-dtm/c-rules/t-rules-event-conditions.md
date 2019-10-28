---
description: As condições determinam quando uma regra baseada em eventos é acionada.
keywords: Dynamic Tag Management, regra, criar regra, nova regra, regra baseada em evento, atrasar ativação de link, aplicar manipulador de eventos diretamente ao elemento, propagação, propagação de eventos
seo-description: As condições determinam quando uma regra baseada em eventos é acionada.
seo-title: Criar condições para regras baseadas em eventos
solution: Experience Cloud, Analytics, Target, Dynamic Tag Management
title: Criar condições para regras baseadas em eventos
uuid: a847391c-5aec-4d64-8a35-388587731598
translation-type: ht
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Criar condições para regras baseadas em eventos

As condições determinam quando uma regra baseada em eventos é acionada.

1. Selecione o tipo de interação que deseja rastrear como cliques de mouse, ou o envio de um formulário.

   ![](assets/condition-event-based.png)

   Para obter mais informações, consulte [Tipos de evento](https://marketing.adobe.com/resources/help/pt_BR/dtm/event_types.html) na Documentação do produto Dynamic Tag Management.

1. Ative as opções a seguir se necessário:

   | Elemento | Descrição |
   |--- |--- |
   | Atrasar ativação de link | Ative se o evento ativar um link e você desejar que o link seja atrasado até que o evento tenha tempo de ser acionado. |
   | Aplicar o manipulador de evento diretamente no elemento | Aplica o manipulador de evento no elemento específico que está marcado. Essa configuração está vinculada ao conceito do efeito de bolhas e camadas em um navegador. |

   Por exemplo, ao clicar em uma imagem dentro de uma tag de âncora como `<a href="abc.html"><img src="xyz.png"/></a>`, é de se esperar que o clique esteja associado à tag de âncora, visto que a tag está no fluxo de propagação. Contudo, quando você inspeciona o clique nas ferramentas do desenvolvedor, o clique pode na verdade afetar somente a tag `<img>`. Para garantir que o evento seja manipulado corretamente, associe o clique à tag `<img>` e não dependa do navegador para propagar o clique para um elemento principal. Um evento como um clique pode gerar bolhas para `<body>`. É importante entender onde o evento está realmente vinculado, e direcioná-lo especificamente para garantir que a regra seja acionada corretamente.

   *Efeito de bolha* significa que o evento é capturado primeiro e manipulado pelo elemento mais interno e propagado para os elementos externos.

1. Indique o nome da tag que deseja rastrear e outras propriedades da tag que você deseja corresponder.

   ![](assets/condition-event-based2.png)

   Consulte [Uso do seletor de CSS](https://marketing.adobe.com/resources/help/pt_BR/dtm/css-selector.html) na Documentação do produto Dynamic Tag Management, para obter informações sobre a localização da tag de elemento correta.

1. Selecione e configure outros critérios ou tipos de condição que deseja vincular à regra.

   ![](assets/condition-event-based3.png)

1. Indique sua preferência com respeito ao efeito de bolha do evento.

   O efeito de bolha do evento é uma forma de propagação de evento no DOM do HTML.

   | Se você... | Marque esta opção |
   |--- |--- |
   | Quer interações relacionadas em elementos secundários do seletor da regra identificada para acionar a regra. | Permitir que eventos em elementos secundários borbulhem. |
   | Quer impedir o efeito de bolha quando o elemento secundário já acionar seu próprio evento. | Não permitir se o elemento secundário já acionar o evento. |
   | Não deseja que os eventos do seletor de regras identificado ultrapassem o próprio elemento na hierarquia de eventos. | Não permitir que os eventos borbulhem até os principais. |
