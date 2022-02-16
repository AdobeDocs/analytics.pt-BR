---
description: Criar um contêiner básico para a coleta de dados no Adobe Analytics
title: Criar um novo conjunto de relatórios
feature: Report Suite Settings
exl-id: 255ae051-d993-41a5-8cf3-819a54c17e34
source-git-commit: 72bd67179e003b70233d863d34153fec77548256
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 66%

---

# Criar um novo conjunto de relatórios

Um conjunto de relatórios é um silo de dados que o Adobe Analytics usa para extrair relatórios. Uma organização pode ter vários conjuntos de relatórios, cada um contendo diferentes conjuntos de dados. Embora os conjuntos de relatórios separados tenham sido importantes no passado, ter um único conjunto de relatórios se tornou mais vantajoso. A introdução do [conjuntos de relatórios virtuais](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=en#virtual-report-suites) O e o processamento de tempo do relatório permitem que os administradores criem seus próprios subconjuntos de dados, permitindo a flexibilidade para obter dados globais e específicos do site.

Este artigo foi projetado para administradores de nível de sistema ou administradores do Adobe Analytics para preparar a coleta de dados.

## Pré-requisitos

[Adobe Analytics First Admin Guide](/help/admin/admin-console/first-admin-guide.md): Ensure that a system-level administrator has granted you access to Adobe Analytics via the Experience Cloud Admin Console.

## Criar um novo conjunto de relatórios {#create-report-suite}

1. Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]**.
1. Clique em **[!UICONTROL Criar novo]** > **[!UICONTROL Conjunto de relatórios]**.
1. Para copiar as configurações de um conjunto de relatórios, na lista de modelos, selecione um modelo predefinido ou um conjunto de relatórios existente para usar como um [modelo.](/help/admin/c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)

   >[!NOTE]
   >
   >Somente as configurações podem ser copiadas, não os dados. Se o Atendimento ao cliente estiver copiando as configurações, você precisará fornecer uma confirmação por escrito ao aviso legal fornecido pelo Atendimento ao cliente sobre os riscos envolvidos. Consulte [Configurações não copiadas de um conjunto de relatórios de origem ](/help/admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md)para obter mais informações.

1. Preencha os campos descritos em [Novo conjunto de relatórios.](/help/admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md)
1. Clique em **[!UICONTROL Criar conjunto de relatórios]**.

A report suite ID has a maximum length of 40 bytes. A report suite friendly name has a maximum length of 255 bytes.

## Solução de problemas

**Depois de fazer logon na Experience Cloud, o ícone do Analytics fica esmaecido.**

Isso significa que sua conta não recebeu as permissões corretas para o Analytics. Trabalhe com um administrador de nível de sistema da organização para garantir que você pertença a um perfil com permissões adequadas para acessar o Adobe Analytics.

**Depois de fazer logon no Adobe Analytics, a pop-up e a lista suspensa &quot;Bem-vindo ao Adobe Analytics&quot; estão ausentes.**

Verifique se você fez logon por meio do [Experience Cloud](https://experience.adobe.com), e não por my.omniture.com. O usuário que faz logon por my.omniture.com não tem o assistente de configuração de conjunto de relatórios disponível.

## Próximas etapas

[Create an Adobe Analytics tag property ](/help/implement/launch/create-analytics-property.md): Create an area to manage your Analytics implementation
