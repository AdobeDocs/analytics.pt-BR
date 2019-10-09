---
description: Variáveis para gerenciamento de consentimento na Privacidade de dados.
seo-description: Variáveis para gerenciamento de consentimento na Privacidade de dados.
seo-title: Variáveis do gerenciamento de consentimento
solution: Analytics
title: Variáveis do gerenciamento de consentimento
topic: Ferramentas administrativas
translation-type: tm+mt
source-git-commit: 492e9405c82183f6beb6588cd0dc039fe15350f7

---


# Variáveis do gerenciamento de consentimento

Para fornecer assistência adicional no gerenciamento de dados de privacidade, um conjunto de variáveis reservadas está disponível para ser usado junto com variáveis de dados de contexto específicas.
Essas variáveis de gerenciamento de consentimento fornecem uma estrutura fácil de usar para capturar o status de consentimento em cada ocorrência de análise.

## Variáveis

* Recusa no gerenciamento de consentimento
   * Variável reservada: List Prop
   * Tipo: String delimitada por vírgula
   * Contém:
      * `contextData.['cm.ssf']=1` exibido como SSF
      * `contextData.['opt.dmp']=N` exibido como DMP
      * `contextData.['opt.sell']=N` exibido como SELL

* Aceitação no gerenciamento de Consentimento
   * Variável reservada: List Prop
   * Tipo: String delimitada por vírgula
   * Contém:
      * `contextData.['opt.dmp']=Y` exibido como DMP
      * `contextData.['opt.sell']=Y` exibido como SELL

## Relatórios

As Variáveis de gerenciamento de consentimento podem ser ativadas por meio de uma nova configuração de Privacidade disponível no Admin Console do Analytics.

Cada conjunto de relatórios pode ser configurado para:
1. Em Relatórios e análises, clique em Admin &gt; Report Suites.
1. Select the report suite(s) where you are collecting media data and click [!UICONTROL Edit Settings &gt; Privacy Management]

   ![](assets/rsm-privacy-select.png)

1. Clique no botão [!UICONTROL Ativar relatórios] de privacidade de dados.  Observação: após ativadas, essas variáveis não podem ser reativadas.

   ![](assets/rsm-privacy-enable.png)

1. Depois de habilitada, você verá uma mensagem de confirmação.

   ![](assets/rsm-privacy-config.png)

1. As variáveis reservadas agora estão disponíveis para relatório.  Consulte Aceitação do gerenciamento de consentimento e Aceitação do gerenciamento de consentimento.

   ![](assets/rsm-privacy-reports.png)

## Implementação

Três variáveis de dados de contexto foram predefinidas para funcionar com as variáveis reservadas do gerenciamento de consentimento.  Cabe a cada engenheiro de implementação determinar como gerenciar e persistir na configuração dessas variáveis.

Consulte Variáveis [de dados de](https://docs.adobe.com/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/context-data-variables.html) contexto para obter orientação geral sobre como implementar variáveis de dados de contexto.

### SSF

* Dados de contexto: `contextData.['cm.ssf']`
* Valores aceitos:
   * `1` - Ao enviar o valor `1`, isso indica que o encaminhamento pelo lado do servidor está em um estado de não participação. O valor `1` emparelhado com essa variável bloqueará o compartilhamento dessa ocorrência com o Adobe Audience Manager. Consulte Conformidade com [privacidade eletrônica do AAM.](https://docs.adobe.com/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/ssf-gdpr.html)
   * Nenhum outro valor é aceito para este parâmetro

### DMP

* Dados de contexto: `contextData.['opt.dmp']`
* Valores aceitos:
   * `N` - Ao enviar o valor `N`, isso indica que o consumidor está optando por não compartilhar nas plataformas de gerenciamento de dados. Observe que não há compartilhamento de bloqueio atual para o AAM.  Use o SSF para essa funcionalidade.
   * `Y` - Ao enviar o valor `Y`, isso indica que o consumidor está optando por compartilhar com plataformas de gerenciamento de dados.

### VENDER

* Dados de contexto: `contextData.['opt.sell']`
* Valores aceitos:
   * `N` - Ao enviar o valor `N`, isso indica que o consumidor está a optar por não partilhar ou vender os dados a terceiros.
   * `Y` - Ao enviar o valor `Y`, indica-se que o consumidor opta por partilhar ou vender os dados a terceiros.
