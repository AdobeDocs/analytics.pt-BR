---
description: Perguntas frequentes sobre recursos, funcionalidades e problemas relacionados ao encaminhamento pelo lado do servidor.
seo-description: Perguntas frequentes sobre recursos, funcionalidades e problemas relacionados ao encaminhamento pelo lado do servidor.
seo-title: Perguntas frequentes sobre o encaminhamento pelo lado do servidor
title: Perguntas frequentes sobre o encaminhamento pelo lado do servidor
uuid: ecd0bc9b-ebf7-414e-88a2-ebba3fd75c92
translation-type: tm+mt
source-git-commit: ed22e0520bf1c7427ead039fb1d0391f2f1e567f

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
| P: E se eu tiver conjuntos de relatórios com tags de vários conjuntos mapeados para organizações separadas da Experience Cloud? | Você nunca deve enviar dados de uma única ocorrência do Analytics para dois conjuntos de relatórios que pertencem a Organizações separadas da Experience Cloud, mas se isso ocorrer, encaminharemos a ocorrência somente para a Organização da Experience Cloud que corresponde à configuração do Serviço de identidade na página. |
| P: E se eu tiver tags de vários conjuntos e apenas um dos meus conjuntos de relatórios estiver mapeado para minha organização da Experience Cloud e o outro não? | Encaminharemos a ocorrência para o servidor de coleta de dados correspondente para a Experience Cloud Org em seu conjunto de relatórios mapeado. No entanto, como o conjunto de relatórios não mapeado não terá uma fonte de dados associada no Audience Manager, nenhum dado será registrado para o conjunto de relatórios não mapeado no Audience Manager. |
| P: E se eu tiver um conjunto de relatórios mapeado para várias organizações da Experience Cloud? | O Analytics considerará este conjunto de relatórios como não mapeado e não permitirá que o encaminhamento pelo lado do servidor seja ativado para este conjunto de relatórios. Entre em contato com o atendimento ao cliente para resolver esse problema de mapeamento. |
| P: O método de encaminhamento pelo lado do servidor baseado no conjunto de relatórios será mais lento do que o encaminhamento pelo lado do servidor baseado no servidor de rastreamento? | Não, o tempo de resposta será o mesmo. |
| P: E se tivermos duas Organizações da Experience Cloud (ou instâncias do AAM) e desejarmos compartilhar dados entre as Organizações da Experience Cloud? É possível encaminhar pelo lado do servidor uma única ocorrência do Analytics para várias organizações da Experience Cloud? | Não. Se você precisar compartilhar dados coletados em uma organização da Experience Cloud para outra organização da Experience Cloud, recomendamos enviar qualquer público aplicável de uma instância do Audience Manager para outra usando o mercado de público-alvo. |
| P: O encaminhamento pelo lado do servidor resultará em cobrança adicional no Audience Manager ou no Analytics? | No Analytics, nenhuma cobrança adicional ocorrerá. No Audience Manager, as ocorrências encaminhadas são tratadas como qualquer outra ocorrência e são cobradas.  É por isso que é importante não ter o DIL e encaminhamento pelo lado do servidor habilitados ao mesmo tempo, o que pode causar cobrança duplicada, bem como duplicação de dados. |

>[!MORELIKETHIS]
>
>* [Encaminhamento pelo lado do servidor](/help/admin/admin/c-server-side-forwarding/ssf.md)

