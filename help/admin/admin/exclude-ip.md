---
description: É possível excluir dos seus relatórios alguns dados de endereços IP específicos, como atividades internas, testes e uso de sites por funcionário. A exclusão de dados melhora a exatidão do relatório, pois exclui os dados do endereço IP. Além disso, você pode remover dados de negação de serviço, além de outros eventos mal-intencionados que podem causar um viés nos dados do relatório. Você pode configurar a exclusão ou usar seu firewall para isso.
seo-description: É possível excluir dos seus relatórios alguns dados de endereços IP específicos, como atividades internas, testes e uso de sites por funcionário. A exclusão de dados melhora a exatidão do relatório, pois exclui os dados do endereço IP. Além disso, você pode remover dados de negação de serviço, além de outros eventos mal-intencionados que podem causar um viés nos dados do relatório. Você pode configurar a exclusão ou usar seu firewall para isso.
seo-title: Excluir por endereço IP
solution: Analytics
title: Excluir por endereço IP
topic: Ferramentas administrativas
uuid: 1 ed 6105 f-e 7 c 5-4 c 4 f-b 8 f 4-e 5 f 66 d 0824 bb
translation-type: tm+mt
source-git-commit: 26ea8e41b9a45c87c339d4d4d56c914fbc44bae8

---


# Excluir por endereço IP

É possível excluir dos seus relatórios alguns dados de endereços IP específicos, como atividades internas, testes e uso de sites por funcionário. A exclusão de dados melhora a exatidão do relatório, pois exclui os dados do endereço IP. Além disso, você pode remover dados de negação de serviço, além de outros eventos mal-intencionados que podem causar um viés nos dados do relatório. Você pode configurar a exclusão ou usar seu firewall para isso.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Administrador]** &gt; **[!UICONTROL Excluir por IP]**

>[!NOTE]
>
>Hits marked as *bots* are billed as [server calls](https://marketing.adobe.com/resources/help/en_US/reference/primary_server_calls.html).

## Excluir por cookie {#section_FB5A20AB5E514DA6BC596CC67F6A3A4C}

Permite impedir o computador de ser rastreado em sua conta. Se você optar por excluir seu computador, todos os dados gerados a partir de seu computador não serão contados.

Esse recurso permite que você e seus colegas visitem seu site sem distorcer seus dados de tráfego. Você poderá usar este recurso caso não tenha um endereço IP estático (ex.: sua conexão é feita com linha telefônica por um provedor de Internet) e deseja excluir a si mesmo dos dados de sua conta.

| Elemento | Descrição |
|--- |--- |
| [!UICONTROL Adicionar CNAME] | Gera um link para opção de não participação que poderá usar para excluir seu domínio. Para obter ajuda, entre em contato com os Usuários suportados de sua empresa. <br>Para excluir seu tráfego do relatório nos conjuntos de relatórios, acesse a página de opção de não participação de sua empresa e selecione a exclusão de seu navegador da medição. <br>Se sua implementação utiliza cookies de terceiros, sua página de opção de não participação está [aqui](https://democorp.112.2o7.net/optout.html?locale=en_US&popup=true). |

>[!NOTE]
>
>A exclusão por computador funciona somente se:
>
>* Você acessar seu site da mesma estação de trabalho.
>* Seus cookies estiverem ativados no navegador que estiver utilizando.
>* Seus cookies não forem excluídos. Se os cookies forem excluídos, você deverá se excluir novamente.


## Excluir por endereço IP {#section_609FB6461529409D840111A32FEF5C3D}

Um endereço IP for um endereço da Internet. Todos os usuários da Internet forem endereços IP numéricos atribuídos (normalmente pelos provedores de serviço da Internet) que atuam de forma efetiva como identificadores eletrônicos.

As exibições de página são contadas e os visitantes de página únicos são identificados através do endereço IP. Ao excluir endereços IP da contagem é possível impedir que a Adobe rastreie visitantes frequentes. Esse recurso pode permitir que você e seus colegas visitem seu site sem distorcer seus dados de tráfego. É possível excluir até 50 endereços IP diferentes.

Você pode usar indicadores curinga (*) para excluir um intervalo de endereços. For example, `[!DNL 0.0.*.0]` would exclude all IP addresses between `[!DNL 0.0.0.0]` and `[!DNL 0.0.255.0]`. É possível excluir até 50 endereços IP diferentes.

## Excluir por firewall {#section_3E7BFB71ADD941D39F923DB9557AD9CD}

Também é possível bloquear a coleção de dados a partir de endereços IP específicos por meio de um Firewall.

Consulte o artigo [Endereços IP usados na Experience Cloud](https://marketing.adobe.com/resources/help/en_US/home/index.html#kb-adobe-ip-addresses).

## Impacto da ofuscação de IP {#section_51B7529FFF16449CA016FDC51D87E2CA}

Se a ofuscação de IP estiver ativada, a exclusão de IP ocorrerá antes de o endereço IP ser ofuscado, de modo que os clientes não precisam fazer qualquer alteração ao ativar a ofuscação de IP.

Se o último octeto for removido, isso ocorrerá antes da filtragem de IP. Assim, o último octeto será substituído por um 0, e as regras de exclusão de IP devem ser atualizadas para corresponder os endereços IP com um zero no final. A correspondência de * deve corresponder a 0.
