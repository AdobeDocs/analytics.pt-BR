---
description: A habilitação do gerenciamento de aplicativos ativa as variáveis de solução móvel que capturam o ciclo de vida e outras métricas de aplicativos móveis.
title: Gerenciamento de aplicativos
feature: Admin Tools
exl-id: ec19695a-2961-45e4-bf44-434f0ff9e3c9
source-git-commit: a17297af84e1f5e7fe61f886eb3906c462229087
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 100%

---

# Gerenciamento de aplicativos

A habilitação do gerenciamento de aplicativos ativa as variáveis de solução móvel que capturam o ciclo de vida e outras métricas de aplicativos móveis.

Esta integração entre o Adobe Analytics e Mobile Services:

* Permite compartilhar seus dados de KPI (Indicador-chave de desempenho) dos Mobile Services para o Adobe Analytics.
* Permite ativar o rastreamento de localização.
* Adiciona novos relatórios em Analytics > Relatórios > Aplicativo móvel.
* Adiciona 25 novas classificações do Adobe Mobile.
* Adiciona 5 novas métricas do Adobe Mobile.
* Adiciona novas dimensões do Adobe Mobile.
* Sincroniza dados com o Analytics a cada 15 minutos

**[!UICONTROL Analytics]** > **[!UICONTROL Administração]** > **[!UICONTROL Conjuntos de relatórios]** > **[!UICONTROL Editar configurações]** > **[!UICONTROL Gerenciamento de aplicativos]** > **[!UICONTROL Relatórios de aplicativos]**.

## Etapa 1. Ativar o App Reports {#section_FBADF80AED2B4978A904ABB770B3B931}

Ative o App Reports v3.0 para mensurar as seguintes métricas:

* **Aquisição:** rastreie URLs de referência para campanhas de download de aplicativo.
* **Ciclo de vida**: nível de base do relatório fornecido pela medição enviada em cada inicialização de aplicativo.
* **Ações do aplicativo:** relatórios e definição de caminho com base nas ações no aplicativo.
* **Valor da vida útil:** saiba mais sobre como os usuários agregam valor ao longo do tempo com os KPIs dos aplicativos (como compras, visualizações de anúncio, vídeos concluídos, compartilhamentos sociais, uploads de fotos).
* **Eventos programados**- meça o tempo (no aplicativo e o tempo total) entre ações-chave do aplicativo (como o tempo antes da primeira compra).

## Etapa 2. Ativar o rastreamento de localização {#section_2CCBD205191C4CA3B7B71A6F11FF97EC}

Habilitar o rastreamento de localização permite:

* Acompanhar os dados de latitude e longitude e relatá-los na Analysis Workspace e nos Mobile Services.
* Identificar, criar e visualizar Pontos de interesse (POIs) específicos nos Mobile Services. Os POIs devem ser definidos no arquivo de configuração do SDK móvel.
* Rastrear beacons bluetooth (UUID, maior, menor e proximidade).

## Etapa 3. (Opcional) Ativar/desativar os relatórios herdados e a atribuição para ocorrências em segundo plano {#section_1708BCAA87AA4884986F7532759C5DD4}

Ocorrências em segundo planto ativadas (ocorrências geradas quando o aplicativo está em segundo plano) significam que são tratadas como ocorrências em primeiro plano de fundo comuns. Agora eles aparecem em relatórios comuns e isso também afeta a atribuição. Esta configuração geralmente é desejável para manter a consistência com as implementações herdadas.

Em vez disso, recomendamos que você “inclua ocorrências em segundo plano” em um [conjunto de relatórios virtual](/help/components/vrs/vrs-about.md). Isso permite ver as ocorrências, mas elas não afetarão negativamente a visita e a contagem de visitantes.
As classificações móveis serão ativadas após habilitar **[!UICONTROL Gerenciamento de aplicativos]** > **[!UICONTROL Relatório de aplicativos]**.

Classificações são usadas para categorizar valores em grupos e relatórios no nível de grupo. Por exemplo, você pode classificar todas as campanhas de Pesquisa paga em uma categoria como termos de música pop e relatar o sucesso dessa categoria com relação a métricas como Instâncias (click-throughs) e conversão para eventos bem-sucedidos.

| Classificação | Definição |
|--- |--- |
| Data da primeira inicialização | Data da primeira execução após a instalação ou reinstalação.   DD/MM/AAAA |
| ID do aplicativo | Armazena o nome e a versão do aplicativo no seguinte formato:   `[AppName] [BundleVersion]`  Por exemplo, `myapp 1.1.` |
| Número de Lançamento | Número de vezes em que o aplicativo foi iniciado ou trazido para o plano de fundo. |
| Dias desde a primeira utilização | Número de dias desde a primeira execução. |
| Dias desde a última utilização | Número de dias desde a última utilização. |
| Hora do dia | Mede a hora em que o aplicativo foi inicializado e usa o formato numérico de 24 horas. Utilizado para hora do visitante para determinar os tempos de pico de uso. |
| Dia da semana | Número do dia da semana no qual o aplicativo foi iniciado. |
| Nome do dispositivo | Armazena o nome do dispositivo.  Cadeia de caracteres de dígitos separados por vírgulas que identifica o dispositivo. O primeiro número representa a geração do dispositivo e o segundo representa versões dos diferentes membros da família do dispositivo. |
| Versão do sistema operacional | Versão do sistema operacional. |
| Resolução | Largura x altura em pixels reais. |
| Valor da duração (eVar) | Preenchido pelos métodos trackLifetimeValue. |
| Fonte da aquisição |  |
| Meio da aquisição |  |
| Termo de aquisição |  |
| Conteúdo da aquisição |  |
| Nome da aquisição |  |
| Localização (abaixo de 10 km) | Preenchido pelos métodos trackLocation. |
| Localização (abaixo de 100 m) | Preenchido pelos métodos trackLocation. |
| Localização (abaixo de 1 m) | Preenchido pelos métodos trackLocation. |
| Nome do ponto de interesse | Preenchido pelos métodos trackLocation quando o dispositivo está em um POI definido. |
| Distância até o centro do ponto de interesse | Preenchido pelos métodos trackLocation quando o dispositivo está em um POI definido. |
| ID da mensagem no aplicativo |  |
| Mensagens no aplicativo online |  |
| Enviar adesão |  |
| ID da carga útil |  |