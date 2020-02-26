---
description: Um Widget de publicação é um contêiner que permite a incorporação de relatórios de marketing (somente marcadores e painéis) em uma página da Web. As pessoas que não possuem acesso aos relatórios de marketing em sua organização podem visualizar os dados pertinentes.
title: Widget de publicação
topic: Admin tools
uuid: 4ecf6a5a-8a4e-4707-b282-39890eba3c5d
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Widget de publicação

Um Widget de publicação é um contêiner que permite incorporar relatórios do Analytics (marcadores e painéis) a uma página da Web. As pessoas que não possuem acesso aos relatórios do Analytics em sua organização podem visualizar os dados pertinentes.

Por exemplo, você poderia fornecer um painel para que os executivos da empresa pudessem exibir o número de visitantes à página, o número de visitantes únicos à página e assim por diante.

> [!CAUTION] Não é necessário uma autenticação para visualizar dados publicados pelo Widget de publicação. Devido a isso, você deve considerar os dados publicados como tão seguros quando os dados enviados para um grupo por email ou servidor de lista. Use o widget somente de acordo com os padrões de segurança, requisitos contratuais existentes e legislação aplicável de sua organização. O Widget de publicação fornece a capacidade de restringir, pelo endereço IP ou caminho de domínio, onde você pode publicar dados. Entretanto, esses mecanismos são destinados exclusivamente a impedir a distribuição não intencional de dados e não são uma forma eficaz de proteger o acesso a dados distribuídos através do Widget de publicação.
>
> A Adobe não se responsabiliza por dados expostos através do Widget de publicação.

Observação: como o Widget de publicação tem o potencial de direcionar grandes volumes de tráfego, a Adobe reserva o direito, a seu próprio critério, de desativar os Widgets de publicação de uma empresa para uso impróprio ou tráfego excessivo que esteja afetando o desempenho geral.

## Solução de problemas - Publicação de cache do Widget

A primeira vez que qualquer usuário visualiza o widget de publicação implantado, este executa o relatório. Depois que o relatório é executado, os resultados são adicionados a um cache e continuam válidos por 1 hora. Qualquer usuário subsequente que visualizar o widget de publicação na próxima hora visualizará a versão em cache (ela retornará instantaneamente). Depois de uma hora, qualquer usuário subsequente que visualizar o widget de publicação o forçará a executar o relatório novamente e, em seguida, esses resultados são armazenados em cache, e assim por diante. Desta forma, os dados terão no máximo uma hora.

Se você notar diferenças de dados entre o Widget de publicação e a interface de relatório, pode ser necessário apagar o cache do Widget de publicação.

1. Clique no Widget de publicação (para que o widget tenha um foco).
1. Clique em **[!UICONTROL Salvar]** no widget.
1. Execute o widget novamente. (O modo de visualização não utiliza o cache do widget).

> [!NOTE] Os widgets de publicação mostram apenas a primeira coluna dos dados de um relatório.

## Descrições de widgets de publicação {#section_D67478AECCA946B19A3E4C7071EB4871}

| Elemento | Descrição |
|--- |--- |
| Nome | O nome do widget. |
| Descrição | (Opcional) Especificar uma descrição para o widget. |
| Relatório | Na lista suspensa superior Relatório, selecione uma pasta ou painel. Na lista suspensa inferior Relatório, selecione um reportlet ou marcador.  Esses relatórios não exigem uma autenticação do visitante. <br>Quando um visitante carrega uma página da Web que inclui um Widget de publicação, o widget exibe automaticamente o relatório associado por meio dos dados atuais do relatório. As alterações feitas em um Widget de publicação, como a alteração do relatório associado, atualizam automaticamente a saída do relatório de todas as páginas da Web que usam esse widget, sem que seja preciso voltar a implantar as páginas da Web.</br> |
| Destino | Especificar o destino do widget.   Os destinos devem estar em um formato válido de URL, que inclua o prefixo https:// ou https://. Os Destinos de widget de publicação são inclusivos, o que significa que o Widget de publicação funciona em todos os URLs que incluem o Destino especificado. <br>Por exemplo, o Destino https://www.corp1.com/sales/ permite Widgets de publicação em todas as páginas da Web, na página de vendas ou abaixo dela, no site www.corp1.com.</br> |
