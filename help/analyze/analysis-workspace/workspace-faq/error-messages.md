---
description: Saiba mais sobre erros e solução de problemas no Analysis Workspace.
title: Erros e solução de problemas
feature: Workspace Basics
role: User, Admin
exl-id: e5c6f710-a205-48db-aeee-ee5b83c42795
TQID: 'https://experienceleague.adobe.com/Kr34CyT7YxRqKRdwpaLN-DZwHhLbaT663Gj-pc5Wd8s'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
    internal-label: Alerts
  - id: c457b289-f974-4a67-a5b6-dec3ffa77675
    internal-label: Workspace basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
source-git-commit: 319f78bb5f8c2449a7263e3f1c378c49656889a7
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 94%
---
# Erros e solução de problemas

Ao interagir com o Analysis Workspace, você pode encontrar alguns erros que influenciam a funcionalidade ou o desempenho. A lista abaixo mostra os tipos de erro mais comuns, por que ocorrem e as otimizações que podem ser feitas.

## Mensagens de erro

Estas são algumas mensagens de erro comuns que você poderá ver ao usar o Analysis Workspace:

| Mensagem de erro | Por que o erro ocorre? | Otimização |
| --- | --- | --- |
| [!UICONTROL O conjunto de relatórios está apresentando um volume excessivo de relatórios. Tente novamente mais tarde.] | Sua organização está tentando executar muitas solicitações simultâneas em relação a um conjunto de relatórios específico. Os fatores que contribuem para esse erro são solicitações de API, projetos agendados, relatórios agendados, alertas agendados e usuários simultâneos que fazem solicitações de relatórios. | Espalhe suas solicitações e agendamentos no conjunto de relatórios de forma mais uniforme ao longo do dia.<p>Admins podem usar o [Gerenciador de atividades de relatórios para identificar e cancelar solicitações](/help/admin/tools/reporting-activity-manager/reporting-activity-overview.md) que estão consumindo a capacidade de gerar relatórios.</p> |
| [!UICONTROL Este relatório é complexo demais. Confira as práticas recomendadas para criar relatórios do Analysis Workspace.] | Sua solicitação de relatório é muito grande e não pode ser executada. Os fatores que contribuem para esse erro são o tempo-limite devido à complexidade da solicitação. | Simplifique sua solicitação. Por exemplo, reduza o intervalo de datas, simplifique os critérios de segmento ou remova algumas colunas ou linhas da tabela. Considere também dividir a tabela em solicitações separadas. |
| [!UICONTROL O conjunto de relatórios está excedendo sua capacidade de gerar relatórios no momento. Simplifique a solicitação ou tente novamente mais tarde.] | Sua organização está tentando executar muitas solicitações simultâneas em relação a um conjunto de relatórios específico. Os fatores que contribuem para esse erro são solicitações de API, projetos agendados e usuários simultâneos que criam solicitações de relatórios. | Espalhe suas solicitações e agendamentos no conjunto de relatórios de forma mais uniforme ao longo do dia. |
| [!UICONTROL Ocorreu um erro de sistema. Registre uma solicitação junto ao Atendimento ao cliente em **[!UICONTROL Ajuda > Enviar tíquete de suporte]** e inclua o código de erro.] | A Adobe está enfrentando um problema que precisa ser resolvido. | Envie o código de erro ao Atendimento ao cliente. |
| [!UICONTROL Erro 500: Falha ao carregar a página] | Problemas com a rede local, como [configurações de firewall](/help/technotes/ip-addresses.md) da empresa, contribuem para esse erro. Além disso, a Adobe pode estar enfrentando um problema que precisa ser resolvido. | Tente fazer logon novamente após alguns minutos. Se o problema persistir, envie o código de ID da instância do EIM para o Atendimento ao cliente. |
| [!UICONTROL Sua solicitação falhou como resultado de muitas colunas ou linhas pré-configuradas.] | Sua tabela tem muitas células de forma livre (linha * colunas). | Remova colunas ou linhas na tabela ou considere dividir a tabela em solicitações separadas. |


## Solução de problemas

Ao usar o Analysis Workspace, você pode usar as informações abaixo para solucionar alguns problemas comuns.

| Problema | Como solucionar problemas |
|---|---|
| Quando arrasto uma métrica, vejo a mensagem *Dados inválidos*. | Dados inválidos significa que a Adobe não pode retornar dados usando a combinação de dimensões e métricas usadas no relatório. Por exemplo, duas métricas empilhadas uma sobre a outra não podem retornar como dados, pois não há como exibir duas métricas desse modo. Em vez disso, coloque as métricas lado a lado. |
| Quando arrasto uma métrica, não vejo nenhum dado real, apenas zeros. | Se você criar um relatório do espaço de trabalho com êxito, mas não houver dados, tente realizar as seguintes verificações:<ul><li>Se você aplicar um segmento no seu relatório, os critérios do segmento podem não corresponder a nenhum dado. Tente remover o segmento ou ajustar a definição do segmento.</li><li>Verifique o intervalo de datas no canto superior direito e verifique se ele está definido conforme o esperado.</li><li>Navegue até o site e use a [Adobe Experience Platform Debugger](https://experienceleague.adobe.com/pt-br/docs/experience-platform/debugger/home) para verificar se os dados estão sendo coletados.</li></ul> |
