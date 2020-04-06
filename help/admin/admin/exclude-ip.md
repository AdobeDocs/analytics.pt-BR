---
description: É possível excluir dos seus relatórios alguns dados de endereços IP específicos, como atividades internas, testes e uso de sites por funcionário. A exclusão de dados melhora a precisão do relatório ao excluir dados de endereço IP. Além disso, você pode remover dados da negação de serviço ou de outros eventos mal-intencionados que podem distorcer os dados do relatório. Você pode configurar a exclusão ou usando seu firewall.
title: Excluir por endereço IP
topic: Admin tools
uuid: 1ed6105f-e7c5-4c4f-b8f4-e5f66d0824bb
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Excluir por endereço IP

É possível excluir dos seus relatórios alguns dados de endereços IP específicos, como atividades internas, testes e uso de sites por funcionário. A exclusão de dados melhora a precisão do relatório ao excluir dados de endereço IP. Além disso, você pode remover dados da negação de serviço ou de outros eventos mal-intencionados que podem distorcer os dados do relatório. Você pode configurar a exclusão ou usando seu firewall.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Exclude by IP]**

>[!NOTE] As ocorrências excluídas pelo endereço IP são cobradas como [chamadas do servidor](https://marketing.adobe.com/resources/help/pt_BR/reference/primary_server_calls.html).

## Excluir por cookie {#section_FB5A20AB5E514DA6BC596CC67F6A3A4C}

Permite que você exclua este computador de ser rastreado em sua conta. Se você optar por excluir seu computador, todos os dados gerados em seu computador não serão contados.

Esse recurso permite que você e seus colegas visitem seu site sem distorcer os dados de tráfego. Você pode querer usar esse recurso se não tiver um endereço IP estático (como ter uma conexão dial-up com a Internet por meio de um provedor de serviço) e quiser se excluir dos dados da sua conta.

| Elemento | Descrição |
|--- |--- |
| [!UICONTROL Add CNAME] | Gera um link de opção de não participação que você pode usar para excluir seu domínio. Para obter ajuda, entre em contato com os Usuários suportados de sua empresa. <br>Para excluir seu tráfego do relatório nos conjuntos de relatórios, acesse a página de opção de não participação de sua empresa e selecione a exclusão de seu navegador da medição. <br>Se sua implementação utiliza cookies de terceiros, sua página de opção de não participação está [aqui](https://democorp.112.2o7.net/optout.html?locale=pt_US&amp;popup=true). |

>[!NOTE] A exclusão por computador funciona somente se:
>
> * Você acessar seu site da mesma estação de trabalho.
> * Seus cookies estiverem ativados no navegador que estiver utilizando.
> * Seus cookies não forem excluídos.  Se os cookies forem excluídos, você deverá se excluir novamente.


## Excluir por endereço IP {#section_609FB6461529409D840111A32FEF5C3D}

Um endereço IP é um endereço da Internet. Todos os usuários da Internet recebem endereços IP numéricos (normalmente por meio de provedores de serviço da Internet) que atuam efetivamente como identificadores eletrônicos.

visualizações de página são contadas e visitantes de página exclusivos são identificados por meio de endereços IP. Ao excluir endereços IP da contagem, você pode impedir que a Adobe rastreie visitantes frequentes. Esse recurso pode permitir que você e seus colegas visitem seu site sem distorcer seus dados de tráfego. É possível excluir até 50 IPs diferentes.

Você pode usar indicadores curingas (*) para excluir um intervalo de endereços. Por exemplo, `[!DNL 0.0.*.0]`excluiria todos os endereços IP entre `[!DNL 0.0.0.0]` e `[!DNL 0.0.255.0]`. É possível excluir até 50 endereços IP diferentes.

## Excluir por firewall {#section_3E7BFB71ADD941D39F923DB9557AD9CD}

Também é possível bloquear a coleção de dados a partir de endereços IP específicos por meio de um Firewall.

Consulte o artigo Endereços [IP usados na Experience Cloud](https://marketing.adobe.com/resources/help/pt_BR/home/index.html#kb-adobe-ip-addresses) .

## Impacto da ofuscação de IP {#section_51B7529FFF16449CA016FDC51D87E2CA}

Se a ofuscação de IP estiver ativada, a exclusão de IP ocorrerá antes de o endereço IP ser ofuscado, de modo que os clientes não precisam fazer qualquer alteração ao ativar a ofuscação de IP.

Se o último octeto for removido, isso será feito antes da filtragem de IP. Dessa forma, o último octeto é substituído por um 0, e as regras de exclusão de IP devem ser atualizadas para corresponder aos endereços IP com um zero no final. A correspondência de * deve corresponder a 0.
