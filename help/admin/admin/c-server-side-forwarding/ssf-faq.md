---
description: Perguntas frequentes sobre recursos, funcionalidades e problemas relacionados ao encaminhamento pelo lado do servidor.
title: Perguntas frequentes sobre o encaminhamento pelo lado do servidor
uuid: ecd0bc9b-ebf7-414e-88a2-ebba3fd75c92
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

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
| P: E se eu tiver conjuntos de relatórios com tags de vários conjuntos que estejam mapeados a organizações separadas da Experience Cloud? | Você nunca deve enviar dados de uma única ocorrência do Analytics para dois conjuntos de relatórios pertencentes a organizações da Experience Cloud separadas, mas se isso ocorrer, apenas encaminharemos a ocorrência para a organização da Experience Cloud correspondente à configuração do serviço da Experience Cloud ID na página. |
| P: E se eu tiver uma tag de vários conjuntos e apenas um dos meus conjuntos de relatórios for mapeado à minha organização da Experience Cloud e o outro não? | Nós encaminharemos a ocorrência para o servidor de coleta de dados correspondente à organização da Experience Cloud em seu conjunto de relatórios mapeado. Contudo, como o conjunto de relatórios não mapeado não terá uma fonte de dados associada no Audience Manager, nenhum dado será gravado para o conjunto de relatórios não mapeado no Audience Manager. |
| P: E se eu tiver um conjunto de relatórios que esteja mapeado a várias organizações da Experience Cloud? | O Analytics considerará este conjunto de relatórios como não mapeado e não permitirá que o encaminhamento pelo lado do servidor seja ativado para este conjunto de relatórios. Entre em contato com o atendimento ao cliente para resolver esse problema de mapeamento. |
| P: O método de encaminhamento pelo lado do servidor baseado no conjunto de relatórios será mais lento do que o encaminhamento pelo lado do servidor baseado no servidor de rastreamento? | Não, o tempo de resposta será o mesmo. |
| P: E se nós tivermos duas organizações da Experience Cloud (ou instâncias AAM) e quisermos compartilhar dados entre as duas organizações da Experience Cloud? Posso encaminhar no lado do servidor uma única ocorrência do Analytics para várias organizações da Experience Cloud? | Não. Se você precisar compartilhar os dados coletados de uma organização da Experience Cloud para outra, recomendamos enviar qualquer público aplicável de uma instância do Audience Manager para outra usando o Audience Marketplace. |
| P: O encaminhamento pelo lado do servidor resultará em cobrança adicional no Audience Manager ou no Analytics? | No Analytics, nenhuma cobrança adicional ocorrerá. No Audience Manager, as ocorrências encaminhadas são tratadas como qualquer outra ocorrência e são cobradas.  É por isso que é importante não ter o DIL e encaminhamento pelo lado do servidor habilitados ao mesmo tempo, o que pode causar cobrança duplicada, bem como duplicação de dados. |

>[!MORELIKETHIS]
>
>* [Encaminhamento pelo lado do servidor](/help/admin/admin/c-server-side-forwarding/ssf.md)

