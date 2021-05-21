---
title: Coleta de dados regionais
description: Informação sobre a coleta de dados regionais
exl-id: 295e9736-2a58-48a8-9968-5dfa33b70d95
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '475'
ht-degree: 100%

---

# Coleta de dados regionais

A Adobe Experience Cloud usa a RDC (Coleta de dados regionais) para que as interações entre os usuários finais e a Adobe Experience Cloud ocorram o mais próximo possível dos usuários finais. Isso melhora o desempenho do seu site/aplicativo e garante que os dados sejam coletados o mais rápido possível para otimizar a experiência do usuário final. Uma vez que os dados das propriedades digitais forem coletados regionalmente em um Centro de coleta de dados (DCC), eles serão transferidos por uma conexão segura para um Centro de processamento de dados (DPC), onde serão processados e disponibilizados para os produtos na Adobe Experience Cloud.

>[!IMPORTANT]
>
>O pacote de complemento RDC da China (Otimização de desempenho na China) é um complemento pago do Adobe Analytics. A Otimização do desempenho da Adobe na China continental permite que os clientes da China enviem dados diretamente para o nó de borda da China, em vez de outros locais globalmente. Isso melhora os tempos de carregamento de páginas e a precisão dos dados em comparação ao envio de dados para nós fora da China. Entre em contato com o representante da Adobe Sales para obter mais informações.

Atualmente, a RDC inclui as seguintes localidades (sujeitas a mudança)

## Coleta de dados HTTP e de terceiros

| Tipo da RDC | Centros de coleta de dados |
|---------------------|-------------------|
| Padrão | Oregon, Virgínia, Irlanda, Paris, Mumbai, Singapura, Tóquio, Sydney, China* |

Observação: se sua solicitação de imagem do Analytics é enviada para os endpoints `adobedc` `2o7.net` ou `omtrdc.net`, você tem a coleção de dados de terceiros. É possível determinar se um desses endpoints aparecem na URL de suas solicitações.

*O RDC da China exige o pacote do complemento da China. Consulte a nota &quot;Importante&quot; acima.

## Coleta de dados HTTPS de terceiros

| Tipo da RDC | Centros de coleta de dados |
|---------------------|-------------------|
| Global (Padrão) | Oregon, Virgínia, Irlanda, Paris, Mumbai, Singapura, Tóquio, Sydney |
| Somente Américas | Oregon, Virgínia |
| Somente Europa | Irlanda, Paris |
| Somente Pacífico Asiático | Mumbai, Singapura, Tóquio, Sidney |
| Somente China* | Pequim |

*O RDC da China exige o pacote do complemento da China. Consulte a nota &quot;Importante&quot; acima.

Observação: a Experience Edge Global oferece o melhor desempenho aos usuários finais.  Se quiser usar um tipo de RDC alternativo, entre em contato com o Atendimento ao cliente da Adobe para obter assistência.

## Benefícios da RDC

| Benefícios | Descrição |
| --- | --- |
| Desempenho | Com o RDC, seus visitantes se conectam ao DCC mais próximo. Isso fornece o tempo de resposta mais rápido, resultando em rastreamento mais preciso e em tempos de carregamento mais rápidos. |
| Redundância | No caso de uma interrupção na comunicação com um DCC, a coleção de dados é encaminhada diretamente ao DCC mais próximo, garantindo a continuidade do serviço. |
| Redundância | No caso de uma interrupção na comunicação entre o DCC e a DPC, a infraestrutura da RDC da Adobe salva os dados localmente e, em seguida, os encaminha para a DPC quando as comunicações forem restauradas. |

## Como a RDC funciona

A lista a seguir descreve o processo de coleta de dados usado pela Adobe:

1. A DNS corrige automaticamente o nome de host da coleta para o endereço IP do Centro de coleta de dados mais próximo do visitante.
1. O visitante envia os dados para o local.
1. Os dados são encaminhados imediatamente por meio de uma conexão segura para o Centro de processamento de dados, onde é processado e disponibilizado para os produtos na Adobe Experience Cloud.
