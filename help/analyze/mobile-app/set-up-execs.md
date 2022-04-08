---
description: Os usuários executivos podem precisar de assistência adicional para acessar e usar o aplicativo. Esta seção fornece informações para ajudá-lo a prestar essa assistência.
title: Configurar usuários executivos com o aplicativo
feature: Analytics Dashboards
role: User, Admin
exl-id: 0e858407-2852-4a5f-a0df-3ba290fcca8f
source-git-commit: 1ee50c6a2231795b2ad0015a79e09b7c1c74d850
workflow-type: ht
source-wordcount: '749'
ht-degree: 100%

---

# Configurar usuários executivos com o aplicativo

Em alguns casos, os usuários executivos podem precisar de assistência adicional para acessar e usar o aplicativo. Esta seção fornece informações para ajudá-lo a prestar essa assistência.

## Garantir que os usuários do aplicativo tenham acesso ao Adobe Analytics

1. Configure novos usuários no [Admin Console da Experience Cloud](/help/admin/admin-console/permissions/product-profile.md).

1. Para compartilhar cartões de pontuação, você deve conceder permissões aos usuários do aplicativo para acessar componentes do cartão de pontuação, como o Analysis Workspace, os conjuntos de relatórios nos quais os cartões de pontuação são baseados, bem como segmentos, métricas e dimensões.

## Pré-requisitos do sistema dos usuários do aplicativo

Para garantir que os usuários executivos tenham acesso aos seus cartões de pontuação no aplicativo, verifique se:

* Os requisitos mínimos do sistema operacional móvel dos dispositivos são iOS versão 10 ou superior ou Android versão 4.4 (KitKat) ou superior
* Eles possuem um logon válido no Adobe Analytics.
* Você criou corretamente os cartões de pontuação para dispositivos móveis para eles e compartilhou esses cartões de pontuação com eles.
* Eles têm acesso aos Componentes incluídos no cartão de pontuação. Observe que você pode selecionar uma opção ao compartilhar seus cartões de pontuação para **[!UICONTROL Compartilhar componentes integrados]**.

## Ajudar os executivos a baixar e instalar o aplicativo

**Para usuários executivos no iOS:**

Clique no link a seguir (ele também está disponível no Analytics em **[!UICONTROL Ferramentas]** > **[!UICONTROL Painéis do Analytics (Aplicativo móvel)]**) e siga as instruções para baixar, instalar e abrir o aplicativo:

`[iOS link](https://apple.co/2zXq0aN)`

**Para usuários executivos no Android:**

Clique no link a seguir (ele também está disponível no Analytics em **[!UICONTROL Ferramentas]** > **[!UICONTROL Painéis do Analytics (Aplicativo móvel)]**) e siga as instruções para baixar, instalar e abrir o aplicativo:

`[Android link](https://bit.ly/2LM38Oo)`

Após o download e a instalação, os usuários executivos podem fazer logon no aplicativo usando suas credenciais atuais do Adobe Analytics. Oferecemos suporte para Adobe ID e Enterprise/Federated ID.

![Tela de boas-vindas do aplicativo](assets/welcome.png)

## Ajudar os executivos a acessar seu cartão de pontuação

1. Faça com que os usuários executivos façam logon no aplicativo.

   A tela **[!UICONTROL Escolher uma empresa]** é exibida. Essa tela lista as empresas de logon às quais o usuário executivo pertence.

1. Faça com que eles toquem no nome da empresa de logon ou na Experience Cloud Org que se aplica ao cartão de pontuação que você compartilhou.

   A lista do cartão de pontuação mostra todos os cartões de pontuação que foram compartilhados com o executivo na empresa de logon.

1. Faça com que eles classifiquem essa lista por **[!UICONTROL Modificado mais recentemente]**, se aplicável.

1. Faça com que eles toquem no nome do cartão de pontuação para visualizá-lo.

   ![Escolha uma empresa](assets/accesscard.png)


### Explicar a interface do cartão de pontuação

Explique ao usuário executivo como os blocos são exibidos nos cartões de pontuação que você compartilha.

![Explicar blocos](assets/newexplain.png)

![Exemplo de scorecard](assets/intro_scorecard.png)

Informações adicionais sobre blocos:

* A granularidade dos minigráficos depende da duração do intervalo de datas:
* Um dia mostra uma tendência horária
   * Mais de um dia e menos de um ano mostra uma tendência diária
   * Um ano ou mais mostra uma tendência semanal
   * A fórmula de alteração do valor percentual é o total da métrica (intervalo de datas atual) - total da métrica (intervalo de datas de comparação) / total da métrica (intervalo de datas de comparação).
   * Você pode puxar a tela para baixo para atualizar o Scorecard.


1. Toque em um bloco para mostrar como funciona um detalhamento minucioso do bloco.

   ![Exibição de detalhamento](assets/sparkline.png)

   * Toque em qualquer ponto em um minigráfico para ver os dados associados a esse ponto na linha.

   * Uma tabela é incluída para exibir dados de dimensões adicionadas ao bloco. Toque na seta para baixo para selecionar dimensões. Se nenhuma dimensão tiver sido adicionada ao bloco, a tabela exibirá os dados do gráfico.

1. Para alterar os intervalos de datas do cartão de pontuação, toque no cabeçalho Data e selecione a combinação de intervalo de datas principal e de comparação que você deseja visualizar.

   ![Alterar datas](assets/changedate.png)

## Alterar preferências do aplicativo

Para alterar as preferências, toque na opção **[!UICONTROL Preferências]** mostrada acima. Em preferências, você pode ativar o logon biométrico ou pode definir o aplicativo para o modo escuro, como mostrado abaixo:

![Modo escuro](assets/darkmode.png)

## Solução de problemas

Se o usuário executivo fizer logon e vir uma mensagem dizendo que nada foi compartilhado:

![Nada compartilhado](assets/nothing.png)

* O usuário executivo pode ter selecionado a instância incorreta do Analytics ou
* O cartão de pontuação pode não ter sido compartilhado com o usuário executivo.

Verifique se o usuário executivo pode fazer logon na instância correta do Adobe Analytics e se o cartão de pontuação foi compartilhado.

>[!IMPORTANT]
>
>A partir de outubro de 2020, a Adobe está lançando gradualmente uma série de melhorias para otimizar o desempenho do aplicativo &quot;Painéis do Adobe Analytics&quot;. Essas melhorias se concentram no armazenamento em cache de dados históricos do Analytics que são usados para preencher scorecards com datas (exceto o dia atual). Esses dados serão armazenados em cache por até 24 horas em uma conta de armazenamento na nuvem pública segura do Microsoft Azure. Entre em contato com seu CSM se não quiser aceitar esses recursos de melhoria de desempenho.
