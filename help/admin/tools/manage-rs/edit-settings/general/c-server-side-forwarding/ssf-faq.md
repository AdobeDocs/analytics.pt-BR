---
description: Perguntas frequentes sobre recursos, funcionalidades e problemas relacionados ao encaminhamento pelo lado do servidor.
title: Perguntas frequentes sobre o encaminhamento pelo lado do servidor
feature: Report Suite Settings
exl-id: 63103d2b-e2e8-42da-bdbd-be90abe305f7
role: Admin
TQID: https://experienceleague.adobe.com/3i6RY7JRPlJc-9NjsQXBPn5SEOn0m4JrtL85Kl84ilM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 707
ht-degree: 42%

---

# Perguntas frequentes sobre o encaminhamento pelo lado do servidor

Perguntas frequentes sobre recursos, funcionalidades e problemas relacionados ao encaminhamento pelo lado do servidor.

## Servidores de rastreamento {#section_28E5BECC2034484AB9726E513F2CCFB7}

| Pergunta | Resposta |
|--- |--- |
| P: E se eu estiver usando atualmente o encaminhamento pelo lado do servidor herdado baseado no servidor de rastreamento? | O método de encaminhamento pelo lado do servidor baseado no servidor de rastreamento herdado continuará a encaminhar dados do Analytics para o Audience Manager. No entanto, se você quiser enviar segmentos do Audience Manager para o Analytics, o novo encaminhamento pelo lado do servidor baseado no conjunto de relatórios será necessário. Além disso, não há nenhum dano em ativar um conjunto de relatórios para encaminhamento pelo lado do servidor além da configuração do servidor de rastreamento. A nova configuração de encaminhamento pelo lado do servidor do conjunto de relatórios será usada sempre que houver um conflito. |
| P: Devo migrar o encaminhamento pelo lado do servidor baseado no servidor de rastreamento herdado para o novo encaminhamento pelo lado do servidor baseado no conjunto de relatórios? | Continuaremos a oferecer suporte ao encaminhamento pelo lado do servidor baseado no servidor de rastreamento no futuro próximo. No entanto, se você quiser aproveitar a integração do Audience Manager com o Analytics (compartilhamento de segmentos para o Analytics), será necessário habilitar o novo encaminhamento pelo lado do servidor baseado no conjunto de relatórios para todos os conjuntos de relatórios aplicáveis. No entanto, não há motivo urgente para desabilitar o encaminhamento pelo lado do servidor baseado no servidor de rastreamento herdado. |

## Aplicação de tags e criação de relatórios {#section_71391BA901AC47B9A2286281644FF281}

| Pergunta | Resposta |
|--- |--- |
| P: E se eu tiver uma tag de vários conjuntos no meu site? O encaminhamento pelo lado do servidor duplicará minhas chamadas de servidor para o Audience Manager? | Não, uma ocorrência que é encaminhada do Analytics para o Audience Manager somente será encaminhada uma vez para o Audience Manager, independentemente do número de conjuntos de relatórios na ocorrência. Se você tiver fontes de dados correspondentes no Audience Manager para cada um dos conjuntos de relatórios na ocorrência, cada um será preenchido apropriadamente a partir dessa única ocorrência.  Tenha em mente, no entanto, que, se você usa atualmente a coleta de dados no lado do cliente (DIL) e habilitar o encaminhamento pelo lado do servidor sem instalar o módulo de Gerenciamento de público-alvo, você duplicará suas chamadas de servidor para o Audience Manager, independentemente do número de conjuntos de relatórios que você possui na sua ocorrência do Analytics. |
| P: E se eu tiver conjuntos de relatórios com tags de vários conjuntos que estejam mapeados a organizações CX Enterprise separadas? | Você nunca deve enviar dados de uma única ocorrência do Analytics para dois conjuntos de relatórios pertencentes a organizações corporativas CX separadas, mas se isso ocorrer, apenas encaminharemos a ocorrência para a organização corporativa CX correspondente à configuração do serviço de identidade na página. |
| P: E se eu tiver uma tag de vários conjuntos e apenas um dos meus conjuntos de relatórios for mapeado para a minha CX Enterprise Org e o outro não? | Encaminharemos a ocorrência para o servidor de coleta de dados correspondente à organização corporativa CX no conjunto de relatórios mapeado. No entanto, como o conjunto de relatórios não mapeado não terá uma fonte de dados associada no Audience Manager, nenhum dado será gravado para o conjunto de relatórios não mapeado no Audience Manager. |
| P: E se eu tiver um conjunto de relatórios mapeado para várias organizações CX Enterprise? | O Analytics considerará esse conjunto de relatórios como não mapeado e não permitirá que o encaminhamento pelo lado do servidor seja ativado para esse conjunto de relatórios. Entre em contato com o atendimento ao cliente para resolver esse problema de mapeamento. |
| P: O método de encaminhamento pelo lado do servidor baseado no conjunto de relatórios será mais lento do que o encaminhamento pelo lado do servidor baseado no servidor de rastreamento? | Não, o tempo de resposta será o mesmo. |
| P: E se nós tivermos duas organizações CX Enterprise (ou instâncias Adobe Audience Manager) e quisermos compartilhar dados entre as duas organizações CX Enterprise? Posso encaminhar no lado do servidor uma única ocorrência do Analytics para várias organizações corporativas CX? | Não. Se você precisar compartilhar os dados coletados de uma organização corporativa CX com outra organização corporativa CX, recomendamos enviar qualquer público aplicável de uma instância do Audience Manager para outra usando o Audience Marketplace. |
| P: O encaminhamento pelo lado do servidor resultará em cobrança adicional no Audience Manager ou no Analytics? | No Analytics, nenhuma cobrança adicional ocorrerá. No Audience Manager, as ocorrências encaminhadas são tratadas como qualquer outra ocorrência e são cobradas.  É por isso que é importante não ter o DIL e encaminhamento pelo lado do servidor habilitados ao mesmo tempo, o que pode causar cobrança duplicada, bem como duplicação de dados. |

>[!MORELIKETHIS]
>
>* [Encaminhamento pelo lado do servidor](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)
