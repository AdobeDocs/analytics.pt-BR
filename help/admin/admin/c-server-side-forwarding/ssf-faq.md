---
description: Perguntas frequentes sobre recursos, funcionalidades e problemas relacionados ao encaminhamento pelo lado do servidor.
seo-description: Perguntas frequentes sobre recursos, funcionalidades e problemas relacionados ao encaminhamento pelo lado do servidor.
seo-title: Perguntas frequentes sobre o encaminhamento pelo lado do servidor
title: Perguntas frequentes sobre o encaminhamento pelo lado do servidor
uuid: asu 0 bc 9 b-ebf 7-414 e -88 a 2-ebba 3 fd 75 c 92
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Perguntas frequentes sobre o encaminhamento pelo lado do servidor

Perguntas frequentes sobre recursos, funcionalidades e problemas relacionados ao encaminhamento pelo lado do servidor.

## Servidores de rastreamento {#section_28E5BECC2034484AB9726E513F2CCFB7}

| Pergunta | Resposta |
|--- |--- |
| P: E se eu estiver usando atualmente o encaminhamento pelo lado do servidor herdado baseado no servidor de rastreamento? | O método de encaminhamento pelo lado do servidor baseado no servidor de rastreamento herdado continuará a encaminhar dados do Analytics para o Audience Manager; contudo, se você quiser enviar os segmentos do Audience Manager para o Analytics, o novo encaminhamento pelo lado do servidor baseado no conjunto de relatórios será necessário. Além disso, não há nenhum problema em habilitar um conjunto de relatórios para o encaminhamento pelo lado do servidor sobre sua configuração de servidor de rastreamento; a nova configuração de encaminhamento pelo lado do servidor do conjunto de relatórios será usada sempre que houver um conflito. |
| P: Devo migrar o encaminhamento pelo lado do servidor baseado no servidor de rastreamento herdado para o novo encaminhamento pelo lado do servidor baseado no conjunto de relatórios? | Continuaremos a oferecer suporte ao encaminhamento pelo lado do servidor baseado no servidor de rastreamento no futuro. Contudo, se você quiser tirar proveito da integração do Audience Manager com o Analytics (compartilhamento de segmentos para o Analytics), você precisará habilitar o novo encaminhamento pelo lado do servidor baseado no conjunto de relatórios para todos os conjuntos de relatórios aplicáveis. Entretanto, não há nenhum motivo urgente para desativar o encaminhamento pelo lado do servidor baseado no servidor de rastreamento herdado. |

## Aplicação de tags e criação de relatórios {#section_71391BA901AC47B9A2286281644FF281}

| Pergunta | Resposta |
|--- |--- |
| P: E se eu tiver uma tag de vários conjuntos no meu site? O encaminhamento pelo lado do servidor duplicará minhas chamadas de servidor para o Audience Manager? | Não, uma ocorrência que é encaminhada do Analytics para o Audience Manager somente será encaminhada uma vez para o Audience Manager, independentemente do número de conjuntos de relatórios na ocorrência. Se você tiver fontes de dados correspondentes no Audience Manager para cada um dos conjuntos de relatórios na ocorrência, cada um será preenchido apropriadamente a partir dessa única ocorrência.  Tenha em mente, no entanto, que, se você usa atualmente a coleta de dados no lado do cliente (DIL) e habilitar o encaminhamento pelo lado do servidor sem instalar o módulo de Gerenciamento de público-alvo, você duplicará suas chamadas de servidor para o Audience Manager, independentemente do número de conjuntos de relatórios que você possui na sua ocorrência do Analytics. |
| P: O que acontece se eu tiver conjuntos de relatórios marcados de vários conjuntos que estão mapeados para separar Organizações da Experience Cloud? | Você nunca deve enviar dados de uma única ocorrência do Analytics para dois conjuntos de relatórios pertencentes a Organizações da Experience Cloud separadas, mas se isso ocorrer, encaminharemos somente a ocorrência à Organização da Experience Cloud correspondente à configuração do Serviço de identidade na página. |
| P: E se eu tiver uma marcação de vários conjuntos e apenas um dos meus conjuntos de relatórios estiver mapeado para minha Organização da Experience Cloud e o outro não? | Encaminharemos a ocorrência ao servidor de coleção de dados correspondente para a Organização da Experience Cloud no conjunto de relatórios mapeado. No entanto, como o conjunto de relatórios não mapeado não terá uma fonte de dados associada no Audience Manager, nenhum dado será gravado para o conjunto de relatórios não mapeado no Audience Manager. |
| P: E se eu tiver um conjunto de relatórios mapeado para várias Organizações da Experience Cloud? | O Analytics considerará este conjunto de relatórios como não mapeado e não permitirá que o encaminhamento pelo lado do servidor seja ativado para este conjunto de relatórios. Entre em contato com o atendimento ao cliente para resolver esse problema de mapeamento. |
| P: O método de encaminhamento pelo lado do servidor baseado no conjunto de relatórios será mais lento do que o encaminhamento pelo lado do servidor baseado no servidor de rastreamento? | Não, o tempo de resposta será o mesmo. |
| P: E se tivermos duas Organizações da Experience Cloud (ou instâncias do AAM) e quiser compartilhar dados entre as Organizações da Experience Cloud? Posso encaminhar o servidor para uma única ocorrência do Analytics a várias Organizações da Experience Cloud? | Não. Se você precisar compartilhar dados coletados em uma Organização da Experience Cloud para outra Organização da Experience Cloud, recomendamos enviar qualquer público aplicável de uma instância do Audience Manager a outra usando o mercado de público-alvo. |
| P: O encaminhamento pelo lado do servidor resultará em cobrança adicional no Audience Manager ou no Analytics? | No Analytics, nenhuma cobrança adicional ocorrerá. No Audience Manager, as ocorrências encaminhadas são tratadas como qualquer outra ocorrência e são cobradas.  É por isso que é importante não ter o DIL e encaminhamento pelo lado do servidor habilitados ao mesmo tempo, o que pode causar cobrança duplicada, bem como duplicação de dados. |

>[!MORE_LIKE_THIS]
>
>* [Encaminhamento pelo lado do servidor](ssf.md#concept_9563FCADF29748928E770EC5221B2685)

