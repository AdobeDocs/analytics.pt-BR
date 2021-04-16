---
description: Saiba mais sobre as diferentes opções de gravação, incluindo salvar automaticamente, salvar como, salvar como modelo e abrir versões anteriores.
title: Salvar projetos
feature: Fundamentos do Workspace
role: Business Practitioner, Administrator
exl-id: e8206956-6e24-4a3a-8c3f-8acf1fb9d800
translation-type: tm+mt
source-git-commit: cfeb681805108c9d9422d88b6d7146d0eb186204
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 54%

---

# Salvar projetos

Para salvar as alterações em um projeto, acesse o menu **[!UICONTROL Projeto]** do Workspace. O Workspace também salva automaticamente projetos em determinados casos.

## Salvar opções do projeto {#Save}

Há diferentes ações de salvamento que podem ser feitas no menu **[!UICONTROL Projeto]**, dependendo de como você deseja acessar sua análise no futuro.

| Ação | Descrição |
|---|---| 
| **[!UICONTROL Salvar]** | Salve as alterações no seu projeto. Se o projeto for compartilhado, os recipients do projeto também verão as alterações. Ao salvar seu projeto pela primeira vez, você será solicitado a fornecer um nome, uma descrição (opcional) e adicionar tags (opcional) ao projeto. |
| **[!UICONTROL Salvar com notas]** | Antes de salvar o projeto, adicione observações sobre o que foi alterado no projeto. As notas são armazenadas com a versão do projeto e estão disponíveis para todos os editores em [!UICONTROL Project] > [!UICONTROL Abrir versão anterior]. |
| **[!UICONTROL Salvar como]** | Crie um duplicado do seu projeto. O projeto original não será afetado. |
| **[!UICONTROL Salvar como modelo]** | Salve seu projeto como um [modelo personalizado](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html) que fica disponível para sua organização em **[!UICONTROL Projeto > Novo]** |

![](assets/save-project.png)

## Salvar automaticamente {#Autosave}

Os projetos existentes, isto é, os que foram salvos pelo menos uma vez antes, são salvos automaticamente a cada dois minutos no computador local. Os novos projetos que nunca foram salvos não são salvos automaticamente no momento.

Há alguns cenários que podem levá-lo a não salvar as alterações em um projeto, resultando em diferentes ações disponíveis.

### Abrir outro projeto do Workspace

A Adobe fornece a opção de salvar antes de sair da página. Após sair de um projeto existente, a cópia local salva automaticamente é excluída.

![](assets/existing-save.png)

### Sair ou fechar uma guia

O navegador avisa que as alterações não salvas serão perdidas. Você pode optar por sair ou cancelar.

![](assets/browser-image.png)

### Falha do navegador ou tempo limite da sessão

Para projetos **existentes**, ao retornar ao Workspace, você verá um modal **Recuperação do projeto**. Selecionar &quot;Sim&quot; restaura o projeto da cópia local salva automaticamente. “Não” exclui a cópia local salva automaticamente e abre a última versão salva pelo usuário do projeto.

![](assets/project-recovery.png)

Para **novos** projetos que nunca foram salvos, as alterações não salvas não são recuperáveis.

## Abrir versão anterior {#previous-version}

>[!NOTE]
>
>As versões anteriores do projeto estão atualmente na versão limitada.

Para abrir uma versão anterior de um projeto:

1. Vá para **[!UICONTROL Projeto]** > **[!UICONTROL Abrir versão anterior]**

   ![](assets/previous-versions.png)

1. Revise a lista de versões anteriores disponíveis.
    Os carimbos de data e hora e   o editor são exibidos, além de   Notas, se foram adicionados quando o   Editor foi salvo. As versões sem notas são armazenadas por 90 dias; versões com notas são armazenadas por 1 ano.
1. Selecione uma versão anterior e clique em **[!UICONTROL Carregar]**.
A versão anterior é carregada com uma notificação. A versão anterior não se torna a versão salva atual do projeto até que você clique em **[!UICONTROL Salvar]**. Ao sair da versão carregada, ao retornar, você verá a última versão salva do projeto.
