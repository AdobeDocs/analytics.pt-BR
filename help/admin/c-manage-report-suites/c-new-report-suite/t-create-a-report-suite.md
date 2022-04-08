---
description: Criar um contêiner básico para a coleta de dados no Adobe Analytics
title: Criar um conjunto de relatórios
feature: Report Suite Settings
exl-id: 255ae051-d993-41a5-8cf3-819a54c17e34
source-git-commit: f4b495b11bcbd55bc8448f2c9c09268547fb9750
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Criar um novo conjunto de relatórios

Um conjunto de relatórios é um silo de dados que o Adobe Analytics usa para extrair relatórios. Uma organização pode ter vários conjuntos de relatórios, cada um contendo diferentes conjuntos de dados. Embora os conjuntos de relatórios separados tenham sido importantes no passado, ter um único conjunto de relatórios se tornou mais vantajoso. A introdução aos [conjuntos de relatórios virtuais](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=pt-BR#virtual-report-suites) e ao processamento de tempo do relatório permite que administradores criem seus próprios subconjuntos de dados, fornecendo flexibilidade para obter dados globais e específicos do site.

Este artigo foi projetado para administradores de nível de sistema ou administradores do Adobe Analytics para preparar a coleta de dados.

## Pré-requisitos

[Guia do primeiro administrador do Adobe Analytics](/help/admin/admin-console/first-admin-guide.md): verifique se um administrador de nível de sistema concedeu acesso ao Adobe Analytics por meio do Admin Console da Experience Cloud.

## Criar um conjunto de relatórios {#create-report-suite}

1. Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]**.
1. Clique em **[!UICONTROL Criar novo]** > **[!UICONTROL Conjunto de relatórios]**.
1. Selecione um modelo predefinido ou um conjunto de relatórios existente para usar como um [modelo](../c-report-suite-templates/report-suite-templates.md).

   >[!NOTE]
   >
   >Somente as configurações podem ser copiadas, não os dados. Se o Atendimento ao cliente estiver copiando as configurações, você precisará fornecer uma confirmação por escrito ao aviso legal fornecido pelo Atendimento ao cliente sobre os riscos envolvidos. Consulte [Configurações não copiadas de um conjunto de relatórios de origem ](/help/admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md)para obter mais informações.

1. Preencha os campos descritos em [Novo conjunto de relatórios.](../c-new-report-suite/new-report-suite.md)
1. Clique em **[!UICONTROL Criar conjunto de relatórios]**.

Uma ID de conjunto de relatórios tem um comprimento máximo de 40 bytes. Um nome amigável do conjunto de relatórios tem um comprimento máximo de 255 bytes.

## Solução de problemas

**Depois de fazer logon na Experience Cloud, o ícone do Analytics fica esmaecido.**

Isso significa que sua conta não recebeu as permissões corretas para o Analytics. Trabalhe com um administrador de nível de sistema da organização para garantir que você pertença a um perfil com permissões adequadas para acessar o Adobe Analytics.

## Próximas etapas

[Criar uma propriedade de tag do Adobe Analytics](/help/implement/launch/create-analytics-property.md): criar uma área para gerenciar a implementação do Analytics.
