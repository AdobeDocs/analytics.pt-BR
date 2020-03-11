---
description: Configurações que definem como todos os relatórios são exibidos e as informações que mapeiam as opções de menu padrão para o local no menu simplificado.
title: Configurações e navegação da exibição de relatórios
topic: Reports,Reports and analytics
uuid: e7e571ce-a1cf-4714-b400-9571805ceeac
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Configurações e navegação da exibição de relatórios

Configurações que definem como todos os relatórios são exibidos e as informações que mapeiam as opções de menu padrão para o local no menu simplificado.

## Configurações e navegação da exibição de relatórios {#concept_09832A2CA0FF4982B1AA37C1B635220B}

**[!UICONTROL Análises]** > **[!UICONTROL Componentes]** > **[!UICONTROL Configurações de relatório]**

<!--Meike, I replaced this table with one from https://marketing.adobe.com/resources/help/en_US/sc/user/report_settings.html -bob -->

| Elemento | Descrição |
|--- |--- |
| **Configurações gerais** |  |
| Incluir seção de métricas relacionadas | Métricas relacionadas estão intimamente ligadas ao relatório que você está exibindo no momento (por exemplo, as cinco principais páginas do relatório de exibições de página). |
| Exibe média na Internet na seção de detalhes | Indica o valor médio de determinada estatística, espalhada por milhares de sites da Web corporativos. Quando ativada, esta seção é exibida como uma coluna separada no resumo do relatório e nas seções de detalhes do relatório. Este recurso é utilizado apenas pelos relatórios de tráfego no grupo de tecnologia, bem como os mecanismos de pesquisa, idiomas e relatórios domínios. |
| Mostrar a estrutura de menus padrão da Adobe | Ignora as configurações em Ferramentas de administração, onde os administradores personalizam menus de relatório para atender às preferências do usuário, retornando o menu de relatório para as configurações padrão. |
| Determina larguras de coluna ao exibir relatórios | Força as larguras de coluna de relatório para uma consistência esteticamente agradável. Essa configuração é útil quando mais de três métricas são exibidas.. |
| **Gráficos e Tabelas** |  |
| Selecionar finais de semana em gráficos de análise de tendências | Destaca verticalmente as datas de fim de semana de gráficos de relatório de tendências. Pode ser muito mais fácil avaliar relatórios de tendência quando os fins de semana são identificados. |
| Incluir previsão no gráfico e no resumo | Estima quando uma determinada estatística irá ocorrer no futuro. A previsão é exibido na seção do resumo do relatório quando ativado. |
| Incluir Eventos de calendário nos Relatórios | Acompanha o desempenho do site em relação a eventos específicos. Quando ativado, esses eventos são exibidos em seus relatórios. |
| Use gráficos em Flash | Habilita gráficos Flash em seus relatórios. Gráficos em Flash fornecem imagens mais nítidas e mais interativas para os relatórios, mas não permitem que você copie ou salve as imagens facilmente. Para obter a funcionalidade de copiar e salvar, desabilite essa opção (as imagens serão no formato .gif). Se você desmarcar essa opção, o botão copiar gráfico não será exibido na barra de ferramentas do relatório. |
| Exibe dados de &quot;Todos os outros&quot; em gráficos selecionados | Exibe todos os outros abaixo dos cinco primeiros agrupados em um único objeto. (Gráficos de barras mostram as cinco principais páginas da Web ou outros dados em seu relatório.) |
| Exibir os dados &quot;Nenhum&quot;, &quot;Não especificado&quot; e &quot;Digitado/Marcado&quot; nos gráficos dos relatórios | Exibe métricas nas quais não existe crédito recebido para o valor da métrica especificada. |
| Mostrar minigráfico nos relatórios classificados | Exibe um minigráfico no campo de totais dos relatórios classificados. Isto fornece uma visão rápida da tendência geral, sem gerar um relatório separado. |
| **Aceleração** |  |
| Ativa o Acelerador de relatório para exibir os relatórios mais rapidamente | Permite que o acelerador de relatório, que usa um algoritmo com base em tempo para colocar em cache relatórios solicitados recentemente e examina apenas os itens únicos mais frequentes, resultando na entrega ainda mais rápida de relatórios. Ao fazer o cache dos relatórios solicitados por 15 minutos, o acelerador de relatório pode recuperar esses relatórios para solicitações subsequentes quase que instantaneamente. Esta configuração é útil quando se navega para frente e para trás, para a impressão de relatórios ou para o acesso frequente aos mesmos relatórios. Quando desativado, o sistema gera novamente os relatórios cada vez que eles são solicitados. |
| Ativa o Painel do acelerador e exibe as versões em cache disponíveis | Habilita o acelerador de painel, que armazena uma versão em cache de seu painel para exibição posterior. Ao fazer o cache da exibição de seu painel por 24 horas, o acelerador de painel é capaz de recuperar essa exibição quase que instantaneamente, pois a consulta ao banco de dados e o processamento intensivo é feito com antecedência. Se a versão disponível em cache ultrapassar o limite de 24 horas, um novo painel é gerado e uma nova versão é criada em cache. Da mesma forma, uma nova versão em cache é criada sempre que você atualizar o painel (ou qualquer reportlet exibido no painel). O cache tem base no usuário. Outros usuários visualizando um painel comum verão uma versão com base em sua própria utilização do acelerador e da atualização do painel. |
| Ative a aceleração de rede para melhorar o desempenho dos relatórios | Aumenta a velocidade de entrega de dados para a sua localização, otimizando o caminho entre a infraestrutura Adobe e seu ambiente. |
| Habilite a aceleração regional para ter uma experiência do usuário mais rápida na China | O Acelerador regional usa domínios acelerados específicos de região para fornecer uma experiência de usuário mais rápida em uma região em particular. No momento, a aceleração regional é compatível somente na China. Habilitar esse recurso para usuários que não estão localizados na China resultará em uma experiência de usuário mais lenta. Depois de habilitar a aceleração regional, é necessário fazer logon novamente para que a configuração seja aplicada. Se você deseja desabilitar o Acelerador regional, desmarque esta caixa de seleção. |
| **Idioma/Moeda/Codificação** |  |
| Separador de milhares | Selecione um separador para cada milhares (decimal ou vírgula). Muitos países utilizam um número decimal para separar o número de milhares. (Este separador é aplicado a todos os números de todo o sistema, não apenas à moeda.) |
| Usar a moeda padrão do conjunto de relatórios | Especifica se a moeda padrão do conjunto de relatórios será ou não usada. |
| Moeda | A moeda para a qual você deseja converter seus dados. Quando um valor é selecionado nessa configuração, os dados armazenados no banco de dados não são afetados, mas é mostrado como um valor convertido com base na taxa de conversão de moeda do dia. Quando as opções de moeda não são configuradas (definidas como padrão) não ocorre nenhuma conversão de moeda, e todos os valores são armazenados e exibidos em dólares dos EUA (USD). Para converter a moeda quando os dados são processados (antes de serem exibidos), entre em contato com o seu gerente de contas do. |
| Codificação do Relatório Programado | Codificação SHIFT-JIS de caracteres japoneses. EUC-JP para código Unix Extended, principalmente para japonês, coreano e chinês simplificado. |
| Caractere de Separação do CSV | O caractere que você deseja usar para separar os valores CSV. |

## Menu de navegação {#concept_1525EE52F8094535B4240F03B70DD75D}

<!-- 

nav_menu.xml

 -->

Se você estiver acostumado ao menu padrão, a seguinte tabela facilita a localização de opções de menu no menu simplificado.

| Localização no Menu padrão | Localização no Menu simplificado |
|---|---|
| **Métricas de site** |  |  |
|  | Visão geral do site | Métricas > Visão geral do site |
|  | Métricas principais | Métricas > Métricas principais |
|  | Exibições de página | Métricas > Exibições de página |
|  | Visitas | Métricas > Visitas |
|  | Visitantes | Métricas > Visitantes |
|  | Tempo gasto por visita | Métricas > Tempo gasto por visita |
|  | Tempo antes do evento | Conversão > Tempo antes do evento |
|  | Compras | Métricas > Compras |
|  | Carrinho de Compras | Métricas > Carrinho de compras |
|  | Eventos Personalizados | Métricas > Eventos personalizados |
|  | Bots | Público-alvo > Bots |
|  | Detecção de anomalias | Métricas > Detecção de anomalias |
|  | Tempo real | Métricas > Tempo real |
| **Conteúdo do site** |  |  |
|  | Páginas | Conteúdo > Páginas |
|  | Seções do site | Conteúdo > Seções do site |
|  | Servidores | Conteúdo > Servidores |
|  | Links | Navegação > Links personalizados; Navegação > Links de saída; Navegação > ClickMap; Navegação > Downloads de arquivos |
|  | Páginas não encontradas | Navegação > Páginas não encontradas |
| **Dispositivo móvel** |  |  |
|  | Dispositivos | Público-alvo > Dispositivo móvel > Dispositivos |
|  | Tipo de dispositivo | Público-alvo > Dispositivo móvel > Tipo de dispositivo |
|  | Fabricante | Público-alvo > Dispositivo móvel > Fabricante |
|  | Tamanho de tela | Público-alvo > Dispositivo móvel > Tamanho da tela |
|  | Altura de tela | Público-alvo > Dispositivo móvel > Altura da tela |
|  | Largura de tela | Público-alvo > Dispositivo móvel > Largura da tela |
|  | Suporte a cookies | Público-alvo > Dispositivo móvel > Suporte a cookies |
|  | Suporte de imagem | Público-alvo > Dispositivo móvel > Suporte da imagem |
|  | Intensidade de cor | Público-alvo > Dispositivo móvel > Intensidade de cor |
|  | Suporte de áudio | Público-alvo > Dispositivo móvel > Suporte de áudio  |
|  | Suporte de vídeo | Público-alvo > Dispositivo móvel > Suporte de vídeo  |
|  | Sistema operacional | Público-alvo > Dispositivo móvel > Sistema operacional |
| **Caminhos** |  |  |
|  | Páginas | Navegação > Caminhos > Páginas |
|  | Termos de pesquisa interna | Navegação > Caminhos > Termos de pesquisa interna |
| **Fontes de Tráfego** |  |  |
|  | Palavra-chave de pesquisa - Tudo | Fontes de tráfego > Palavra-chave de pesquisa - Tudo |
|  | Palavra-chave de pesquisa - Paga | Fontes de tráfego > Palavra-chave de pesquisa - Paga |
|  | Palavra-chave de pesquisa - Natural | Fontes de tráfego > Palavra-chave de pesquisa - Natural |
|  | Mecanismos de Pesquisa - Todos | Fontes de tráfego > Mecanismos de pesquisa - Tudo |
|  | Mecanismos de Pesquisa - Pagos | Fontes de tráfego > Mecanismos de pesquisa - Pago |
|  | Mecanismos de Pesquisa - Naturais | Fontes de tráfego > Mecanismos de pesquisa - Natural |
|  | Toda a classificação da página de pesquisa | Fontes de tráfego > Todas as classificações de página de pesquisa |
|  | Domínios de referência | Fontes de tráfego > Domínios de referência |
|  | Domínios de referência originais | Fontes de tráfego > Domínios de referência original |
|  | Referenciadores | Fontes de tráfego > Referenciadores |
|  | Tipos de Referenciador | Fontes de tráfego > Tipos de referenciador |
| **Campanhas** |  |  |
|  | Funil de Conversão de Campanha | Fontes de tráfego > Campanhas > Funil de conversão da campanha |
|  | Código de acompanhamento | Fontes de tráfego > Campanhas > Código de rastreamento |
| **Produtos** |  |  |
|  | Funil de conversão de produtos | Conversão > Produtos > Funil de conversão de produtos |
|  | Produtos | Conversão > Produtos > Produtos |
|  | Venda cruzada | Conversão > Produtos > Venda cruzada |
|  | Categorias | Conversão > Produtos > Categorias |
| **Retenção de visitante** |  |  |
|  | Frequência de Retorno | Público-alvo > Retenção de visitantes > Frequência de retorno |
|  | Visitas de Retorno | Público-alvo > Retenção de visitantes > Visitantes de retorno |
|  | Visitas de Retorno Diário | Público-alvo > Retenção de visitantes > Visitantes de retorno diários |
|  | Número da visita | Público-alvo > Retenção de visitantes > Número de visitas |
|  | Ciclo de Vendas | Público-alvo > Retenção de visitantes > Ciclo de vendas |
| **Perfil do visitante** |  |  |
|  | GeoSegmentation | Público-alvo > Perfil do visitante > Segmentação geográfica |
|  | Idiomas | Público-alvo > Perfil do visitante > Idiomas |
|  | Fusos horários | Público-alvo > Perfil do visitante > Fusos horários |
|  | Domínios | Público-alvo > Perfil do visitante > Domínios |
|  | Domínios de nível superior | Público-alvo > Perfil do visitante > Domínios de nível superior |
|  | Tecnologia | Público-alvo > Perfil do visitante > Tecnologia |
|  | Estado do visitante | Público-alvo > Perfil do visitante > Estado do visitante |
|  | Código postal/CEP do visitante | Público-alvo > Perfil do visitante > CEP do visitante/código postas |
| **Conversão personalizada** |  |  |
|  | Conversão personalizada 1-10 | Conversão > Conversão personalizada > Conversão personalizada 1-10 |
|  | Conversão personalizada 11-20 | Conversão > Conversão personalizada > Conversão personalizada 11-20 |
| **Tráfego personalizado** |  |  |
|  | Tráfego personalizado 1-10 | Conteúdo > Tráfego personalizado > Tráfego personalizado 1-10 |
| **Test&amp;Target** |  | Conversão > Test&amp;Target |
| **Survey** |  | Público-alvo > Survey |
| **Canais de marketing** |  |  |
|  | Relatório de Visão Geral de Canal | Fontes de tráfego > Canais de marketing > Relatório de visão geral do canal |
|  | Canal de Primeiro Contato | Fontes de tráfego > Canais de marketing > Canal de primeiro toque |
|  | Detalhe de Canal de Primeiro Contato | Fontes de tráfego > Canais de marketing > Detalhe do canal de primeiro toque |
|  | Canal de Último Contato | Fontes de tráfego > Canais de marketing > Canal de último toque |
|  | Detalhe de Canal de Último Contato | Fontes de tráfego > Canais de marketing > Detalhe do canal de último toque |
| **Aplicativo remoto** |  |  |
|  | Visão geral dos aplicativos móveis | Conteúdo > Aplicativo móvel > Visão geral do aplicativo móvel |
|  | Relatórios de ciclo de vida | Conteúdo > Aplicativo móvel > Relatórios de ciclo de vida |
| **Relatórios personalizados** |  |  |
|  | Os relatórios personalizados aparecem somente se você tem qualquer configuração. | Relatórios personalizados |
|  |  |  |

