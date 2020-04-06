---
description: Um Widget de publicação é um container que permite a incorporação de relatórios de marketing (marcadores e painéis) em uma página da Web. As pessoas em sua organização que não têm acesso aos relatórios de marketing podem visualização dados pertinentes.
title: Widget de publicação
topic: Admin tools
uuid: 4ecf6a5a-8a4e-4707-b282-39890eba3c5d
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Widget de publicação

Um Widget de publicação é um contêiner que permite incorporar relatórios do Analytics (marcadores e painéis) a uma página da Web. As pessoas que não possuem acesso aos relatórios do Analytics em sua organização podem visualizar os dados pertinentes.

Por exemplo, você poderia fornecer um painel para que os executivos da empresa pudessem exibir o número de visitantes à página, o número de visitantes únicos à página e assim por diante.

>[!CAUTION] Não é necessário uma autenticação para visualizar dados publicados pelo Widget de publicação. Devido a isso, você deve considerar os dados publicados como tão seguros quando os dados enviados para um grupo por email ou servidor de lista. Use o widget somente de acordo com as normas de segurança de sua organização, os requisitos contratuais existentes e a lei aplicável. O Widget de publicação fornece a capacidade de restringir, por endereço IP ou caminho de domínio, onde você pode publicar dados. No entanto, esses mecanismos são destinados exclusivamente a impedir a distribuição não intencional de dados e não são uma forma eficaz de proteger o acesso aos dados distribuídos por meio do Widget de publicação.
>
> A Adobe não assume nenhuma responsabilidade por dados expostos por meio do Widget de publicação.

Como o Widget de publicação pode potencialmente direcionar grandes volumes de tráfego, a Adobe reserva o direito, a seu critério exclusivo, de desativar os widgets de publicação do empresa para uso impróprio ou tráfego excessivo que esteja afetando o desempenho geral.

## Solução de problemas - Publicação de cache do Widget

Na primeira vez que qualquer usuário vê o widget de publicação implantado, o widget executa o relatório. Após a execução do relatório, os resultados são adicionados a um cache e são válidos por 1 hora. Qualquer usuário subsequente que visualização no widget de publicação na próxima hora visualizará a versão em cache (ela retornará instantaneamente). Depois de uma hora, qualquer usuário subsequente que visualização o widget de publicação forçará a execução do relatório novamente, e esses resultados serão armazenados em cache e assim por diante. Dessa forma, é garantido que os dados tenham no máximo uma hora.

Se você observar diferenças de dados entre o Widget de publicação e a interface do relatórios, talvez seja necessário limpar o cache do Widget de publicação.

1. Clique no Widget de publicação (para que o widget tenha foco).
1. Click **[!UICONTROL Save]** on the widget.
1. Execute novamente o widget. (O modo de Pré-visualização não usa o cache do widget.)

>[!NOTE] Os widgets de publicação mostram apenas a primeira coluna dos dados de um relatório.

## Descrições de widgets de publicação {#section_D67478AECCA946B19A3E4C7071EB4871}

| Elemento | Descrição |
|--- |--- |
| Nome | O nome do widget. |
| Descrição | (Opcional) Especifique uma descrição para o widget. |
| Relatório | Na lista suspensa superior Relatório, selecione uma pasta ou um painel. Na lista suspensa inferior Relatório, selecione um reportlet ou marcador.  Esses relatórios não exigem uma autenticação do visitante. <br>Quando um visitante carrega uma página da Web que inclui um Widget de publicação, o widget exibe automaticamente o relatório associado por meio dos dados atuais do relatório. As alterações feitas em um Widget de publicação, como a alteração do relatório associado, atualizam automaticamente a saída do relatório de todas as páginas da Web que usam esse widget, sem que seja preciso voltar a implantar as páginas da Web.</br> |
| Destino | Especificar o destino do widget.   Os destinos devem estar em um formato válido de URL, que inclua o prefixo https:// ou https://. Os Destinos de widget de publicação são inclusivos, o que significa que o Widget de publicação funciona em todos os URLs que incluem o Destino especificado. <br>Por exemplo, o Destino https://www.corp1.com/sales/ permite Widgets de publicação em todas as páginas da Web, na página de vendas ou abaixo dela, no site www.corp1.com.</br> |
