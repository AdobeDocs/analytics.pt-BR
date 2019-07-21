---
description: Uma propriedade da Web pode ser qualquer agrupamento de um ou mais domínios e subdomínios com uma biblioteca de regras incluída em um código de incorporação.
keywords: Implementação do Analytics; método de implementação; gerenciamento dinâmico de tags; dtm; propriedade da Web; propriedade
seo-description: Uma propriedade da Web pode ser qualquer agrupamento de um ou mais domínios e subdomínios com uma biblioteca de regras incluída em um código de incorporação.
seo-title: Criar propriedade da Web
solution: Analytics
title: Criar propriedade da Web
topic: Desenvolvedor e implementação
uuid: f 19 d 5504-eb 44-4 d 93-a 387-7470 ab 4 b 3 a 3 a
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# Criar propriedade da Web

Uma propriedade da Web pode ser qualquer agrupamento de um ou mais domínios e subdomínios com uma biblioteca de regras incluída em um código de incorporação.

>[!NOTE]
>
>Somente um usuário com direitos de administrador pode criar uma propriedade. For more information about roles, see [Create and Manage Groups in DTM](https://marketing.adobe.com/resources/help/en_US/dtm/groups.html) in the Dynamic Tag Management Product Documentation.

É possível gerenciar e rastrear esses ativos da mesma maneira com o DTM. Por exemplo, suponhamos que você tenha vários sites baseados em um só modelo e queira rastrear os mesmos recursos em todos eles. É possível aplicar uma propriedade da Web a vários domínios.

Para obter informações gerais sobre propriedades da Web e práticas recomendadas, consulte [Propriedades da Web](https://marketing.adobe.com/resources/help/en_US/dtm/web_property.html) na Documentação do produto do Gerenciamento dinâmico de tags.

1. Navigate to your company page, then click **[!UICONTROL Add Property]**.

   ![](assets/dtm-create-web-property.png)

1. Preencha os campos:

   <table id="table_376D72251C4D4C4CA878D10C18D2532C"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Elemento </th> 
    <th colname="col2" class="entry"> Descrição </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Nome</span> </td> 
    <td colname="col2"> <p>O nome da sua propriedade. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> URL</span> </td> 
    <td colname="col2"> <p>O URL de base da propriedade. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Esse site passa por vários domínios </span> </td> 
    <td colname="col2"> <p>Você pode adicionar e remover domínios, se desejar que os dados do visitante persistam entre domínios. Se essa opção for selecionada, os dados da visita serão persistidos nos subdomínios. </p> <p>Essa configuração permite especificar como você gostaria de rastrear o tráfego entre os subdomínios ou domínios associados. Links para subdomínios são tratados como links de saída. As visitas a subdomínios são rastreadas separadamente. </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. (Opcional) Defina as [!UICONTROL Configurações avançadas].

   <table id="table_6E687FBE6ACC4301BCCD837F4DCBB9C9"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Elemento </th> 
    <th colname="col2" class="entry"> Descrição </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Permitir aprovação de regras múltiplas</span> </td> 
    <td colname="col2"> <p>Permite que várias regras da propriedade sejam aprovadas de uma vez. A aprovação padrão permite somente uma aprovação de regra. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Habilitar publicação seletiva</span> </td> 
    <td colname="col2"> <p>Especifica se deve permitir que os usuários selecionem quais regras aprovadas serão publicadas. Esta é a opção preferencial. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Nome do cookie de rastreamento</span> </td> 
    <td colname="col2"> <p>Substitui o nome do cookie do rastreamento padrão. Você pode personalizar o nome usado pelo Dynamic Tag Management para rastrear o status de opção de não participação para receber outros cookies. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Tempo limite da tag</span> </td> 
    <td colname="col2"> <p>Especifica a quantidade de tempo que o Dynamic Tag Management aguarda para o acionamento de uma tag antes de atingir o tempo limite e cancelar a solicitação de tag. </p> <p> Devido ao funcionamento do Dynamic Tag Management, não se preocupe se esse for um número alto. O DTM possui métodos eficazes para garantir que tags lentas não afetem a experiência do usuário. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Atraso de âncora</span> </td> 
    <td colname="col2"> <p>Especifica a quantidade de tempo que o Dynamic Tag Management aguarda para o acionamento das tags em links clicados antes de passar para a próxima página. O valor padrão é 100 milissegundos. </p> <p>Atrasos maiores aumentam a precisão do rastreamento. A Adobe recomenda um atraso máximo de 500 milissegundos, que não é percebido pelo usuário. </p> <p>O Dynamic Tag Management aguardará durante o tempo especificado, mas se o beacon for acionado antes, o atraso será cortado. (Ou seja, nem sempre o usuário esperará por todo o tempo do atraso.) </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Clique em **[!UICONTROL Criar propriedade]**.
