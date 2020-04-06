---
description: Uma propriedade da Web pode ser qualquer agrupamento de um ou mais domínios e subdomínios com uma biblioteca de regras incluída em um código de incorporação.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;web property;property
title: Criar propriedade da Web
topic: Developer and implementation
uuid: f19d5504-eb44-4d93-a387-7470ab4b3a3a
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Criar propriedade da Web

Uma propriedade da Web pode ser qualquer agrupamento de um ou mais domínios e subdomínios com uma biblioteca de regras incluída em um código de incorporação.

>[!NOTE] Somente um usuário com direitos de Administrador pode criar uma propriedade. Para obter mais informações sobre funções, consulte [Criar e gerenciar grupos no DTM](https://marketing.adobe.com/resources/help/pt_BR/dtm/groups.html) na Documentação de produto do Dynamic Tag Management.

É possível gerenciar e rastrear esses ativos da mesma maneira com o DTM. Por exemplo, suponha que você tenha vários sites baseados em um modelo e queira rastrear os mesmos ativos em todos esses sites. Você pode aplicar uma propriedade da Web a vários domínios.

Para obter informações gerais sobre propriedades da Web e práticas recomendadas, consulte [Propriedades da Web ](https://marketing.adobe.com/resources/help/pt_BR/dtm/web_property.html)na Documentação de produto do Dynamic Tag Management.

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
    <td colname="col2"> <p>Você pode adicionar e remover domínios se desejar que os dados do visitante persistam entre domínios. Se essa opção for selecionada, os dados da visita persistirão em subdomínios. </p> <p>Essa configuração permite especificar como você gostaria de rastrear o tráfego entre os subdomínios ou domínios associados. Links para subdomínios são tratados como links de saída. Visitas a subdomínios são rastreadas separadamente. </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. (Opcional) Configurar [!UICONTROL Advanced Settings].

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
    <td colname="col2"> <p>Permite que várias regras da propriedade sejam aprovadas de uma vez. A aprovação padrão permite somente a aprovação de regra única. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Habilitar publicação seletiva</span> </td> 
    <td colname="col2"> <p>Especifica se deve permitir que os usuários selecionem quais regras aprovadas serão publicadas. Esta é a opção padrão. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Nome do cookie de rastreamento</span> </td> 
    <td colname="col2"> <p>Substitui o nome do cookie do rastreamento padrão. Você pode personalizar o nome que o Gerenciamento dinâmico de tags usa para rastrear seu status de não participação para receber outros cookies. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Tempo limite da tag</span> </td> 
    <td colname="col2"> <p>Especifica por quanto tempo o Gerenciamento dinâmico de tags aguardará o acionamento de uma tag antes de expirar e cancelar a solicitação da tag. </p> <p> Devido ao funcionamento do Dynamic Tag Management, não se preocupe se esse for um número alto. O DTM tem métodos eficazes para garantir que tags lentas não afetem a experiência do usuário. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Atraso de âncora</span> </td> 
    <td colname="col2"> <p>Especifica a quantidade de tempo que o Dynamic Tag Management aguarda para o acionamento das tags em links clicados antes de passar para a próxima página. O valor padrão é 100 milissegundos. </p> <p>Atrasos maiores aumentam a precisão do rastreamento. A Adobe recomenda um atraso máximo de 500 milissegundos, que não é percebido pelo usuário. </p> <p>O Gerenciamento dinâmico de tags aguardará até o tempo especificado, mas se o beacon for acionado mais cedo, o atraso será reduzido. (Ou seja, nem sempre o usuário esperará por todo o tempo do atraso.) </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Clique em **[!UICONTROL Create Property]**.
