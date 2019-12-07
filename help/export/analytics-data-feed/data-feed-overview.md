---
description: Os dados coletados em sites, aplicativos móveis ou carregados por meio de APIs de serviço da Web ou fontes de dados são processados e armazenados no Data Warehouse da Adobe. Esses dados de sequência de cliques brutos formam o conjunto de dados usado pelo Adobe Analytics.
keywords: clickstream;data feed;datafeed;Data Feed
title: Visão geral do feed de dados do Analytics
uuid: 6bdbe90c-e6ed-4bb0-b5be-24fd795adde4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Visão geral do feed de dados do Analytics

Os feeds de dados são uma maneira avançada de obter dados brutos do Adobe Analytics. Esses dados brutos podem ser usados em outras plataformas fora da Adobe para uso a critério de sua organização. Os dados são fornecidos em lotes por hora, no final de cada hora, ou em lotes diários, no final de cada dia.

## Pré-requisitos

Certifique-se de atender a todos os requisitos a seguir antes de usar os feeds de dados.

* Tenha um site FTP e credenciais acessíveis. Os feeds de dados só podem ser enviados para um destino de servidor. Sua organização geralmente fornece credenciais FTP. A Adobe pode fornecer um local FTP com uma quantidade modesta de armazenamento, a seu pedido. Entre em contato com o Atendimento ao cliente para solicitar um destino FTP para feeds de dados.
* Uma implementação em funcionamento que envia dados para os servidores de coleta de dados da Adobe. Consulte [Validar e publicar uma implementação no Launch](../../implement/implement-with-launch/validate-publish-prod.md) no guia do usuário Implementar.
* Sua conta é um administrador de produto do Analytics ou sua conta pertence a um perfil de produto com acesso a feeds de dados.

## Etapas para começar

1. Faça logon em [experiencecloud.adobe.com](https://experiencecloud.adobe.com) usando as credenciais da Adobe ID.
2. Clique no ícone de 9 quadrados no canto superior direito e clique no logotipo colorido do Analytics.
3. Na barra de navegação superior, navegue até Admin &gt; Feeds de dados.
4. Clique em [!UICONTROL Adicionar]. Uma nova página é exibida com três categorias principais: Informações [!UICONTROL do]feed, [!UICONTROL Destino]e Definições [!UICONTROL da coluna]de dados.
5. Preencha os campos Informações [!UICONTROL do] feed.
   * Nome: Qualquer nome desejado, como "Test data feed".
   * Conjunto de relatórios: Selecione o conjunto de relatórios desejado.
   * Enviar email ao concluir: Insira seu email.
   * Intervalo do feed: Selecione o intervalo desejado (por hora ou por dia).
   * Atraso no processamento: Pode ser deixado como [!UICONTROL Sem Atraso].
   * Datas de início e término: Selecione uma data inicial de vários dias atrás e hoje como a data final.
6. Preencha os campos [!UICONTROL de Destino] .
   * Tipo: FTP
   * Host: Digite o URL de destino do FTP desejado. Por exemplo, `ftp://ftp.omniture.com`.
   * Caminho: Pode ser deixado em branco
   * Nome de usuário: Digite o nome de usuário para fazer logon no site FTP.
   * Senha e senha de confirmação: Digite a senha para fazer logon no site FTP.
7. Preencha as Definições [!UICONTROL da Coluna]de Dados.
   * Selecione o modelo mais recente "Todas as colunas da Adobe" na lista suspensa.
   * Formato de compactação: Gzip
   * Tipo de empacotamento: Vários arquivos
   * Manifesto: Nenhum arquivo
8. Clique em [!UICONTROL Salvar] na parte superior direita.
9. Depois de salvo, o processamento de dados históricos é iniciado. Quando os dados terminam o processamento de um dia, o arquivo é colocado no site FTP.
10. Faça logon no site FTP usando o Windows Explorer ou um cliente FTP dedicado.
11. Baixe o arquivo de feed de dados compactado no computador local.
12. Descompacte o arquivo compactado usando um programa compatível com extensões `.tar.gz` de arquivo.
13. Abra o `hit_data.tsv` arquivo na planilha ou no aplicativo de banco de dados preferido para ver os dados brutos desse dia.

## Próximas etapas

Depois de entender o fluxo de trabalho básico de obtenção de feeds de dados, você pode trabalhar com equipes em sua organização para armazenar ou assimilar dados brutos em um banco de dados.

* [Criar um feed](create-feed.md)de dados: Detalhes técnicos para criar um feed de dados, explicando campos individuais com mais detalhes
* [Gerenciar feeds](df-manage-feeds.md)de dados: Saiba mais sobre como navegar na interface do feed de dados
* [Conteúdo](c-df-contents/datafeeds-contents.md)do feed de dados: Entenda o que está dentro do arquivo compactado
* [Definições](c-df-contents/datafeeds-reference.md)da coluna de dados: Uma lista abrangente de todas as colunas disponíveis

## Recursos adicionais

Vídeo que navega na interface do feed de dados:

> [!VIDEO](https://www.youtube.com/watch?v=m_fb--gNtR4)
