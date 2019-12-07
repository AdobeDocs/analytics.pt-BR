---
description: A serialização de eventos é um processo de implementação de medidas, usado para evitar que eventos duplicados sejam inseridos nos relatórios da Adobe. Isso pode ocorrer quando um usuário atualiza uma mesma página várias vezes, navega até uma mesma página várias vezes ou salva a página da Web em seu computador (por exemplo, se um cliente salvar a página de confirmação de uma compra em seu computador, os pedidos e a receita serão contados todas as vezes que ele a acessar; isso, é claro, se a serialização não estiver configurada).
keywords: Analytics Implementation
title: Visão geral da serialização de eventos
topic: Developer and implementation
uuid: 8c7883bb-5ba4-4440-af80-c0d15867570c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Visão geral da serialização de eventos

A serialização de eventos é um processo de implementação de medidas, usado para evitar que eventos duplicados sejam inseridos nos relatórios da Adobe. Isso pode ocorrer quando um usuário atualiza uma mesma página várias vezes, navega até uma mesma página várias vezes ou salva a página da Web em seu computador (por exemplo, se um cliente salvar a página de confirmação de uma compra em seu computador, os pedidos e a receita serão contados todas as vezes que ele a acessar; isso, é claro, se a serialização não estiver configurada).

A [!UICONTROL serialização de eventos] é útil nas seguintes circunstâncias:

* Uma página pode ser recarregada ou atualizada e enviar um evento várias vezes. A [!UICONTROL serialização de eventos] impede a recontagem dos eventos com o uso de um número de série para cada evento.
* O usuário guarda a página em seu computador para uma revisão posterior. Este cenário é muito comum em páginas de confirmação de compra, para a análise dos recibos de compra. A [!UICONTROL serialização de eventos] impede que a página seguinte seja recarregada pela recontagem de eventos.

> [!NOTE] As fontes de dados não são compatíveis com a serialização de eventos ou a eliminação da duplicação.

Este documento descreve o processo de implementação da [!UICONTROL serialização de eventos] para eventos de [!UICONTROL conversão] e [!UICONTROL personalização]. Para usar a [!UICONTROL Serialização de eventos], primeiro você precisa ativá-la em **[!UICONTROL Administração]** &gt; **[!UICONTROL Conjunto de relatórios]** &gt; **[!UICONTROL [[selecione o conjunto de relatórios]]]** &gt; **[!UICONTROL Editar configurações]** &gt; **[!UICONTROL Eventos bem-sucedidos]** . Em seguida, selecione quais eventos você deseja registrar na coluna [!UICONTROL Registro exclusivo de evento].

## Comportamento padrão {#section_892BB2BEFC434B69869D4504A8B54308}

O comportamento padrão é contar cada instância de um evento. Um evento é definido para cada [!UICONTROL exibição de página] contada, mesmo em recarregamentos ou atualizações de página. A variável [!UICONTROL s.purchaseID] é usada para identificar unicamente cada pedido (compra). Isso permite a um usuário recarregar a página de pedido sem recontar o pedido, a receita ou os produtos. Um recurso semelhante está disponível para todos os eventos. Ele inclui eventos predefinidos, como [!UICONTROL prodView] e [!UICONTROL scCheckout], bem como todos os eventos personalizados.

<!-- 

event_serialization_impl.xml

 -->

Para usar a [!UICONTROL Serialização de eventos], primeiro você precisa ativá-la em **[!UICONTROL Administração]** &gt; **[!UICONTROL Conjunto de relatórios]** &gt; **[!UICONTROL [[selecione o conjunto de relatórios]]]** &gt; **[!UICONTROL Editar configurações]** &gt; **[!UICONTROL Eventos bem-sucedidos]** . Em seguida, selecione quais eventos você deseja registrar na coluna [!UICONTROL Registro exclusivo de evento]. Há três configurações diferentes possíveis para um evento.

**Sempre registrar evento**: esse é o comportamento padrão de todos os eventos quando estão ativados inicialmente. Todos os eventos incluídos em solicitações de imagem são enviados diretamente para o Analytics, incluindo os recarregamentos de página.

**Registrar uma vez por visita**: um evento com essa configuração ativada rastreará somente a primeira instância desse evento em determinada visita. Depois que uma nova visita começa, todos os novos eventos com essa configuração ativada poderão ser rastreados novamente. Esta é uma maneira eficaz de atenuar eventos duplicados por meio da atualização da página do navegador.

**Usar ID de evento**: esta configuração permite que você associe cada evento a uma ID exclusiva. Caso o Analytics encontre uma eventID que já tenha sido visto anteriormente com essa mesma variável, ela não será contabilizada no relatório.

O único evento que não pode ter a serialização habilitada é o evento de compra, pois ele utiliza a variável s.purchaseID. O restante dos eventos de comércio eletrônico e personalizados podem ter essas configurações ativadas.

* Use um identificador exclusivo para acionar um evento uma vez por ID exclusiva.
* Envie vários eventos, depois use a configuração do Analytics para permitir um acionamento de evento por visita.

Para implementar a [!UICONTROL serialização de eventos], especifique uma ID exclusiva para event1:1234ABCD.

## Serialização de eventos - uma vez por ID exclusiva {#section_8806E48B497546F5A335383FB8627694}

Quando a [!UICONTROL serialização de eventos] for implementada e o [!DNL Analytics] receber um número duplicado, ele irá ignorar o evento. Um evento só é contado una vez por valor exclusivo. Se o número for exclusivo, outra instância do evento será contada, como mostrado no exemplo a seguir:

| Nome do Usuário | Descrição | Sintaxe do evento | Contagem total do Event1 do Analytics |
|---|---|---|---|
| John | O usuário exibe a página pela primeira vez. | event1:1000 | 1 |
| John | O usuário recarrega a página (pode haver falha no envio de um formulário e causar o recarregamento da página). | event1:1000 | 1 |
| Stacy | O usuário exibe a página pela primeira vez. | event1:1001 | 2 |
| Stacy | O usuário recarrega a página (pode haver falha no envio de um formulário e causar o recarregamento da página). | event1:1001 | 2 |
| Jill | O usuário exibe a página pela primeira vez, insere as informações corretamente e passa para a próxima página. | event1:1002 | 3 |
| Jamie | O usuário exibe a página pela primeira vez | evento 1 | 4 |
| Jamie | O usuário esquece de preencher o campo de sobrenome no formulário. O formulário é exibido novamente com as informações ausentes realçadas. | evento 1 | 5 |

Observe o seguinte ao selecionar IDs de serialização:

* IDs de serialização devem ter 20 caracteres ou menos.
* IDs de serialização devem conter caracteres alfanuméricos.
* IDs de serialização são separadas para cada evento bem-sucedido. Portanto, você pode usar a mesma ID para vários eventos de sucesso, se necessário, não somente para o mesmo evento bem-sucedido.
* As IDs de serialização estão vinculadas ao conjunto de relatórios, portanto, lembre disso se você usa marcação multiconjunto para enviar dados a vários conjuntos de relatórios.
* As IDs de serialização nunca expiram, portanto, mesmo que a mesma ID seja usada anos depois, o evento bem-sucedido não será contado novamente.
* A exclusão de cookie não impede a serialização da ID de evento porque as IDs de serialização são armazenadas nos servidores da Adobe e não têm por base cookies.
* O único evento bem-sucedido com o qual não é possível usar a serialização de ID de evento é o evento de Compra, que usa uma variável especial s.purchaseID para a serialização.

## Serialização de eventos - Uma vez por visita {#section_C919D44F321A47FBBF043D0C57A2A050}

O[!DNL Analytics] oferece um recurso para permitir o acionamento de um evento apenas uma vez a cada visita.

Isso pode ser ativado na interface do usuário: **[!UICONTROL Admin]** &gt; **[!UICONTROL Conjunto de relatórios]** &gt; **[!UICONTROL Editar configurações]** &gt; **[!UICONTROL Conversão]** &gt; **[!UICONTROL Eventos bem-sucedidos]**.
