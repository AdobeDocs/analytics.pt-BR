---
title: Quais são as novidades do Adobe Report Builder?
description: Descreve a nova funcionalidade do Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Analytics
source-git-commit: 7e8a25381f2eadafc5dc22a0991060ea475b5d43
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 27%

---

# Sobre a nova Adobe Report Builder

O novo Suplemento de Report Builder do Javascript, que estava disponível inicialmente apenas no Customer Journey Analytics, agora também está sendo introduzido no Adobe Analytics. Esta nova versão oferece vários benefícios:

- Encontre insights no Excel de forma mais rápida e fácil com fluxos de trabalho aprimorados para criação e gerenciamento de blocos de dados, incluindo maior flexibilidade de blocos de dados
- Entre plataformas: não é mais necessário fazer logon na VM para usar o Report Builder, pois agora oferecemos suporte a PC, Mac e Excel Online
- Menos tempo aguardando o retorno dos blocos de dados, graças à atualização da API 2.0
- Aumentar a velocidade.

>[!NOTE]
>
>O agendamento da pasta de trabalho para esta versão do Report Builder no Adobe Analytics ainda não foi lançado, mas estará disponível no início de 2025. Agora você pode começar a usar pastas de trabalho que não exigem agendamento.

Os usuários da ferramenta Report Builder herdado podem [converter pastas de trabalho herdadas](/help/analyze/report-builder/convert-workbooks.md) para o novo Report Builder.

O Report Builder permite criar, editar e atualizar facilmente relatórios personalizados usando dados do Adobe Analytics. Com a interface de usuário de arrastar e soltar simples e flexível do Report Builder, é possível criar consultas de dados complexas e relatórios personalizados com base em dados do Adobe Analytics, tudo dentro do Excel.

Com o Report Builder, você pode:

- Referenciar células de planilhas existentes para obter a ordem perfeita de linhas, intervalo de datas ou filtro
- Criar datas personalizadas usando calendário, referências de células ou matemática de data
- Criar tabelas e visualizações com as ferramentas de formatação conhecidas do Excel

## Uso do Report Builder antigo e do novo Report Builder lado a lado

Você ainda pode usar ambas as versões do Report Builder, com os seguintes avisos:

- Não use ambas as versões de Report Builder no mesmo arquivo ao mesmo tempo. Elas são mutuamente exclusivas.
- Você ainda pode usar o Report Builder herdado nas pastas de trabalho herdadas e o novo Report Builder nas novas pastas de trabalho.
- Além disso, você pode [converter automaticamente pastas de trabalho herdadas](/help/analyze/report-builder/convert-workbooks.md) para o novo formato Report Builder. Antes de fazer isso, duplique e renomeie o arquivo.

## Recursos de Report Builder herdados não são suportados no Novo Report Builder

Ao comparar a funcionalidade do Report Builder herdado com o novo Suplemento de Report Builder, alguma funcionalidade herdada não está mais disponível:

- Solicitações em tempo real

- Relatório de caminho/fallout

- Opção de FTP para relatórios agendados

- Métricas de visitantes. As métricas a seguir serão convertidas em &quot;visitantes únicos&quot;, mesmo que o resultado do relatório não seja uma correspondência exata: `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly`, `visitorsquarterly` e `visitorsyearly`. Isso também se aplica a `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly` e `mobilevisitorsyearly`.

## Casos de uso comuns

- **Extração de dados**: o Adobe Report Builder permite extrair dados do Adobe Analytics para o Excel. É possível criar relatórios e consultas personalizadas para recuperar pontos de dados específicos relevantes para a análise.

- **Relatórios personalizados**: você pode formatar relatórios personalizados e mudar seu design no Excel para atender às suas necessidades específicas de relatórios. Isso é especialmente útil para adaptar relatórios a diferentes partes interessadas.

- **Análise ad hoc**: os usuários podem gerar relatórios ad hoc rapidamente para responder a perguntas específicas ou explorar tendências de dados sem precisar passar por um longo processo de criação de relatórios.

- **Painéis**: os dados extraídos do CJA podem ser usados para criar painéis e visualizações com base no Excel para uma visão geral de alto nível dos indicadores principais de desempenho (KPIs).

- **Compartilhamento de insights**: você pode compartilhar relatórios e insights do Excel com membros da equipe ou partes interessadas que podem não ter acesso direto ao CJA.

## Vídeo de visão geral

>[!IMPORTANT]
>
>Este vídeo de visão geral mostra a interface de usuário do Report Builder no Customer Journey Analytics. Algumas interfaces de usuário e terminologias diferem. Caso contrário, a experiência do usuário será idêntica.

>[!VIDEO](https://video.tv.adobe.com/v/337569/?quality=12&learn=on)

Você pode baixar o Report Builder da [Microsoft Store](https://appsource.microsoft.com/en-us/product/office/WA200003101?tab=Overview).
