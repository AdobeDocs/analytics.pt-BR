---
description: Os arquivos de log ajudam a identificar quando os usuários fazem logon, suas atividades, acessos, conjuntos de relatórios e alterações de Admin.
title: Logs
feature: Admin Tools
exl-id: 43f79e2a-2cb9-47eb-982a-54714c9cbafc
role: Admin
TQID: https://experienceleague.adobe.com/TsWKmf74-b1RhjP0CSGZatLrGN39xDylj9tbFZg5R-Y
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: c6a85389-fb1b-4b26-96ea-08f17fed0c9f
  - id: e44bec7e-8653-4d5b-b53e-60b1ae7c3475
  - id: e499b847-6dc4-408a-9f0b-70d35ce9b711
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 595
ht-degree: 27%

---

# Logs

Os arquivos de log ajudam a identificar quando os usuários fazem logon, suas atividades, acessos, conjuntos de relatórios e alterações de administrador.

**[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Todos os administradores]** > **[!UICONTROL Logs]**

## Log de administração {#section_8ADE8A7204A8401C968ABC20AECA381D}

O log de administração relata todas as alterações feitas pelos administradores nas ferramentas administrativas. O log fornece um portal para os relatórios definidos pelo usuário de qualquer um dos três logs. Você pode pesquisar eventos que correspondam aos critérios selecionados em um intervalo de datas especificado.

## Log de uso e acesso {#section_6FBAF92D9EA244809C45A78A2F0A7232}

O [!UICONTROL Log de Uso e Acesso] permite avaliar o uso do relatório no nível da conta de usuário. Por exemplo, rastreia ações de abertura, criação, atualização, cancelamento de compartilhamento e exclusão no Analysis Workspace. Isso permite melhor visibilidade de quem está usando a Workspace e com que frequência.

| Elemento | Descrição |
|---|---|
| Intervalo de datas | Especifique um filtro de intervalo de datas. Você pode inserir uma data manualmente no formato AAAA-MM-DD ou clicar no ícone Calendário para selecionar uma data. |
| Logon | Filtrar o log por nome de usuário. |
| IP | Filtrar o log por um endereço IP. |
| Conjunto de relatórios | Filtrar o log por uma ID de conjunto de relatórios específica. |
| Tipo de evento | Filtrar o log por um tipo de evento. Selecione um tipo de evento na lista suspensa. Consulte a lista completa de tipos de evento abaixo. |
| Evento | Filtre o log por uma palavra ou frase na descrição do evento. |
| Baixar relatório | Exporta o conteúdo do [!UICONTROL Log de Uso e Acesso] para um arquivo delimitado por tabulação. |

### Tipos de evento

| Tipo de evento | Descrição |
| --- | --- |
| Sem categoria | Pode ser qualquer tipo de evento. |
| Falha no logon | Falha no processo de logon do usuário. |
| Logon realizado com sucesso | Usuário conectado com sucesso. |
| Ação Administrativa | Ocorreu uma ação do administrador, como editar um conjunto de relatórios, alterar as configurações da empresa, criar um usuário, cancelar uma solicitação de relatório etc. |
| Alteração da configuração de segurança | Configuração de segurança alterada. |
| Alerta enviado | Um alerta foi enviado. |
| Ação do usuário | As informações do usuário foram editadas. |
| Ferramenta exibida | Uma ferramenta foi visualizada. |
| Ação da Omniture | Uma ação foi executada pelo Adobe. |
| Recuperação de senha | Uma senha foi recuperada. |
| Marcadores | Um marcador foi gerenciado. |
| Painéis | Um painel foi gerenciado. |
| Alertas | Um alerta foi gerenciado. |
| Eventos de calendário | Um evento de calendário foi gerenciado. |
| Metas | Um público alvo foi gerenciado. |
| Configurações de relatório | Uma configuração de relatório foi gerenciada. |
| Relatórios agendados | Um relatório agendado foi gerenciado. |
| Exclusão por IP | A configuração de IP foi alterada. |
| Nomear páginas | Obsoleto. |
| Classificações | Uma classificação foi gerenciada. |
| Fontes de dados | Uma fonte de dados foi gerenciada. |
| Projeto do espaço de trabalho | Um projeto do Workspace foi visualizado ou editado. |
| Segmento | Um segmento foi criado/editado. |
| Métrica calculada | Uma métrica calculada foi criada/editada. |
| Intervalo de datas | Um intervalo de datas foi criado/editado. |
| Conjunto de relatórios virtuais | Um conjunto de relatórios virtual foi criado/editado. |
| Análise de contribuição | Um trabalho de análise de contribuição foi executado. |
| Método de API | Foi feita uma chamada à API. |


## Log de alterações do conjunto de relatórios {#section_3864966639414BBEA871F4D0352F56B6}

O registro de Alterações do conjunto de relatórios exibe as alterações feitas em seus conjuntos de relatórios fora do Administrador.

As ferramentas que podem modificar um conjunto de relatórios de fora das [!UICONTROL Ferramentas administrativas] incluem:

* Uploads de classificações feitos em um navegador da Web (uploads de classificações feitos via FTP não são incluídos no log de alterações)
* Alterações feitas em versões anteriores.
* Alterações feitas por um representante de conta ou pelo Atendimento ao cliente usando ferramentas internas

| Elemento | Descrição |
|---|---|
| Intervalo de datas | Especifique um filtro de intervalo de datas. Você pode inserir uma data manualmente no formato AAAA-MM-DD ou clicar no ícone Calendário para selecionar uma data. |
| Empresa | Filtre o log pelo nome da empresa. |
| Logon | Filtrar o log por nome de usuário. |
| IP | Filtrar o log por um endereço IP. |
| Evento | Filtre o log por uma palavra ou frase na descrição do evento. |
| Baixar relatório | Exporta o conteúdo do [!UICONTROL Log de Uso e Acesso] para um arquivo delimitado por tabulação. |
