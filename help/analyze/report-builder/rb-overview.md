---
title: Visão geral do Report Builder
description: Descreve a funcionalidade do Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: b6f2b1f5-8790-4342-85c8-524fdf346073
source-git-commit: 9a2d4c582b6a3946b658924851e5b5ada2f5a7ee
workflow-type: ht
source-wordcount: '527'
ht-degree: 100%

---

# Visão geral do Report Builder

O novo complemento de Javascript do Report Builder que estava disponível inicialmente apenas no Customer Journey Analytics agora também está sendo introduzido no Adobe Analytics. Esta nova versão oferece vários benefícios:

- Encontre insights no Excel de forma mais rápida e fácil, com fluxos de trabalho aprimorados para criação e gerenciamento de blocos de dados, incluindo maior flexibilidade dos blocos de dados
- Multiplataformas: não é mais necessário fazer logon na sua VM para usar o Report Builder, pois ele agora é compatível com PC, Mac e Excel Online
- Menos tempo aguardando o retorno dos blocos de dados, graças à atualização da API 2.0
- Aumentar a velocidade.

Os usuários da ferramenta Report Builder herdada podem [converter pastas de trabalho herdadas](/help/analyze/report-builder/convert-workbooks.md) para o novo Report Builder.

O Report Builder permite criar, editar e atualizar relatórios personalizados com facilidade, usando dados do Adobe Analytics. Com a interface de arrastar e soltar simples e flexível do Report Builder, você pode criar consultas de dados complexas e relatórios personalizados de dados do Adobe Analytics, tudo dentro do Excel.

Com o Report Builder, você pode:

- Referenciar células de planilhas existentes para obter a ordem perfeita de linhas, intervalo de datas ou filtro
- Criar datas personalizadas usando calendário, referências de células ou matemática de data
- Criar tabelas e visualizações com as ferramentas de formatação conhecidas do Excel

## Usando o Report Builder herdado e o novo lado a lado

Você ainda pode usar ambas as versões do Report Builder, com as seguintes ressalvas:

- Não use ambas as versões do Report Builder no mesmo arquivo ao mesmo tempo. Elas são mutuamente exclusivas.
- Você ainda pode usar o Report Builder herdado nas pastas de trabalho herdadas e o novo Report Builder nas novas pastas de trabalho.
- Além disso, você pode [converter automaticamente pastas de trabalho herdadas](/help/analyze/report-builder/convert-workbooks.md) para o formato do novo Report Builder. Antes de fazer isso, duplique e renomeie o arquivo.

## Recursos herdados do Report Builder não são compatíveis com o novo Report Builder

Ao comparar a funcionalidade do Report Builder herdado com o novo complemento do Report Builder, algumas funcionalidades herdadas não estão mais disponíveis:

- Solicitações em tempo real

- Relatório de caminho/fallout

- Opção de FTP para relatórios programados

- Métricas de visitantes. As métricas a seguir serão convertidas em “visitantes únicos”, mesmo que o resultado do relatório não seja uma correspondência exata: `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly`, `visitorsquarterly` e `visitorsyearly`. Isso também se aplica a `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly` e `mobilevisitorsyearly`.

## Casos de uso comuns

- **Extração de dados**: o Adobe Report Builder permite extrair dados do Adobe Analytics para o Excel. É possível criar relatórios e consultas personalizadas para recuperar pontos de dados específicos relevantes para a análise.

- **Relatórios personalizados**: você pode formatar relatórios personalizados e mudar seu design no Excel para atender às suas necessidades específicas de relatórios. Isso é especialmente útil para adaptar relatórios a diferentes partes interessadas.

- **Análise ad hoc**: os usuários podem gerar relatórios ad hoc rapidamente para responder a perguntas específicas ou explorar tendências de dados sem precisar passar por um longo processo de criação de relatórios.

- **Painéis**: os dados extraídos do CJA podem ser usados para criar painéis e visualizações com base no Excel para uma visão geral de alto nível dos indicadores principais de desempenho (KPIs).

- **Compartilhamento de insights**: você pode compartilhar relatórios e insights do Excel com membros da equipe ou partes interessadas que podem não ter acesso direto ao CJA.

## Vídeo de visão geral

>[!IMPORTANT]
>
>Este vídeo de visão geral mostra a interface do usuário do Report Builder no Customer Journey Analytics. Algumas interfaces do usuário e terminologias variam. Fora isso, a experiência do usuário é idêntica.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Visão geral do Report Builder](https://video.tv.adobe.com/v/337569?quality=12&learn=on){target="_blank"} para assistir a um vídeo de demonstração.

>[!ENDSHADEBOX]

Você pode baixar o Report Builder da [Microsoft Store](https://appsource.microsoft.com/pt-br/product/office/WA200003101?tab=Overview).
