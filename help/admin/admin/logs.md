---
description: Os arquivos de log ajudam a identificar quando os usuários fazem logon, suas atividades, acessos, conjuntos de relatórios e alterações de Admin.
title: Logs
feature: Admin Tools
exl-id: 43f79e2a-2cb9-47eb-982a-54714c9cbafc
role: Admin
source-git-commit: 938795c7378cb1f0537ff84eddeab3feddf8d073
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 67%

---

# Logs

Os arquivos de log ajudam a identificar quando os usuários fazem logon, suas atividades, acessos, conjuntos de relatórios e alterações de Admin.

**[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Todos os administradores]** > **[!UICONTROL Logs]**

## Log de administração {#section_8ADE8A7204A8401C968ABC20AECA381D}

O log de administração relata todas as alterações feitas pelos administradores nas ferramentas administrativas. O log fornece um portal para relatórios definidos pelo usuário a partir de qualquer um dos três logs. Você pode pesquisar eventos que correspondam aos critérios selecionados em um intervalo de datas especificado.

## Log de uso e acesso {#section_6FBAF92D9EA244809C45A78A2F0A7232}

O [!UICONTROL Log de uso e acesso] permite avaliar o uso do relatório no nível da conta de usuário. Por exemplo, monitora ações de abrir, criar, atualizar, cancelar compartilhamento e excluir na Analysis Workspace. Isso permite melhor visibilidade de quem está usando a Workspace e com que frequência.

| Elemento | Descrição |
|---|---|
| Intervalo de datas | Especifique um filtro de intervalo de datas. Você pode inserir uma data manualmente no formato AAAA-MM-DD ou clicar no ícone de Calendário para selecionar uma data. |
| Logon | Filtre o log por nome de usuário. |
| IP | filtrar o log por endereço IP. |
| Conjunto de relatórios | filtre o log segundo uma ID de conjunto de relatórios específica. |
| Tipo de evento | Filtre o log segundo um tipo de evento. Selecione um tipo de evento na lista suspensa. Consulte a lista completa de tipos de evento abaixo. |
| Evento | Filtre o log por uma palavra ou frase na descrição do evento. |
| Baixar relatório | Exporta o conteúdo do [!UICONTROL Log de uso e acesso] para o arquivo com tabulações. |

### Tipos de evento

| Tipo de evento | Descrição |
| --- | --- |
| Nenhuma categoria | Pode ser qualquer tipo de evento. |
| Falha no logon | Falha no processo de logon do usuário. |
| Login bem sucedido | Usuário conectado com sucesso. |
| Ação do administrador | Ocorreu uma ação do administrador, como editar um conjunto de relatórios, alterar as configurações da empresa, criar um usuário, cancelar uma solicitação de relatório etc. |
| Alteração da configuração de segurança | Configuração de segurança alterada. |
| Alerta enviado | Um alerta foi enviado. |
| Ação do usuário | As informações do usuário foram editadas. |
| Ferramenta exibida | Uma ferramenta foi visualizada. |
| Ação do Omniture | Uma ação foi executada por Adobe. |
| Recuperação de senha | Uma senha foi recuperada. |
| Marcadores | Um marcador foi gerenciado. |
| Painéis | Um painel foi gerenciado. |
| Alertas | Um alerta foi gerenciado. |
| Eventos de calendário | Um evento de calendário foi gerenciado. |
| Metas | Um público alvo foi gerenciado. |
| Configurações do relatório | Uma configuração de relatório foi gerenciada. |
| Relatórios agendados | Um relatório agendado foi gerenciado. |
| Exclusão por IP | A configuração de IP foi alterada. |
| Nomear páginas | Obsoleto. |
| Classificações | Uma classificação foi gerenciada. |
| Fontes de dados | Uma fonte de dados foi gerenciada. |
| Projeto do Workspace | Um projeto do Workspace foi visualizado ou editado. |
| Segmento | Um segmento foi criado/editado. |
| Métrica calculada | Uma métrica calculada foi criada/editada. |
| Intervalo de datas | Um intervalo de datas foi criado/editado. |
| Conjunto de relatórios virtuais | Um conjunto de relatórios virtual foi criado/editado. |
| Análise de contribuição | Um trabalho de análise de contribuição foi executado. |
| Método De Api | Foi feita uma chamada à API. |


## Log de alterações do conjunto de relatórios {#section_3864966639414BBEA871F4D0352F56B6}

O log Alterações do conjunto de relatórios exibe as alterações feitas em seus conjuntos de relatório, fora do de administração.

Ferramentas que podem modificar um conjunto de relatórios fora das [!UICONTROL Ferramentas administrativas] incluem:

* Uploads de classificações feitos em um navegador da Web (uploads de Classificações feitos via FTP não estão inclusos no log de alteração)
* Alterações feitas em versões mais antigas.
* Alterações feitas por um representante de conta ou pelo atendimento ao cliente usando ferramentas internas

| Elemento | Descrição |
|---|---|
| Intervalo de datas | Especifique um filtro de intervalo de datas. Você pode inserir uma data manualmente no formato AAAA-MM-DD ou clicar no ícone de Calendário para selecionar uma data. |
| Empresa | Filtre o log por nome de empresa. |
| Logon | Filtre o log por nome de usuário. |
| IP | filtrar o log por endereço IP. |
| Evento | Filtre o log por uma palavra ou frase na descrição do evento. |
| Baixar relatório | Exporta o conteúdo do [!UICONTROL Log de uso e acesso] para o arquivo com tabulações. |
