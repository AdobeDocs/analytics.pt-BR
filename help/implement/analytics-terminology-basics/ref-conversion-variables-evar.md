---
description: A variável de conversão do Custom Insight (ou eVar) é colocada no código da Adobe em páginas da Web selecionadas do site. Seu propósito principal é segmentar métricas de sucesso de conversão em relatórios de marketing personalizados.
keywords: Analytics Implementation;eVar;conversion variable;eVar value;conversion;success event
title: Variáveis de conversão (eVars)
topic: Developer and implementation
uuid: 50071c1c-be00-4b3a-a7ee-5d129acf498b
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Variáveis de conversão (eVars)

A variável de conversão do Custom Insight (ou eVar) é colocada no código da Adobe em páginas da Web selecionadas do site. Seu propósito principal é segmentar métricas de sucesso de conversão em relatórios de marketing personalizados.

O melhor uso das eVars é para medir causa e efeito, como:

* Quais campanhas internas influenciaram a receita
* Quais anúncios em banner resultam em um registro
* O número de vezes em que uma pesquisa interna foi usada antes de um pedido ser feito

>[!IMPORTANT]
>
>Ao implementar o Analytics, é importante saber quais e quantas eVars você usará. Você também deve saber como configurar as eVars no Admin Console. Para obter informações detalhadas sobre eVars, consulte [Variáveis de conversão (eVar)](https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html) na documentação de Ajuda e referência do Analytics.

Uma eVar pode ter por base visitas e funcionar de forma semelhante aos cookies. Os valores passados para variáveis eVar seguem o usuário por um período predeterminado.

Quando uma eVar é definida como um valor para um visitante, a Adobe se lembra automaticamente desse valor até sua expiração. Quaisquer eventos bem-sucedidos que um visitante encontrar enquanto o valor da eVar está ativo são contados no valor da eVar.

> [!NOTE] Somente um valor único pode ser armazenado em uma eVar em uma solicitação de imagem. Se vários valores forem desejados no valor de uma eVar, recomendamos a implementação de [Listar variáveis](/help/implement/js-implementation/page-variables/listvariable.md) (list vars).

Para obter mais informações sobre variáveis, consulte:

* [Variáveis para implementação e relatórios do Analytics](/help/implement/js-implementation/c-variables/sc-variables.md) nesta ajuda
* [Variáveis - Como são usadas em relatórios](https://marketing.adobe.com/resources/help/en_US/reference/variable_definitions.html)
* [Variáveis de página](/help/implement/js-implementation/page-variables/page-variables.md)
* [Variável da campanha](/help/implement/js-implementation/page-variables/campaign.md)
* [Variável products](/help/implement/js-implementation/page-variables/products.md)
* [Variável de produtos](https://marketing.adobe.com/resources/help/en_US/mobile/android/products.html) na documentação do SDK móvel

