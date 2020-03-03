---
description: Os dados coletados em sites, aplicativos móveis ou carregados por meio de APIs de serviço da Web ou fontes de dados são processados e armazenados no Data Warehouse da Adobe. Esses dados de sequência de cliques brutos formam o conjunto de dados usado pelo Adobe Analytics.
keywords: clickstream;data feed;datafeed;Data Feed
title: Visão geral do feed de dados do Analytics
uuid: 6bdbe90c-e6ed-4bb0-b5be-24fd795adde4
translation-type: ht
source-git-commit: 984d6034d14cc4256d93bd4f7d1a7f01b63b71e9

---


# Visão geral do feed de dados do Analytics

Os feeds de dados são uma maneira avançada de obter dados brutos do Adobe Analytics. Esses dados brutos podem ser usados em outras plataformas fora da Adobe para uso a critério da sua organização. Os dados são fornecidos em lotes por hora, no final de cada hora, ou em lotes diários, no final de cada dia.

## Pré-requisitos

Certifique-se de atender a todos os requisitos a seguir antes de usar os feeds de dados.

* Tenha um site FTP e credenciais acessíveis. Os feeds de dados só podem ser enviados para um destino de servidor. Sua organização geralmente fornece credenciais FTP. A Adobe pode fornecer um local FTP com uma quantidade modesta de armazenamento, a seu pedido. Entre em contato com o Atendimento ao cliente para solicitar um destino FTP para feeds de dados.
* Uma implementação em funcionamento que envia dados para os servidores de coleta de dados da Adobe. Consulte [Validar e publicar uma implementação no Launch](/help/implement/launch/validate-publish-prod.md) no guia do usuário Implementar.
* Sua conta é um administrador de produto do Analytics ou pertence a um perfil de produto com acesso a feeds de dados.

## Etapas para começar

1. Faça logon em [experiencecloud.adobe.com](https://experiencecloud.adobe.com) usando as credenciais da Adobe ID.
2. Clique no ícone de 9 quadrados no canto superior direito e clique no logotipo colorido do Analytics.
3. Na barra de navegação superior, navegue até Admin > Feeds de dados.
4. Clique em [!UICONTROL Adicionar]. Uma nova página é exibida com três categorias principais: [!UICONTROL Informações do feed], [!UICONTROL Destino] e [!UICONTROL Definições da coluna de dados].
5. Preencha os campos [!UICONTROL Informações do feed].
   * Nome: qualquer nome que desejar, como &quot;Test data feed&quot;.
   * Conjunto de relatórios: selecione o conjunto de relatórios desejado.
   * Enviar email ao concluir: insira seu email.
   * Intervalo do feed: selecione o intervalo desejado (por hora ou por dia).
   * Atraso no processamento: pode ser deixado como [!UICONTROL Sem atraso].
   * Datas de início e término: selecione uma data inicial de vários dias atrás, e hoje como a data final.
6. Preencha os campos de [!UICONTROL Destino].
   * Tipo: FTP
   * Host: digite o URL de destino do FTP desejado. Por exemplo, `ftp://ftp.omniture.com`.
   * Caminho: pode ser deixado em branco
   * Nome de usuário: digite o nome de usuário para fazer logon no site FTP.
   * Senha e senha de confirmação: digite a senha para fazer logon no site FTP.
7. Preencha as [!UICONTROL Definições da Coluna de dados].
   * Selecione o modelo mais recente &quot;Todas as colunas da Adobe&quot; na lista suspensa.
   * Formato de compactação: Gzip
   * Tipo de empacotamento: vários arquivos
   * Manifesto: nenhum arquivo
8. Clique em [!UICONTROL Salvar] na parte superior direita.
9. Depois de salvo, o processamento de dados históricos é iniciado. Quando os dados terminam o processamento de um dia, o arquivo é colocado no site FTP.
10. Faça logon no site FTP usando o Windows Explorer ou um cliente FTP dedicado.
11. Baixe o arquivo de feed de dados compactado no computador local.
12. Descompacte o arquivo compactado usando um programa compatível com extensões de arquivo `.tar.gz`.
13. Abra o arquivo `hit_data.tsv` na planilha ou no aplicativo de banco de dados preferido para ver os dados brutos desse dia.

## Próximas etapas

Depois de entender o fluxo de trabalho básico de obtenção dos feeds de dados, você pode trabalhar com as equipes na organização para armazenar ou assimilar dados brutos em um banco de dados.

* [Criar um feed de dados](create-feed.md): Detalhes técnicos para criar um feed de dados, explicando campos individuais com mais detalhes
* [Gerenciar feeds](df-manage-feeds.md)de dados: Saiba mais sobre como navegar na interface do feed de dados
* [Conteúdo do feed de dados](c-df-contents/datafeeds-contents.md): Entenda o que está dentro do arquivo compactado
* [Definições de coluna de dados](c-df-contents/datafeeds-reference.md): Uma lista abrangente de todas as colunas disponíveis

## Recursos adicionais

Vídeo que navega na interface do feed de dados:

> [!VIDEO](https://www.youtube.com/watch?v=m_fb--gNtR4)
