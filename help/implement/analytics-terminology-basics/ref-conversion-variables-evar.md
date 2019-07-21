---
description: A variável de conversão do Custom insight (ou eVar) é colocada no código da Adobe em páginas da Web selecionadas do site. Seu propósito principal é segmentar métricas de sucesso de conversão em relatórios de marketing personalizados.
keywords: Implementação do Analytics; Evar; variável de conversão; valor de evar; conversão; evento bem-sucedido
seo-description: A variável de conversão do Custom insight (ou eVar) é colocada no código da Adobe em páginas da Web selecionadas do site. Seu propósito principal é segmentar métricas de sucesso de conversão em relatórios de marketing personalizados.
seo-title: Variáveis de conversão (evars)
solution: Analytics
title: Variáveis de conversão (evars)
topic: Desenvolvedor e implementação
uuid: 50071 c 1 c-be 00-4 b 3 a-a 7 ee -5 d 129 acf 498 b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Variáveis de conversão (evars)

A variável de conversão do Custom insight (ou eVar) é colocada no código da Adobe em páginas da Web selecionadas do site. Seu propósito principal é segmentar métricas de sucesso de conversão em relatórios de marketing personalizados.

O melhor uso das eVars é para medir causa e efeito, como:

* Quais campanhas internas influenciaram a receita
* Quais anúncios em banner resultam em um registro
* O número de vezes em que uma pesquisa interna foi usada antes de um pedido ser feito

>[!IMPORTANT]
>
>Ao implementar o Analytics, é importante saber quais evars você usará e quantas. Você também deve saber como configurar as eVars no Admin Console. Para obter informações detalhadas sobre eVars, consulte [Variáveis de conversão (eVar)](https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html) na documentação de Ajuda e referência do Analytics.

Uma eVar pode ter por base visitas e funcionar de forma semelhante aos cookies. Os valores passados para variáveis eVar seguem o usuário por um período predeterminado.

Quando uma eVar é definida como um valor para um visitante, a Adobe se lembra automaticamente desse valor até sua expiração. Quaisquer eventos bem-sucedidos que um visitante encontrar enquanto o valor da eVar está ativo são contados no valor da eVar.

>[!NOTE]
>
>Apenas um único valor pode ser armazenado em uma evar em uma solicitação de imagem. Se vários valores forem desejados no valor de uma eVar, recomendamos a implementação de [](/help/implement/js-implementation/c-variables/page-variables.md)Listar variáveis (list vars).

Para obter mais informações sobre variáveis, consulte:

* [Variáveis para implementação e relatórios do Analytics](../../implement/js-implementation/c-variables/sc-variables.md#concept_E10E43221A2740FAAF900B79CE1EC5FB) nesta ajuda
* [Variáveis - Como são usadas em relatórios](https://marketing.adobe.com/resources/help/en_US/reference/variable_definitions.html)
* [Variáveis de página](/help/implement/js-implementation/c-variables/page-variables.md)
* [Variável de campanha](/help/implement/js-implementation/c-variables/page-variables.md)
* [Variável products](/help/implement/js-implementation/c-variables/page-variables.md)
* [Variável de produtos](https://marketing.adobe.com/resources/help/en_US/mobile/android/products.html) na documentação do SDK móvel

