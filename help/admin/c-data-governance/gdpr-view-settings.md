---
description: A caixa de diálogo Governança de dados nas Ferramentas administrativas fornece uma visão geral de quais conjuntos de relatórios foram configurados para a governança de dados, se foram mapeados para uma organização da Experience Cloud e se uma política de retenção de dados está em vigor para este conjunto de relatórios.
title: Exibir/gerenciar as configurações de governança de dados do conjunto de relatórios
feature: Data Governance
exl-id: 87b0be42-1098-4e72-8eb8-0c1bb56791f8
source-git-commit: 196e7672026a284591c0dba2336cb11fc3661c72
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 100%

---

# Exibir/gerenciar as configurações de governança de dados do conjunto de relatórios

A caixa de diálogo Governança de dados nas Ferramentas administrativas fornece uma visão geral de quais conjuntos de relatórios foram configurados para a governança de dados, se foram mapeados para uma organização da Experience Cloud e se uma política de retenção de dados está em vigor para este conjunto de relatórios.

1. Faça logon na Adobe Experience Cloud.
1. Navegue até **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Governança de dados]**.

>[!NOTE]
>
>Se não puder ver esse item de menu, você precisará ser adicionado a um [perfil de produto no Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=pt-BR) com permissões para essa funcionalidade.

1. Ver todos os conjuntos de relatórios que fazem parte da empresa de logon:

   ![](assets/privacy_setup_an.png)

| Configuração | Descrição |
| --- | --- |
| **[!UICONTROL Conjuntos de relatórios]** | A primeira linha lista o nome amigável do conjunto de relatórios. A segunda linha contém o nome interno do conjunto de relatórios. Se você tiver permissão para definir rótulos para um conjunto de relatórios, a primeira linha será um link clicável que encaminhará você à página de rotulagem. |
| **[!UICONTROL Mapeamento da organização]** | <ul><li>Mapeado: esse conjunto de relatórios já foi mapeado para a mesma organização da Experience Cloud que a empresa de logon do Analytics na qual você está conectado. Somente conjuntos de relatórios com essa configuração podem ser rotulados.</li><li>Mapeado a outra organização: outra organização da Experience Cloud já mapeou esse conjunto de relatórios para uma organização.</li></ul> |
| **[!UICONTROL Política de retenção de dados]** | A implementação da Privacidade de dados do Analytics exige que você tenha uma política de retenção de dados em vigor. Esta configuração mostra se:<ul><li>Uma política de retenção de dados está em vigor para este conjunto de relatórios e</li><li>Por quanto tempo os dados ficam retidos pela Adobe antes de serem excluídos. O período de retenção de dados padrão é de 25 meses.</li></ul>**Observação**: o Adobe Analytics não pode ajudá-lo com o processamento de solicitações da API de privacidade de dados (ou seja, com o processamento de solicitações de acesso ou de exclusão recebidas dos usuários finais) se o período de retenção de dados não tiver sido definido. Entre em contato com o gerente de sucesso do cliente para definir o período de retenção de dados. |
| **[!UICONTROL Grupos]** | Atualmente, o recurso de agrupamento não está implementado. |
| Barra à esquerda | Clique no ícone de funil para abrir ou fechar a barra lateral. A seção [!UICONTROL Mapeamento da organização] exibe o número de conjuntos de relatórios que se enquadram em cada uma das categorias descritas. A seção [!UICONTROL Política de retenção de dados] exibe cada política de retenção de dados exclusiva que está em vigor atualmente para a sua organização, bem como o número de conjuntos de relatórios atribuídos a essa política de retenção. |
| **[!UICONTROL Exportar para CSV]** | Se você marcar a caixa de seleção próxima de um ou mais conjuntos de relatórios, a opção Exportar para CSV será exibida. Essa opção permite baixar um arquivo CSV que contenha todas as definições de rótulo atuais de todas as variáveis para todos os conjuntos de relatórios selecionados. Recomendamos que a sua equipe jurídica analise as escolhas de rotulagem e essa opção facilita a análise. Em vez de precisar executar a análise enquanto estiver conectado à interface do usuário na Governança de dados, você pode compartilhar o arquivo CSV com a equipe. |

{style=&quot;table-layout:auto&quot;}
