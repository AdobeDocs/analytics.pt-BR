---
description: Criar um contêiner básico para a coleta de dados no Adobe Analytics
title: Criar um conjunto de relatórios
feature: Report Suite Settings
exl-id: 255ae051-d993-41a5-8cf3-819a54c17e34
TQID: https://experienceleague.adobe.com/ZmPcYHvXOhaXXnqsSVUh1bpvignxomS3d4S76iMCAa4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2:
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: c2ae876122715b4fa6367326dc23479dd9648021
workflow-type: tm+mt
source-wordcount: 312
ht-degree: 87%

---

# Criar um novo conjunto de relatórios

Um conjunto de relatórios é um silo de dados que o Adobe Analytics usa para extrair relatórios. Uma organização pode ter vários conjuntos de relatórios, cada um contendo diferentes conjuntos de dados. Embora os conjuntos de relatórios separados tenham sido importantes no passado, ter um único conjunto de relatórios se tornou mais vantajoso. A introdução aos [conjuntos de relatórios virtuais](/help/components/vrs/vrs-about.md#virtual-report-suites) e ao processamento de tempo do relatório permite que administradores criem seus próprios subconjuntos de dados, fornecendo flexibilidade para obter dados globais e específicos do site.

Este artigo foi projetado para administradores de nível de sistema ou administradores do Adobe Analytics para preparar a coleta de dados.

## Pré-requisitos

[Guia do primeiro administrador do Adobe Analytics](/help/admin/admin-console/first-admin-guide.md): verifique se um administrador de nível de sistema concedeu acesso ao Adobe Analytics por meio do CX Enterprise Admin Console.

## Criar um conjunto de relatórios {#create-report-suite}

1. Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]**.
1. Clique em **[!UICONTROL Adicionar conjunto de relatórios]**.
1. Selecione um modelo predefinido ou um conjunto de relatórios existente para usar como um [modelo](/help/admin/tools/manage-rs/rs-templates/report-suite-templates.md).

   >[!NOTE]
   >
   >Somente as configurações podem ser copiadas, não os dados. Se o Atendimento ao cliente estiver copiando as configurações, você precisará fornecer uma confirmação por escrito de que aceitou o aviso legal recebido sobre os riscos envolvidos. Consulte [Configurações não copiadas de um conjunto de relatórios de origem](/help/admin/tools/manage-rs/new-rs/settings-not-copied-from-rs.md) para obter mais informações.

1. Preencha os campos descritos em [Novo conjunto de relatórios](/help/admin/tools/manage-rs/new-rs/new-report-suite.md).
1. Clique em **[!UICONTROL Criar conjunto de relatórios]**.

Uma ID de conjunto de relatórios tem um comprimento máximo de 40 bytes. Um nome amigável do conjunto de relatórios tem um comprimento máximo de 255 bytes.

## Solução de problemas

**Depois de fazer logon no CX Enterprise, o ícone do Analytics fica esmaecido.**

Isso significa que sua conta não recebeu as permissões corretas para o Analytics. Trabalhe com um administrador de nível de sistema da organização para garantir que você pertença a um perfil com permissões adequadas para acessar o Adobe Analytics.

## Próximas etapas

[Criar uma propriedade de tag do Adobe Analytics](/help/implement/launch/create-analytics-property.md): criar uma área para gerenciar a implementação do Analytics.
