---
description: Respostas a perguntas que você pode se fazer ao implantar o Audience Analytics.
solution: Experience Cloud
title: Perguntas frequentes sobre o Audience Analytics
feature: Audience Analytics
exl-id: 86e7967c-030c-44d6-8294-e7e6d41f6fc3
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '1090'
ht-degree: 31%

---

# Perguntas frequentes

Respostas a perguntas que você pode se fazer ao implantar o Audience Analytics.

## Perguntas frequentes jurídicas {#legal}

+++ Como faço para saber se tenho Informações de identificação pessoal (PII) nos dados do Analytics? E se sim, o que devo fazer sobre isso?

Se você tiver emails/endereços/etc em uma prop ou eVar, considere colocar os dados em hash durante a coleta. Se seu país considera endereços IP como PII, [ative a ofuscação de IP](/help/admin/tools/exclude-ip.md). Fale com o administrador do Analytics para ver o que você está coletando. Converse com o departamento jurídico para saber o que eles consideram sobre PII.

+++

+++ Como saber se meus conjuntos de relatórios fazem personalização no local ou direcionamento externo/no local?

Isso não se aplica ao envio de dados do Adobe Analytics para o Adobe Audience Manager. Pergunte a si mesmo:

* Você compartilhará um segmento compartilhado do Analytics com uma dimensão MCA de volta para a Experience Cloud?

* Você está exportando (por meio de feeds de dados) para um sistema de Business Intelligence (BI) usado para esse propósito?

+++

## Perguntas frequentes específicas sobre o Adobe Audience Manager {#aam-specific}

+++ Como criar um destino do Analytics no Audience Manager?

Consulte [Configurar um destino do Analytics no Adobe Audience Manager](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/destinations/experience-cloud-destinations/create-analytics-destination.html?lang=pt-BR)&quot;.

+++

+++ Depois de criar e salvar um destino do Analytics, quanto tempo leva até que os dados sejam exibidos nos conjuntos de relatórios selecionados?

Pode demorar algumas horas para preencher seus conjuntos de relatórios com novos dados.

+++

+++ Criei um novo destino do Analytics, mas não o vejo na seção Mapeamentos de destino dos meus segmentos disponíveis. Para onde foi esse destino ou como o encontro?

Um destino do Analytics desaparece da seção de Mapeamentos de destino de um segmento ao selecionar a opção **[!UICONTROL Mapear automaticamente todos os segmentos atuais e futuros]** em **[!UICONTROL Mapeamentos de segmentos]**. Para evitar que isso aconteça, selecione **[!UICONTROL Mapear segmentos manualmente]** em vez da opção automática.

+++

Terei acesso a todas as informações do Adobe Audience Manager no Analytics agora?

Não, você terá acesso somente a dados relacionados a pessoas que visitam seu site durante ou depois da habilitação do Audience Manager Audiences e durante/depois da qualificação de segmentos.

+++

+++ Isso fornecerá um público endereçável total por segmento?

Não necessariamente. Isso indica a quantidade de visitantes no segmento que acessaram o site durante ou após a qualificação de segmentos.

+++

+++ Como isso difere do destino de cookie herdado para o Analytics?

Segmentos são qualificados e retornados em tempo real, na mesma ocorrência. Nomes amigáveis são exibidos automaticamente.

+++

+++ E se alguns dos meus conjuntos de relatórios tiverem dados pessoais e outros não?&lt;

Dica: crie dois destinos; adicione os conjuntos de relatórios com dados pessoais a um destino e os conjuntos de relatórios sem dados pessoais ao outro destino.

+++

## Perguntas frequentes específicas sobre o Analytics {#aa-specific}

+++ Essa integração aparecerá como uma dimensão ou segmento no Analytics?

Como dimensões: ID e nome de públicos-alvo.

+++

+++Onde posso usar essas dimensões no Analytics?

Em todos os lugares; eles são tratados como qualquer outra dimensão coletada no Analytics.

+++

+++ Por que não vejo dados sendo inseridos no Analytics?

É provável que você tenha controles de privacidade do Adobe Audience Manager em conflito entre a fonte de dados e o destino.

+++

+++ Por que alguns de meus segmentos estão ausentes no Analytics, apesar de eu ter selecionado para enviar todos os segmentos?&lt;

* Seus controles de exportação de dados do Adobe Audience Manager no destino e nas fontes de dados dos segmentos podem estar em conflito, o que evita que certos segmentos sejam enviados.

* Se você estiver usando características de dados de terceiros em seus segmentos, tais segmentos não poderão ser compartilhados a destinos (um conjunto de conjuntos de relatórios) que contêm dados pessoais.

+++

+++ Por que vejo &quot;Limite de público-alvo atingido&quot; no meu relatório do Analytics? (Observação: isso também será representado como ID de público-alvo = -1 e `::max_audiences_exceeded::` no Data Warehouse)

Por padrão, a integração do Audience Analytics para o Adobe Audience Manager envia todos os segmentos para os quais um visitante se qualifica, com base em cada ocorrência, para o Analytics. Se um visitante pertencer a mais de 150 segmentos do Adobe Audience Manager em uma única ocorrência, os **150 segmentos qualificados mais recentemente** serão enviados ao Analytics, enquanto a lista restante será truncada. Um sinalizador adicional é enviado ao Analytics, para avisar que a lista de segmentos está truncada, e é exibido como “Limite de público-alvo atingido” na dimensão Nome de público-alvo e “-1” na dimensão ID de público-alvo.

Mesmo sendo improvável que um visitante seja qualificado para mais de 150 segmentos em uma única ocorrência, há uma pequena chance de isso ocorrer. Se você encontrar o erro “Limite de público-alvo atingido” em seu relatório, há duas opções:

* Opção 1: continue permitindo que a integração funcione no estado pronto para uso, enviando os 150 segmentos qualificados mais recentemente para um visitante específico.

* Opção 2: no Adobe Audience Manager, escolha os 150 segmentos mais importantes para sua empresa na integração. Em seguida, o Adobe Audience Manager verifica os visitantes em relação apenas a esses 150 segmentos. A desvantagem dessa abordagem é que você receberá somente esses 150 segmentos por todos os visitantes. Por outro lado, a abordagem da Opção 1 pode fornecer segmentos ilimitados devido à natureza “por ocorrência” da integração.

+++

+++ As chamadas de servidor adicionais serão cobradas do Analytics por essa integração?

Não. Os públicos-alvo da Adobe Audience Manager são incorporados ao lado do servidor de ocorrências do Analytics. Isso não causa chamadas de servidor adicionais para o Analytics (primário ou secundário).

+++

## Perguntas frequentes sobre o encaminhamento pelo lado do servidor (SSF) {#SSF}

+++ Se o SSF herdado estiver implementado, também preciso ir para o Administrador do Analytics e ativar o SSF do conjunto de relatórios?

Sim. Na configuração de destino do Adobe Audience Manager, você verá apenas conjuntos de relatórios com o SSF ativado.

+++

+++ Por que não consigo ativar certos conjuntos de relatórios para SSF no Analytics Admin?

Somente conjuntos mapeados para a sua Organização Experience Cloud podem ser habilitados.

Para obter mais perguntas frequentes sobre esse tópico, consulte [Perguntas frequentes sobre o encaminhamento pelo lado do servidor](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-faq.md).

+++

## Perguntas frequentes gerais {#section_E55410BBFB624AAFB87ADCF7F036DDA3}

+++ Por que as contagens de visitantes do segmento são diferentes no Audience Manager e no Analytics?

Consulte [Diferenças na contagem de visitantes](/help/integrate/c-audience-analytics/visitor-count-reconciliation.md).

+++

+++ Qual é a diferença entre &quot;públicos-alvo&quot; no Adobe Audience Manager e &quot;segmentos&quot; no Analytics?

Consulte [Entender os segmentos no Analytics e no Audience Manager](/help/integrate/c-audience-analytics/aam-analytics-segments.md). Os públicos-alvo da Adobe Audience Manager são enviados e compartilhados como componentes de &quot;dimensão&quot; a serem usados no Analytics. Elas não são exibidas como segmentos no Construtor de segmentos, por exemplo, mas como dimensões com as quais você pode construir segmentos.

+++

+++ Qual é a diferença entre os atributos do cliente e os dados do cliente integrados no Adobe Audience Manager?

Os atributos do cliente não são baseados em tempo; eles são aplicados retroativamente e prosseguem. Os dados integrados do Adobe Audience Manager são baseados em tempo e somente progressivos. Além disso, os atributos do cliente são uma tabela de pesquisa para IDs de visitante do Experience Cloud, enquanto a integração do Adobe Audience Manager é de dados compilados em cada ocorrência para um visitante.

+++

+++ E quanto às abordagens herdadas para esse problema, por exemplo, o beta antigo ou os destinos de cookies do plug-in do Consulting?

Recomendamos que você implemente a nova integração e remova as anteriores.

+++
